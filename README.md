# Whiteboard / Post-it Board – Hilfe

Diese Datei beschreibt die Bedienung von `post-it_v01.html`.

## 1. Grundidee

Die Seite ist ein großes, virtuelles Whiteboard (5000×5000 px) mit:

- **Post-it-Notizen** (Text + optionales Bild)
- **Verbindungen** (Linien mit Pfeilen und Text)
- **Gruppierung / Andocken** von Notizen als Ketten
- **Zoom & Navigation**
- **Speichern / Laden** des gesamten Boards oder einzelner Notizen
- **Seitliche Bibliothek** für wiederverwendbare Notizen (aus einem Ordner)

Alle Daten werden zusätzlich im **Local Storage des Browsers** gespeichert und beim Laden der Seite wiederhergestellt.

---

## 2. Oberfläche im Überblick

### Wichtige Bereiche

- **Whiteboard** (Mitte)  
  Großer Arbeitsbereich für Notizen und Verbindungen.

- **Viewport** (Fenster um das Whiteboard)  
  Scrollbarer Ausschnitt. Mit Scrollbalken und Zoom steuerbar.

- **Toolbar (oben links)**  
  Buttons für Speichern, Laden, Einstellungen, Undo/Redo, Löschen, Zoommodus.

- **Zoom-Controls (oben rechts, mittig)**  
  Prozentanzeige & +/− Buttons für Zoomstufe.

- **Sidebar / Bibliothek (rechts)**  
  Ausklappbare Leiste mit wiederverwendbaren Notizen (aus einem Ordner).

- **Floating „+ Neue Notiz“ (unten rechts)**  
  Erstellt eine neue Post-it-Notiz.

---

## 3. Notizen (Post-its)

### 3.1 Neue Notiz erstellen

- Button **„+ Neue Notiz“** (unten rechts).
- Die Notiz erscheint ungefähr in der Mitte des sichtbaren Bereichs.

Standard:
- Größe: ca. 220×220 px
- Farbe: Gelb
- Schriftgröße: über die Einstellungen konfigurierbar.

### 3.2 Notiz bewegen

- **Drag & Drop**:  
  Maus auf den **Kopfbereich** der Notiz (grauer Balken oben) → gedrückt halten → ziehen.

**Gruppenverhalten:**  
Bewegt man eine Notiz, werden **alle Notizen derselben Gruppe** mitbewegt (Kettenfunktion).  
Wenn du nur eine bestimmte Notiz unabhängig machen willst, siehe „Gruppierung / Andocken“.

### 3.3 Text bearbeiten

Es gibt zwei Modi, die du in den **Einstellungen** aktivierst:

- **Plain-Text-Modus (Standard, Markdown aus)**  
  - Der Textbereich ist ein normales Textfeld.
  - Klicken und direkt losschreiben.
- **Markdown-Modus (Markdown an)**  
  - Die Notiz zeigt den **gerenderten Markdown-Text** an.
  - **Doppelklick** auf den Text → Editor öffnet sich.
  - Bearbeiten → Fokusverlust (z.B. Klick außerhalb) speichert und rendert neu.

### 3.4 Farbe ändern

- Im Header der Notiz: **Farbfeld** (Farb-Picker).
- Klick darauf → Farbe auswählen → Notizhintergrund wird aktualisiert.

### 3.5 Bild hinzufügen

- Im Header der Notiz: **📷-Button**.
- Klick → Dateiauswahl → Bilddatei wählen.
- Das Bild erscheint oben in der Notiz; Höhe ist per **unterem Rand der Bildfläche** vertikal ziehbar.

Alternativ:
- Im Textfeld: **Bild aus Zwischenablage einfügen (Paste)**  
  → Bild wird als Data-URL in die Notiz eingehängt.

### 3.6 Bild entfernen

- Maus über das Bild → oben rechts erscheint ein kleiner **🗑️-Button**.
- Klick darauf → Rückfrage „Bild weg?“ → Bestätigen → Bild wird entfernt.

### 3.7 Größe einer Notiz ändern

- Notiz hat **Resize-Griffe** (Browser-Standard, meist unten/rechts).
- Maus an die Kante → ziehen → Größe wird geändert.
- Verbindungen werden automatisch neu gezeichnet.

---

## 4. Verbindungen zwischen Notizen

### 4.1 Verbindung erstellen

1. An einer Notiz: links oder rechts ist ein kleiner **Verbindungs-Handle** (vertikales Rechteck mit Rand).
2. Auf diesen Handle klicken und gedrückt halten → Maus ziehen (Kreuz-Cursor).
3. Maus über eine andere Notiz ziehen.
4. Maus loslassen über der Zielnotiz → Verbindung (Linie) wird erstellt (ohne Pfeil, ohne Text).

