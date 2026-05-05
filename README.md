# LiftLog — Installatie als Telefoon App via GitHub

## Wat je nodig hebt (alles gratis)
- **GitHub** account → github.com
- **Supabase** account → supabase.com (voor gedeeld geheugen)

---

## Stap 1 — Supabase database aanmaken

1. Ga naar **supabase.com** → gratis account aanmaken
2. Klik **"New project"** → naam bijv. "liftlog" → wacht ~1 minuut
3. Ga naar **SQL Editor** → plak dit en klik **Run**:

```sql
CREATE TABLE liftlog (
  key TEXT PRIMARY KEY,
  value TEXT NOT NULL,
  updated_at TIMESTAMPTZ DEFAULT NOW()
);

ALTER TABLE liftlog ENABLE ROW LEVEL SECURITY;

CREATE POLICY "open_access" ON liftlog FOR ALL USING (true) WITH CHECK (true);
```

4. Ga naar **Settings → API** → kopieer:
   - **Project URL** (bijv. `https://abcxyz.supabase.co`)
   - **anon / public key**

---

## Stap 2 — App configureren

Open `index.html` in een teksteditor en zoek deze 2 regels:

```js
const SUPABASE_URL = "JOUW_SUPABASE_URL";
const SUPABASE_KEY = "JOUW_SUPABASE_KEY";
```

Vervang ze met jouw gegevens en sla op.

---

## Stap 3 — Op GitHub zetten

1. Ga naar **github.com** → maak gratis account
2. Klik op **"+"** rechtsboven → **"New repository"**
3. Naam: `liftlog` → zet op **Public** → klik **"Create repository"**
4. Klik op **"uploading an existing file"**
5. Sleep alle 4 bestanden erin:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon.svg`
6. Klik **"Commit changes"**

---

## Stap 4 — GitHub Pages aanzetten

1. In je repository → klik op **"Settings"** tab
2. Links in het menu → klik op **"Pages"**
3. Onder "Branch" → kies **main** → klik **Save**
4. Wacht ~1 minuut
5. Je app staat nu live op: `https://JOUW-GEBRUIKERSNAAM.github.io/liftlog`

---

## Stap 5 — App installeren op telefoon

**iPhone (Safari):**
1. Open de link in **Safari** (niet Chrome)
2. Tik het **deel-icoon** (vierkantje met pijl omhoog)
3. Scroll naar beneden → **"Zet op beginscherm"**
4. Tik **"Voeg toe"** → klaar!

**Android (Chrome):**
1. Open de link in **Chrome**
2. Tik de **drie puntjes** rechtsboven
3. Tik **"App installeren"** of **"Toevoegen aan startscherm"**
4. Klaar!

---

## Vrienden laten joinen

Stuur ze gewoon de link: `https://JOUW-GEBRUIKERSNAAM.github.io/liftlog`

Ze openen hem in de browser, installeren hem als app, en maken een eigen profiel aan. Omdat alles via Supabase gaat, zien jullie elkaars Battle stats direct!

---

## Kosten overzicht

| Service | Prijs |
|---|---|
| GitHub Pages | **Gratis** |
| Supabase (tot 500MB) | **Gratis** |
| **Totaal** | **€0/maand** |

Met 5 personen die dagelijks trainen: ~9MB/jaar → je zit nog **55 jaar** binnen de gratis grens.
