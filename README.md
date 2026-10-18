# Welle Null

**Reinhören:** https://thenickcoolst.github.io/welle-null/

Welle Null ist ein Radiosender, der seine Musik selbst komponiert. Jeder Titel entsteht live im Browser mit der Web Audio API. Die Uhrzeit legt Titel, Tempo, Tonart und jede einzelne Note fest. Deshalb hören alle, die gerade eingeschaltet haben, im selben Moment denselben Ton, obwohl kein Audio übertragen wird.

- 6 Sendungen nach Berliner Zeit: Nachtschicht, Frühfunk, Mittagswelle, Nachmittagsdrift, Feierabend-Synth, Spätlese
- Ansagen per Sprachausgabe des Browsers (Uhrzeit, Titel, Interpret)
- Lautsprechergitter als Spektrumanzeige, 24-Stunden-Senderskala
- Keine Samples, kein Server, kein Stream, keine Werbung, kein Tracking

## So funktioniert es

Der Tag ist in Slots von 210 Sekunden geteilt. Die Slot-Nummer ist der Seed für einen Hash, aus dem Tempo, Tonart, Akkordfolge, Schlagzeugmuster und Melodie-Motiv entstehen. Jede Note wird aus `(slot, step)` berechnet, also kann man mitten im Titel einschalten und landet an derselben Stelle wie alle anderen. Ein Lookahead-Scheduler plant die Noten ein paar hundert Millisekunden im Voraus.

Alles steckt in einer einzigen `index.html`.

---

**English:** A 24/7 generative radio station. The clock is the stream: every note is derived from the current time slot, synthesized locally with the Web Audio API, so all listeners hear the same thing at the same moment. No samples, no server, no ads.