Eine temporäre gestrichelte Linie zeigt während des Ziehens den Verlauf.

### 4.2 Pfeil umschalten

- **Einfachklick** auf die Verbindungslinie → Pfeil wird umgeschaltet:
  - Keine Pfeilspitze
  - Pfeilspitze am Ende (Richtung: von „from“ zu „to“)

### 4.3 Kontextmenü der Verbindung

- **Rechtsklick** (Kontextmenü) auf die Linie oder den Text.
- Es erscheint das **Verbindungs-Menü** mit:

  - **Text (Einzeilig/Mehrzeilig)**  
    Textfeld für die Beschriftung.  
    Modus (einzeilig/mehrzeilig) wird zentral in den **Einstellungen** über  
    „Verbinder Mehrzeilig“ gesteuert.

  - **Linie Dicke** (Slider)  
    Einstellung der Strichbreite (px).

  - **Schriftgröße** (Slider)  
    Schriftgröße des Verbindungstextes (px).

  - **↔ Pfeil umschalten**  
    Schaltet die Pfeilspitze an/aus.

  - **🗑️ Löschen**  
    Entfernt diese Verbindung.

Änderungen werden **sofort** angezeigt und mit Verlassen des Menüs gespeichert.

### 4.4 Mehrzeiliger Text an Verbindungen

- In den **Einstellungen**: „Verbinder Mehrzeilig“ aktivieren.
- Der Text wird dann in einem **kleinen gedrehten Kasten** dargestellt, der Mehrzeilen unterstützt (mit Scrollbar, falls nötig).

---

## 5. Gruppierung, Andocken & Ketten

### 5.1 Grundprinzip

- Jede Notiz hat eine **Gruppen-ID**.
- Standard: Jede neue Notiz ist ihre **eigene Gruppe**.
- Beim **Andocken** an andere Notizen werden Gruppen **zusammengeführt**, sodass sie gemeinsam verschoben werden: eine **Kette**.

### 5.2 Andocken (Auto-Docking)

Nachdem du eine Notiz bewegt hast und die Maus loslässt, prüft das System für die „Haupt-Notiz“:

- **Andocken rechts**  
  Wenn die Notiz **nahe rechts** an einer anderen Notiz liegt (mit geringem Abstand, SNAP_DIST und DOCK_MARGIN intern festgelegt)  
  und die **Oberkanten** halbwegs übereinstimmen, schnappt sie rechts an.
- **Andocken unten**  
  Wenn sie **unterhalb** einer anderen Notiz liegt und die **linken Kanten** halbwegs übereinstimmen, schnappt sie darunter an.

Beim Andocken:
- Die gesamte Gruppe der bewegten Notiz wird verschoben.
- Alle Notizen dieser Gruppe werden der **Gruppe der Zielnotiz** zugewiesen.
- Alle Notizen dieser gemeinsamen Gruppe erhalten optisch einen leichten **Gruppen-Rahmen** (CSS-Klasse `grouped`).

So entstehen **Ketten von Post-its**, die als Verbund bewegt werden.

### 5.3 Notiz aus Gruppe lösen

Wenn eine Notiz Teil einer Gruppe mit mehr als einem Mitglied ist:

- Im Kopf der Notiz erscheint ein **🔗-Button** („Aus Gruppe lösen“).
- Klick darauf →  
  die Notiz bekommt eine **neue, eigene Gruppen-ID** und verlässt damit die Kette.
- Darstellung wird neu aufgebaut, Gruppenrahmen aktualisiert.

---

## 6. Auswahl & Zoom

### 6.1 Auswahl mehrerer Notizen

- Klick auf freien Bereich des Whiteboards.
- Mit gedrückter Maustaste **Rechteck aufziehen**.
- Alle Notizen, die mit diesem Rechteck überlappen, werden ausgewählt (blauer Rahmen).

Hinweis:  
Beim Verschieben über den Header wird standardmäßig die **Gruppe der angeklickten Notiz** bewegt.  
Die Rechteckauswahl wird hauptsächlich visuell/modular genutzt; das tatsächliche Verschieben nutzt die Gruppenlogik.

### 6.2 Zoom per Buttons

Rechts oben (Zoom-Leiste):

- **–**: Zoom verringern
- **100 %**: Anzeige der aktuellen Zoomstufe (Klick setzt auf 100 %)
- **+**: Zoom erhöhen

Der Zoom ist auf **0,2× bis 3×** begrenzt.

### 6.3 Zoom per Strg+Mausrad

Im Viewport:

- **Strg + Mausrad hoch/runter**  
  → rein-/rauszoomen.
- Zoom erfolgt **um die aktuelle Mausposition**, d.h. der Punkt unter dem Mauszeiger bleibt ungefähr im Blick.

