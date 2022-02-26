## Ausgangslage

Bei einigen Report Jobs geht der Status nicht auf `Beendet`, obwohl bis zum Output alles ausgeführt wurde.


## Korrektur 1

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


## Korrektur 2

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
      A[Generierungsserver]--Generierung_beendet-->B[Update Generierungsstatus];
      A-->T[Test Generierungsstatus];
      T-->O[Gruppen Ausgabe];
```

