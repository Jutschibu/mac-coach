# Mac-Coach – Anleitung für Julien

Ein Spaced-Repetition-Lernsystem, mit dem Mama den Umgang mit ihrem MacBook Air lernt: 32 Karten in 6 Themen, davon 9 mit interaktiven Übungen, die echte Aktionen erkennen (Klick, Rechtsklick, Doppelklick, Scrollen, Ziehen, Fake-Finder).

**Live:** https://jutschibu.github.io/mac-coach/
**Quelle:** `~/Documents/Claude/Mac-Coach/` (Git-Repo, GitHub: `Jutschibu/mac-coach`, öffentlich)

---

## Teil 1: Einmalige Einrichtung bei Mama (ca. 5 Minuten, ihr macht das zusammen)

Ziel: Sie hat ein Icon im Dock, ein Klick öffnet die App. Kein Browser, keine Adresse, kein Suchen.

1. Auf **ihrem** Mac **Safari** öffnen (nicht Chrome – der Dock-Weg ist in Safari zuverlässiger).
2. Oben in die Adressleiste eingeben: `jutschibu.github.io/mac-coach`
3. Wenn die App da ist: In der Menüleiste oben auf **Ablage → Zum Dock hinzufügen**, Name „Mac-Coach" bestätigen. Jetzt liegt ein Icon (weißes Laptop mit grünem Haken) im Dock.
4. **Wichtig:** Ab jetzt öffnet sie die App **immer über dieses Dock-Icon**, nie mehr über Safari. Grund: Safari führt für die Dock-App einen eigenen Speicher – wenn sie mal im Browser und mal im Dock übt, hätte sie zwei getrennte Lernstände.
5. Im Dock-Fenster oben rechts auf **⚙️** und ihren Vornamen eintragen (für die Begrüßung).
6. **Die erste Runde macht ihr gemeinsam.** Danach ist das Ritual: morgens Dock-Icon anklicken, „Jetzt üben", durchgehen, fertig.

Wenn das Icon im Dock verrutscht oder verschwindet: Schritte 1 bis 3 wiederholen, der Lernstand bleibt erhalten.

## Teil 2: Änderungen und Updates