### 6.4 Bereichs-Zoom (Zoommodus)

- In der Toolbar: **🔍-Button** (mit Tooltip „Bereich vergrößern“).
- Klick → Zoommodus **an/aus** (Cursor wird Fadenkreuz; Auswahlrahmen grünlich).

Im Zoommodus:

1. Auf freien Bereich klicken und ziehen → Rechteck aufziehen.  
2. Beim Loslassen wird der Zoom so gewählt, dass das Rechteck den Viewport fast ausfüllt.  
3. Der Viewport scrollt automatisch, um das ausgewählte Gebiet zu zentrieren.
4. Der Zoommodus schaltet sich danach automatisch wieder aus.

---

## 7. Speichern & Laden

### 7.1 Alles speichern

Toolbar:

- **💾-Button** → „Alles speichern“
- Erstellt eine `.json`-Datei mit:
  - allen Notizen
  - allen Verbindungen
  - Board-Einstellungen (Größe, Markdown, Standardwerte)
- Dateiname: `whiteboard_<timestamp>.json`

### 7.2 Alles laden

Toolbar:

- **📂-Button** (mit Tooltip „Alles laden“).
- Eine `.json`-Datei auswählen, die mit dieser App erzeugt wurde.
- Das gesamte Board wird durch den Inhalt der Datei ersetzt.

Nach dem Laden:
- Notizen & Verbindungen werden aufgebaut.
- Board-Größe, Markdown-Einstellung usw. werden übernommen.

### 7.3 Einzelne Notiz speichern

In jeder Notiz:

- **💾-Button** im Header → „Einzelne Notiz speichern“
- Speichert nur diese Notiz als  
  `note_<id>.json` (Typ: `{"type":"single_note", "note":{...}}`).

### 7.4 Einzelne Notiz laden (ins aktuelle Board)

Toolbar:

- **📥-Button** („Einzelne Notiz laden“).
- `.json`-Datei einer einzelnen Notiz wählen (Format wie oben).
- Die Notiz wird mit **neuer ID** in der Mitte des aktuellen sichtbaren Bereichs eingefügt.

---

## 8. Bibliothek / Sidebar

### 8.1 Sidebar öffnen/schließen

Rechts oben:

- **📚-Kreis-Button** → Sidebar ein-/ausblenden.

### 8.2 Ordner laden

In der Sidebar:

- Button **„📂 Ordner wählen“**.
- Einen Ordner auswählen, der `.json`-Dateien mit **einzelnen Notizen** enthält (Format wie `note_*.json`).

Das System:

- Liest alle `.json`-Dateien im Ordner.
- Für jede Datei mit `type: "single_note"` wird eine **Mini-Notiz** erzeugt:
  - Hintergrundfarbe wie Original
  - Optional kleines Bild
  - Kurzer Textauszug (ersten ca. 30 Zeichen)
  - Tooltip: Dateiname

### 8.3 Notiz aus Bibliothek ins Board ziehen

- Mini-Notiz in der Sidebar **per Drag & Drop** auf das Whiteboard ziehen.
- An der Drop-Position wird eine neue Notiz eingefügt:
  - Inhalt, Bild, Farbe wie im Mini-Notizdatensatz
  - Neue ID & eigene Gruppe
  - Position entspricht der Drop-Stelle (zentriert).

---

## 9. Kontextmenü fürs Einfügen (Copy & Paste)

### 9.1 Notiz kopieren

In der Notiz:

- **📄-Button** im Header → kopiert die Notiz intern in die Zwischenablage der App.
- Der Button zeigt kurz **„✅“**, um den Erfolg zu signalisieren.

### 9.2 Kopierte Notiz einfügen

Auf eine freie Stelle des Whiteboards:

1. **Rechtsklick** → Kontextmenü „📋 Einfügen“.
2. Klick auf „📋 Einfügen“:
   - Wenn eine Notiz im internen Clipboard vorhanden ist, wird eine **Kopie** am Maus-Position eingefügt:
     - Neue ID
     - Eigene Gruppe
     - Gleicher Inhalt, Bild, Farbe, Größe wie im Original.

---

## 10. Undo / Redo

Toolbar:

- **↩️-Button** → Undo (Schritt zurück)
- **↪️-Button** → Redo (Schritt vor)

Zusätzlich Tastatur:

- **Strg+Z** → Undo
- **Strg+Y** → Redo

Die History umfasst:
- Strukturänderungen an Notizen und Verbindungen (Erstellen, Löschen, Verschieben, Farbe, Textänderungen per Markdown-Speicher, Gruppierung).

---

## 11. Einstellungen

Toolbar:

- **⚙️-Button** → öffnet Einstellungsdialog.

Folgende Optionen:

### 11.1 Boardgröße

