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
Eine Einschränkung ist zum Beispiel: Es ist keine Klassenhierarchie möglich, einzig eine `abstract value class` kann `extends` werden.

Zum Ausprobieren:
 - `sdk install java 28.0.0.0+ea.18-open` (oder von https://jdk.java.net/28/ herunterladen)
 - auf die neueste IntelliJ Version upgraden und Java 28 ea, `X Experimental features` sowie `--enable-preview` einschalten)

Wichtig, jetzt schon vorzubereiten (hilft auch allgemein):
- Verwendungen von `==` eliminieren, insbesondere in `.equals()` Implementationen

https://m.devoxx.com/events/dvbe26/talks/15354/will-valhalla-fix-tony-s-billion-dollar-mistake

https://www.youtube.com/watch?v=vLDbzmiT7Xs

https://www.infoq.com/presentations/Null-References-The-Billion-Dollar-Mistake-Tony-Hoare/


# Write Java Code Like a Seasoned Hacker: 2026 Edition

Soroosh Khodami

Sehr empfehlenswert. Ich war beeindruckt von den Supply/Build Chain Attacken.

Was er uns nahelegt:
- nur Standard Repositories verwenden (Maven Central, jcenter), *keine* "Schubidu" Repositories
- falls man doch eine Bibliothek aus einem "Schubidu" Repository braucht: Die benötigte Version herunterladen, scannen und ins eigene Artifactory stellen
- unser Artifactory darf aus dem Internet nicht erreichbar sein
- eigene Bibliotheken signieren

https://m.devoxx.com/events/dvbe26/talks/8194/write-java-code-like-a-seasoned-hacker-2026-edition

https://www.youtube.com/watch?v=Upd5ZqUn1qY&list=PLKlmOVksNGoE&index=3&pp=iAQB


# Structured Concurrency Looms

Alan Bateman, Viktor Klang

Dieser Vortrag festig nochmals, was man im Hands-On Lab gelernt hat.

https://m.devoxx.com/events/dvbe26/talks/29351/structured-concurrency-looms

https://www.youtube.com/watch?v=aow56RgptLA&list=PLKlmOVksNGoE&index=9&pp=iAQB


# Engineering for the Long Haul: Operating Open Source at Scale

Sven Sellen

Eher eine Werbeveranstaltung, aber mit interessanten Ansätzen. Er behauptet, für zahlende Kunden ihren ganzen Dependency Baum von CVE's zu befreien.

https://m.devoxx.com/events/dvbe26/talks/49253/engineering-for-the-long-haul-operating-open-source-at-scale

https://www.youtube.com/watch?v=Pg5kS8l9CpI&list=PLKlmOVksNGoE&index=23&pp=iAQB



# G1, ZGC, Shenandoah, ... with all these GCs in Java, which one do I choose?

Antoine Dessaigne

Eine sehr gut verständliche Erklärung, wie Garbage Kollektoren funktionieren

https://m.devoxx.com/events/dvbe26/talks/9008/g1-zgc-shenandoah-with-all-these-gcs-in-java-which-one-do-i-choose

(online leider nicht gefunden)

---
Zwischendurch, so zur Entspannung, ein paar KI-generierte Kurzfilme "Die Devoxx Miniserie". Sie wurden uns in den Pausen präsentiert.

Kinepolis im Jahr 2170:
https://www.youtube.com/watch?v=FFRdupUFpL0&list=PLKlmOVksNGoE&index=2&pp=iAQB

Die Singularität:
https://www.youtube.com/watch?v=9Uz6lyElOL0&list=PLKlmOVksNGoE&index=3&pp=iAQB

Die Rebellion:
https://www.youtube.com/watch?v=CscMBNKvQA8&list=PLKlmOVksNGoE&index=4&pp=iAQB

Viel Spass!
---

