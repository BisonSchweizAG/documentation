# Java is for Data Science, Too: Building an End-to-End ML Pipeline Without Leaving the JVM
Hands-On Lab (Sven Reimers, Zoran Sevarac)

Eine interessante Mischung von aktuellen Java Tools - unbedingt ausprobieren ;-)

- die neueste Version des JTaccuino Studio von https://github.com/jtaccuino/jtaccuino/releases herunterladen und installieren
- das .zip File von https://github.com/jtaccuino/devoxx-2026-hol/releases herunterladen und ins lokale `~/.m2` Verzeichnis entpacken
- das Repo `git@github.com:jtaccuino/devoxx-2026-hol.git` klonen
- mit dem Browser das File `devoxx-2026-hol/narrative/web/index.html` im geklonten Repo öffnen und damit die Notebooks im `/notebooks/exercises` Ordner durcharbeiten - es gibt auch `/notebooks/solutions`

Tipp: Das erwähnte GitHub Token braucht man nicht.

Zeitbedarf: mindestens 3 h




# Using Structured Concurrency and Scoped Values to Create a Virtual Threads Based Asynchronous Application

Hands-On Lab (Ana-Maria Mihalceanu, José Paumard)

Anhand einer vorbereiteten Anwendung mit 2 lokal laufenden Servern programmierst du sukzessive parallele Anfragen 
mit Abbruch- und Ausnahmebedingungen (unter Verwendung von `StructuredTaskScope`, `Joiner`, `Scoped Values`).

Für meinen Geschmack hat es am Anfang etwas viel "Data Driven Programming" - es fühlt sich an wie ein kaum endendes Refactoring von `record`s.
Aber dann wird es spannender. Also empfehlenswert (siehe auch Tipps).

- klone https://github.com/JosePaumard/2026_DevoxxBE-Loom-lab.git
- arbeite `DevoxxBE-Loom-Lab.md` durch


Tipps: 
- die "Branches" sind Tags - nach `git checkout Step-xx` kann man sie mit `git switch -c Step-xx` in einen Branch wandeln.
- Man kann auch Schritte überspringen und weiter hinten fortfahren

Zeitbedarf: mindestens 4 h


# Analyze and Optimize Your Applications with JFR

Hands-On Lab  (Ana-Maria Mihalceanu, José Paumard)

Ein sehr gut vorbreitetes Lab, das ohne Probleme alleine durchgearbeitet werden kann.

Sehr empfehlenswert, um einen ersten Eindruck über JFR (Java Flight Recorder) zu bekommen.
Ich habe gelernt, wie ich mit dem jfr Tool aus einem laufenden Java Prozess Informationen holen kann.
Und wie ich selbst JFR Events schreiben kann.

- klone git@github.com:java/j126-hol-jfr.git
- Beginne mit dem `README`


Zeitbedarf: mindestens 3 h

---

Das war es von den Hands-On Labs, nun zu den Vorträgen, die auch online sind.

# Devoxx BE 2020 Youtube Playlist
Die ganze Playlist findet man hier:
https://www.youtube.com/playlist?list=PLKlmOVksNGoE

# Secure Your Coding Agent Like It’s Malware
Richard Gross

Der Titel sagt eigentlich schon allse...

https://m.devoxx.com/events/dvbe26/talks/7011/secure-your-coding-agent-like-it-s-malware

https://www.youtube.com/watch?v=GLJGhkxMdgU&list=PLKlmOVksNGoE&index=40&pp=iAQB


# Teaching a New Dog Old Tricks: Give the Agent a Debugger

Anton Arhipov

https://m.devoxx.com/events/dvbe26/talks/23533/teaching-a-new-dog-old-tricks-give-the-agent-a-debugger

https://www.youtube.com/watch?v=rk22mStXsGU


# One tool to rule them all: bash, a tiny LLM, and the birth of a coding agent

Philippe Charrière

Konstuiert mit Bash und einem lokalen LLM einen Coding Agent.

https://m.devoxx.com/events/dvbe26/talks/22911/one-tool-to-rule-them-all-bash-a-tiny-llm-and-the-birth-of-a-coding-agent

https://www.youtube.com/watch?v=wWfj4AJahlQ


# Will Valhalla Fix Tony's Billion-Dollar Mistake?

José Paumard, Rémi Forax

Value Klassen mit all ihren Vorteilen und Einschränkungen ausführlich erklärt.
Muss man gesehen haben. Insbesondere wenn Mario mal wieder fragt, ob wir einfach auf `value class`es umstellen könnten...

Zum Ausprobieren:
 - `sdk install java 28.0.0.0+ea.18-open` (oder von https://jdk.java.net/28/ herunterladen)
 - auf die neueste IntelliJ Version upgraden und Java 28 ea, `X Experimental features` sowie `--enable-preview` einschalten)

https://m.devoxx.com/events/dvbe26/talks/15354/will-valhalla-fix-tony-s-billion-dollar-mistake

https://www.youtube.com/watch?v=vLDbzmiT7Xs