- **Breite (px)** – `boardW`
- **Höhe (px)** – `boardH`

Verändert die absolute Arbeitsfläche.

### 11.2 Post-it-Schrift

- **Post-it Schrift** (Zahl)  
  Standard-Schriftgröße für alle Notiztexte.

### 11.3 Markdown

- **Checkbox „Markdown“**  
  Ein/Aus für den Markdown-Modus aller Notizen.

### 11.4 Verbindungs-Standardwerte

- **Linien Dicke** – Standardstrichbreite für neue Verbindungen.
- **Linien Text** – Standardschriftgröße für neuen Verbindungstext.
- **„Verbinder Mehrzeilig“** – aktiviert mehrzeilige Textboxen an Verbindungen.

### 11.5 Speichern

- Button **„Speichern“** im Dialog:
  - Übernimmt Werte
  - Rendert alle Notizen/Verbindungen neu
  - Schließt den Dialog
  - Speichert in Local Storage

---

## 12. Board zurücksetzen

Toolbar:

- **🗑️-Button** („Alles löschen“).
- Sicherheitsabfrage „Sicher?“
- Danach wird das gesamte Board geleert:
  - Alle Notizen und Verbindungen entfernt.
  - Einstellungen bleiben erhalten.
  - Local Storage wird aktualisiert.

---

## 13. Speicherung im Browser

- Das Board speichert seinen Zustand zusätzlich automatisch in `localStorage` unter dem Schlüssel `wb_data_full_v3`.
- Beim Laden der Seite:
  - Falls vorhanden, wird dieser Zustand **automatisch geladen**.
- Speichervorgänge passieren z.B. bei:
  - Textänderungen
  - Farbänderungen
  - Erstellen/Löschen von Notizen/Verbindungen
  - Anwenden von Einstellungen

---

## 14. Tooltips

Viele Buttons haben kleine **Tooltips**, die beim Darüberfahren mit der Maus erscheinen, z.B.:

- „Alles speichern“
- „Alles laden“
- „Einzelne Notiz laden“
- „Einstellungen“
- „Undo (Strg+Z)“
- „Redo (Strg+Y)“
- „Bereich vergrößern“
- „Bild“
- „Kopieren“
- „Speichern“
- „Aus Gruppe lösen“
- „Neue Notiz“
- „Bibliothek“

---

## 15. Bekannte Einschränkungen / Hinweise

- Es gibt **keine Mehrbenutzer-Synchronisation** – alles läuft lokal im Browser.
- Die JSON-Dateien sind **nicht** gegen externe Manipulation geschützt; sie sind als Austausch-/Backupformat gedacht.
- Bilder werden als **Data-URLs** in den JSON-Dateien und im Local Storage gespeichert. Viele oder große Bilder können den Speicher belasten.
- Die Gruppierung basiert auf einer internen Gruppen-ID. Nach vielen Andock- und Lösevorgängen können Gruppen IDs inhaltlich „chaotisch“ sein – das ist rein intern und für den Nutzer normalerweise irrelevant.

---

## 16. Kurzübersicht – wichtigste Aktionen

- **Neue Notiz:** „+ Neue Notiz“
- **Notiz verschieben:** Kopfbereich ziehen
- **Farbe ändern:** Farbfeld im Header
- **Text schreiben:** Direkt ins Textfeld (oder Doppelklick bei Markdown)
- **Bild einfügen:** 📷 im Header oder Bild aus Zwischenablage in den Text
- **Verbindung erstellen:** Verbindungs-Handle ziehen und auf andere Notiz loslassen
- **Pfeil umschalten:** Auf Linie klicken
- **Verbindung bearbeiten/löschen:** Rechtsklick auf Linie
- **Notiz kopieren:** 📄 im Header
- **Notiz einfügen:** Rechtsklick auf Board → „📋 Einfügen“
- **Einzelne Notiz speichern:** 💾 im Header
- **Einzelne Notiz laden:** 📥 in Toolbar
- **Gesamtes Board speichern:** 💾 in Toolbar
- **Gesamtes Board laden:** 📂 in Toolbar
- **Einstellungen:** ⚙️
- **Undo/Redo:** ↩️ / ↪️ oder Strg+Z / Strg+Y
- **Bereichs-Zoom:** 🔍 aktivieren → Rechteck ziehen
- **Bibliothek:** 📚 öffnen → Ordner wählen → Mini-Notiz auf Board ziehen
- **Kette bilden:** Notiz an andere andocken (rechts/unten), dann bewegen sie sich zusammen
- **Aus Kette lösen:** 🔗 im Header der Notiz

Diese Hilfe bezieht sich auf die Version `post-it_v01.html` mit Ketten-/Auto-Docking-Funktion.# Notizzettel
Einfaches Whiteboard für Notizzettel
