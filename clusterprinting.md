## Ausgangslage

TEC-3655 "B4LCH - Monitoring 900 - mehrere Druckjobs von Serviceaufträgen auf Lieferscheindruck auf in Arbeit stehen geblieben"

Bei einigen Report Jobs geht der Status nicht auf `Beendet`, obwohl bis zum Output alles ausgeführt wurde.


## Korrektur für TEC-3655

Unter anderem versuchen wir, die Report Job Events im Cluster zu synchronisieren, so dass sie alle Server erhalten:

```mermaid
  graph TD;
      A[Generierungsserver n]--Rptjob_Generierung_beendet-->B[Cluster Server 1];
      A--Rptjob_Generierung_beendet-->C[Cluster Server 2];
      A--Rptjob_Generierung_beendet-->D[Cluster Server 3];
      A--Rptjob_Generierung_beendet-->E[Cluster Server 4];
      B-->F[Gruppen Ausgabe 1];
      C-->G[Gruppen Ausgabe 2];
      D-->H[Gruppen Ausgabe 3];
      E-->I[Gruppen Ausgabe 4];
```

Effekt: Der Gruppen-Ausdruck erfolgt 4 Mal, statt nur 1 Mal. (Der Einzel-Ausdruck funktioniert nach wie vor).

TEC-3822 "B4LCH - Rechnungen werden 4 fach gedruckt (pro Server im Cluster)"


## Korrektur für TEC-3822

Die Gruppen-Ausgabe wird direkt auf dem generierenden Server angestossen:


```mermaid
  graph TD;
      A[Generierungsserver n]--Generierung_beendet-->B[Server 1];
      A--Generierung_beendet-->C[Server 2];
      A--Generierung_beendet-->D[Server 3];
      A--Generierung_beendet-->E[Server 4];
      A-->O[Gruppen Ausgabe n];
```

Effekt: Der Gruppen-Ausdruck erfolgt nur noch 1 Mal.


## Zoom auf den Generierungsserver


```mermaid
  graph TD;
      A[Generierungsserver]-->G[Generierung];
      G--Generierung_beendet-->C[Event Konsument = neuer Thread];
      C-->B[Update Generierungsstatus];
      G-->T[Test alle generiert?];
      T-->O[Gruppen Ausgabe];
```

Da der Update des Generierungsstatus in einem separaten Thread statt findet, kann es sein dass beim Test der Status auf der RDB noch nicht sichtbar ist.


## Weitere Korrektur für TEC-3822

Der Generierungsstatus wird sofort persistiert:

```mermaid
  graph TD;
      A[Generierungsserver]-->G[Generierung];
      G-->B[Update Generierungsstatus];
      B--Generierung_beendet-->C[Event Konsument = neuer Thread];
      B-->T[Test alle generiert?];
      T-->O[Gruppen Ausgabe];
```

Somit findet der Test für die Gruppenausgabe immer die aktuellsten Stati vor. 

Natürlich muss auch im Fehlerfall korrekt persistiert werden: TEC-3846 "PQ: Generierung bleibt auf in Arbeit bei ReportJobGruppe mit einem Fehlerhaften Reportjob" gab noch eine kleine Ehrenrunde.


## Zusammenfassung

Durch Anstossen der Ausgabe auf dem generierenden Server (Sender statt Empfänger) verhindern wir mehrfachen Output.

Durch sofortiges Persistieren des Generierungsstatus (Sender statt Empfänger) liefern wir den Nachfolgern die korrekte Information.

Alle Korrekturen sind in den folgenden Frame Versionen enthalten:
 - `56.0.0`
 - `55.0.2`
 - `54.0.3`
 - `53.0.2`

Wir sind zuversichtlich, dass diese Korrekturen auch zu einer Verbesserung des ursprünglichen Problems beitragen.
Dies muss in der Produktion jedoch noch bestätigt werden.

