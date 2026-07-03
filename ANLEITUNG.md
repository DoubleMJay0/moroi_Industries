# MOROI Industries — Setup-Anleitung

Alles kostenlos. Zwei Schritte: Formular-Backend, dann Hosting.

## 1. Formspree einrichten (Bewerbungs-Speicherung)

1. Kostenlosen Account auf https://formspree.io anlegen (Free-Tier: 50 Einsendungen/Monat — reicht für eine Gruppe locker).
2. **New Form** → Name z. B. „MOROI Applications". Als Empfänger-Adresse deine E-Mail.
3. Formspree zeigt dir einen Endpoint wie `https://formspree.io/f/abcdwxyz`.
4. In `index.html` ganz unten im `<script>`-Block eintragen:

   ```js
   const FORMSPREE_ENDPOINT = "https://formspree.io/f/abcdwxyz";
   ```

Jede Bewerbung landet dann als E-Mail bei dir **und** im Formspree-Dashboard (dort als Tabelle exportierbar). Das Foto kommt als Base64-String mit (`photo_base64`) — den String kannst du in die Adresszeile des Browsers kopieren oder auf https://base64.guru/converter/decode/image einfügen, um das Bild zu sehen. Die Seite verkleinert Fotos automatisch auf max. 480 px, damit das Limit nicht reißt.

**Fallback:** Solange der Endpoint leer ist, öffnet „Submit Application" stattdessen eine fertig ausgefüllte E-Mail an dich (martin.jendrusch@gmail.com) — funktioniert also auch ganz ohne Formspree, nur ohne Foto.

## 2. Auf GitHub Pages hosten

1. Neues öffentliches Repo anlegen, z. B. `moroi-industries`.
2. `index.html` ins Repo (Web-Upload reicht: **Add file → Upload files**).
3. Repo → **Settings → Pages** → Source: `Deploy from a branch`, Branch `main`, Ordner `/ (root)` → Save.
4. Nach ~1 Minute ist die Seite live unter
   `https://DEIN-USERNAME.github.io/moroi-industries/`

## Was die Seite kann

- Corporate-Landing-Page (Company, Facility DECAGONE, Careers) — spoilerfrei, reines Flavour.
- Bewerbungsformular = Mothership-Charaktererstellung: Foto (ID-Badge-Look), Name, Pronomen, Geschlecht (inkl. Android), Klasse, Stats/Saves/Health/Credits mit eingebautem Würfel-Tool (2D10+25 etc., Klassen-Modifikatoren werden automatisch verrechnet), Skill-Auswahl nach Klassenregeln, Trinket/Patch/Loadout, Personal Statement.
- Anpassen: Farben oben in `:root`, Texte direkt im HTML. `WARDEN_EMAIL` im Script bei Bedarf ändern.