Du sagst mir im Chat, was du willst („füge ein Thema WLAN hinzu", „die Rechtsklick-Erklärung ist zu lang", „baue eine Übung für Lautstärke"). Ich ändere die App, teste sie im Browser und veröffentliche sie. Bei ihr passiert dann Folgendes von allein:

- Beim nächsten Öffnen holt sich die App die neue Fassung (sie prüft beim Start `version.json` und lädt sich bei Bedarf einmal selbst neu).
- **Ihr Lernstand bleibt dabei komplett erhalten** – der liegt in ihrem Browser, nicht in der App-Datei.
- Neue Karten tauchen automatisch als „✨ neu" im normalen Rhythmus auf, bestehende behalten ihre Stufe.
- Ist im `version.json` ein Text unter `neu` hinterlegt, sieht sie beim Öffnen einmal einen freundlichen Hinweis („✨ Es ist etwas Neues dazugekommen: …"). Beim allerersten Start erscheint der Hinweis nie.

Sie muss also **nichts** installieren, nichts ersetzen, nichts bestätigen.

### Wenn du selbst etwas veröffentlichen willst

```bash
cd ~/Documents/Claude/Mac-Coach && git add -A && git commit -m "Was geändert wurde" && git push
```

Danach dauert es 1 bis 3 Minuten, bis GitHub die neue Fassung ausliefert.

**Zwei Regeln beim Ändern**, sonst geht ihr Lernstand für einzelne Karten verloren:
1. **Bei jeder Veröffentlichung** die Versionsnummer an **beiden** Stellen hochziehen: `VERSION` in `index.html` und `version` in `version.json`. Nur dann holt sich ihre App die neue Fassung.
2. **Karten-IDs nie umbenennen** (z.B. `rechtsklick`). Der Lernstand hängt an diesen IDs. Texte, Grafiken und Übungen darin ändern ist jederzeit gefahrlos.

---

## Wie das Lernsystem funktioniert

- Pro Tag kommen **3 neue Themen** (in den Einstellungen änderbar) plus alle fälligen Wiederholungen.
- **9 Karten haben interaktive Spiel-Übungen** (6 der 7 Trackpad-Karten + Ordner anlegen, Datei verschieben, Papierkorb). Die App erkennt die echte Aktion und bewertet selbst:
  - Geschafft → das Übungsfeld verwandelt sich in eine große grüne Fläche („Perfekt – das hat geklappt!") und zählt als „Kann ich".
  - Falsche Aktion → sanftes Feedback, was stattdessen passiert ist („Das war ein normaler Klick …"). Nach 2 Fehlversuchen klappt die Hilfe von selbst auf, nach 4 kommt ein druckfreier Ausstieg („kommt morgen einfach nochmal").
  - **Ab der ersten Wiederholung** folgt die Echt-Zugabe: „Und jetzt in echt, auf deinem Mac" mit „✓ Hat am Mac geklappt" / „Am Mac klappt's noch nicht".
- Die übrigen Karten laufen über Selbsteinschätzung (😅 gleich nochmal · 🙂 morgen wieder · 😄 Kann ich!).
- **Der Rhythmus ist überall sichtbar:** Nach jedem Erfolg steht da, wann die Übung wiederkommt, plus eine Leiste `1 › 2 › 4 › 7 › 14 › 30 › 60 Tage Abstand` mit markierter aktueller Stufe. Jede neue Übung kommt am nächsten Tag wieder, danach wachsen die Abstände. Ab Stufe 4 (Wochenabstand) gilt eine Karte als „✓ sitzt".

- **Themen frei üben:** In jedem Thema steht oben „▶ Jetzt … üben". Das startet eine Runde mit allen Karten des Themas – unabhängig vom Tageslimit und auch dann, wenn für heute schon alles erledigt ist. Die Bewertungen zählen ganz normal in den Wiederholungsrhythmus.
- **Einzelne Karte nachtragen:** Beim Nachschauen einer Karte gibt es „✓ Das habe ich gerade geübt" (= „Kann ich!", Karte steigt eine Stufe) und daneben „Nur angeschaut – zurück" (ändert nichts).
- **„Das kann ich schon"** ist der kleine, unterstrichene Knopf ganz unten auf einer Karte – bewusst klein, mit Rückfrage. Er setzt die Karte auf die höchste Stufe (60 Tage), sie verschwindet also aus dem täglichen Üben. Derselbe Knopf holt sie später wieder zurück („Doch wieder üben"). In der Themenliste steht dann „✓ kann ich schon".

**🤔 „Das möchte ich Julien fragen"** steht auf jeder Karte. Was sie markiert, sammelt sich in den Einstellungen unter „Fragen an Julien" – da schaust du rein, wenn du sie besuchst oder anrufst.

## Sicherung ihres Lernstands

Der Lernstand liegt nur in ihrem Browser. Falls sie mal Website-Daten löscht, wäre er weg. Deshalb gelegentlich: ⚙️ → „Sicherung herunterladen" (kleine Datei, dort auch wieder einspielbar).

## Datenschutz

Das Repo ist öffentlich, die App selbst enthält nur Lernkarten über Mac-Bedienung – nichts Persönliches. Ihr Lernstand, ihr Name und ihre Fragen werden **nie** hochgeladen, die bleiben ausschließlich auf ihrem Mac.

## Ideen für später (bewusst noch nicht gebaut)

- **Offline-Fähigkeit** (Service Worker): Bisher braucht sie WLAN. Absichtlich weggelassen, weil ein fehlerhafter Cache dazu führen kann, dass sie eine alte Fassung sieht – der am schwersten zu erklärende Fehler bei ihr.
- **Echte Rückfragen per KI** (bräuchte einen Server oder API-Key).
- **Fake-Browser und Fake-Mail** als Spiel-Übungen (Risiko: Simulation weicht vom echten Programm ab).
- **Mehr Themen:** WLAN, Lautstärke, Fotos, FaceTime, Software-Updates, Passwörter, Drucken.
