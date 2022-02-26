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
      B-->F[Output 1];
      C-->G[Output 2];
      D-->H[Output 3];
      E-->I[Output 4];
```

Effekt: Der Ausdruck erfolgt 4 Mal, statt nur 1 Mal.


## Korrektur 2

Die Ausgabe wird direkt auf dem generierenden Server angestossen:


```mermaid
  graph TD;
      A[Generierungsserver n]-->O[Output n];
      O--Rptjob_Generierung_beendet-->B[Cluster Server 1];
      O--Rptjob_Generierung_beendet-->C[Cluster Server 2];
      O--Rptjob_Generierung_beendet-->D[Cluster Server 3];
      O--Rptjob_Generierung_beendet-->E[Cluster Server 4];
```

Effekt: Der Ausdruck erfolgt nur noch 1 Mal.