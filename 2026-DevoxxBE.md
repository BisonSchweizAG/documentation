# Java is for Data Science, Too: Building an End-to-End ML Pipeline Without Leaving the JVM
Hands-On Lab (Sven Reimers, Zoran Sevarac)

Eine interessante Mischung von aktuellen Java Tools - unbedingt ausprobieren ;-)

- Die neueste Version des JTaccuino Studio von https://github.com/jtaccuino/jtaccuino/releases herunterladen und installieren
- Das .zip File von https://github.com/jtaccuino/devoxx-2026-hol/releases herunterladen und ins lokale `~/.m2` Verzeichnis entpacken
- Das Repo `git@github.com:jtaccuino/devoxx-2026-hol.git` klonen
- Mit dem Browser das File `devoxx-2026-hol/narrative/web/index.html` im geklonten Repo öffnen und damit die Notebooks im `/notebooks/exercises` Ordner durcharbeiten - es gibt auch `/notebooks/solutions`

Tipp: Das erwähnte GitHub Token braucht man nicht.

Zeitbedarf: mindestens 3 h




# Using Structured Concurrency and Scoped Values to Create a Virtual Threads Based Asynchronous Application

Hands-On Lab (Ana-Maria Mihalceanu, José Paumard)

Anhand einer vorbereiteten Anwendung mit 2 lokal laufenden Servern programmierst du sukzessive parallele Anfragen 
mit Abbruch- und Ausnahmebedingungen (unter Verwendung von `StructuredTaskScope`, `Joiner`, `Scoped Values`).

Für meinen Geschmack hat es am Anfang etwas viel "Data Driven Programming" - es fühlt sich an wie ein kaum endendes Refactoring von `record`s.
Aber dann wird es spannender. Also empfehlenswert (siehe auch Tipps).

- Klone https://github.com/JosePaumard/2026_DevoxxBE-Loom-lab.git
- arbeite `DevoxxBE-Loom-Lab.md` durch


Tipps: 
- die "Branches" sind Tags - nach `git checkout Step-xx` kann man sie mit `git switch -c Step-xx` in einen Branch wandeln.
- Man kann auch Schritte überspringen und weiter hinten fortfahren

Zeitbedarf: mindestens 4 h
