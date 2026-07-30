# Mac-Coach – Anleitung für Julien

Ein Spaced-Repetition-Lernsystem für Mamas neuen MacBook Air. Eine einzige Datei (`index.html`), läuft komplett ohne Internet und ohne Server direkt im Browser. Der Lernstand wird im Browser gespeichert (localStorage).

## Übergabe an Mama (einmalig, ~5 Minuten)

1. `index.html` auf ihren Mac bringen (AirDrop oder USB-Stick).
2. Datei in ihren Ordner **Dokumente** legen und am besten ein Alias auf den Schreibtisch: Rechtsklick → „Alias erstellen" → Alias auf den Schreibtisch ziehen und z.B. „Mac lernen" nennen.
3. Doppelklick öffnet die App im Browser. Wichtig: **immer im selben Browser** öffnen (Safari ODER Chrome festlegen), sonst hat sie zwei getrennte Speicherstände. Festlegen: Rechtsklick auf die Datei → „Informationen" → „Öffnen mit" → Browser wählen → „Alle ändern".
4. In den Einstellungen (⚙️ oben rechts) ihren Vornamen eintragen.
5. **Die erste Runde macht ihr zu zweit.** Danach ist das Ritual: morgens Doppelklick, Karten durchgehen, fertig.

## Wie es funktioniert

- Pro Tag kommen **3 neue Themen** (einstellbar) plus alle fälligen Wiederholungen.
- **9 Karten haben interaktive Spiel-Übungen** (alle 6 Trackpad-Karten + Ordner anlegen, Datei verschieben, Papierkorb): Die App erkennt die echte Aktion (Klick, Rechtsklick, Doppelklick, Scrollen, Ziehen) und bewertet selbst:
  - Übung geschafft → das Übungsfeld verwandelt sich in eine große grüne Fläche („Perfekt – das hat geklappt!"), zählt automatisch als „Kann ich"
  - Falsche Aktion → sanftes Feedback, was stattdessen passiert ist („Das war ein normaler Klick …"). Nach 2 Fehlversuchen klappt die Hilfe von selbst auf, nach 4 kommt ein druckfreier Ausstieg („kommt morgen einfach nochmal").
  - **Ab der ersten Wiederholung** folgt nach der Spiel-Übung die Echt-Zugabe: „Und jetzt in echt, auf deinem Mac" mit Selbstauskunft („Hat geklappt" / „Klappt noch nicht" → kommt morgen wieder).
- Die übrigen Karten (Internet, Mail, Schreibtisch-Theorie) laufen über Selbsteinschätzung:
  - 😅 **Zeig's mir gleich nochmal** → Karte kommt am Ende der Runde erneut, morgen wieder
  - 🙂 **Geht so** → morgen wieder
  - 😄 **Kann ich!** → Abstand wächst eine Stufe

### Der Wiederholungs-Rhythmus ist überall sichtbar

Nach jedem Erfolg steht auf dem Bildschirm, **wann genau** die Übung wiederkommt („Diese Übung kommt morgen wieder", „in 4 Tagen", „in einer Woche") plus eine Leiste `1 › 2 › 4 › 7 › 14 › 30 › 60 Tage Abstand`, in der die aktuelle Stufe markiert und die erreichten abgehakt sind. Auch die Knöpfe sagen die Folge an („dann erst in 4 Tagen wieder" / „dann morgen nochmal"). So ist ohne Fachbegriffe klar: manche Dinge sind Wiederholung, und der Abstand wächst mit jedem Erfolg.

Die Stufen im Detail: **jede neue Übung kommt am nächsten Tag wieder** (dort erscheint dann auch die Echt-Zugabe), danach nach 2, 4, 7, 14, 30 und 60 Tagen. Ab Stufe 4 (Wochenabstand) gilt eine Karte in der Themenliste als „✓ sitzt". „Geht so" oder „Klappt noch nicht" wirft auf morgen zurück.
- **🤔 „Das möchte ich Julien fragen"** auf jeder Karte: markiert das Thema für euch. Die Liste steht in den Einstellungen unter „Fragen an Julien" – schaut da rein, wenn du sie besuchst.
- Über die Startseite kann sie jederzeit alles **nachschlagen** (ohne Bewertung).

## Inhalt (Prototyp: 25 Karten, 5 Themen)

Trackpad & Klicken (6) · Schreibtisch & Dock (5) · Ordner & Dateien (5) · Internet & YouTube (5) · E-Mail (4)

## Sicherung

Der Lernstand liegt nur im Browser. Falls sie mal den Browserverlauf/Websitedaten löscht, wäre er weg. Deshalb gelegentlich: Einstellungen → „Sicherung herunterladen" (kleine JSON-Datei, lässt sich dort auch wieder einspielen).

## Ideen für Stufe 2 (bewusst noch nicht gebaut)

- Echte Rückfragen per KI (bräuchte einen kleinen Server oder API-Key auf ihrem Mac)
- Fake-Browser und Fake-Mail als Spiel-Übungen (erst, wenn sich der Simulations-Ansatz bewährt; Gefahr: Simulation weicht vom echten Programm ab)
- Mehr Themen: WLAN, Lautstärke, Fotos, FaceTime, Software-Updates, Passwörter

Neue Karten hinzufügen: in `index.html` im Block `const KARTEN = [...]` einfach einen Eintrag nach dem Muster der anderen ergänzen (plus ggf. eine Grafik-Funktion in `GRAFIKEN`).
