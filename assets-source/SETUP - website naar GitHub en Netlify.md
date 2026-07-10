# Website → Claude Code → GitHub → Netlify

Stappenplan om de website van The Aurora Project te bewerken in Claude Code,
te versiebeheren op GitHub en automatisch te hosten via Netlify — zodat je
'm op elke laptop kunt onderhouden.

De repo is de map:
`...\The aurora project\website\`
(alleen `index.html` + `assets/` + de config die ik heb toegevoegd)

---

## Wat ik al voor je heb klaargezet (in `website/`)

- `.gitignore` — houdt rommel (OS-bestanden, node_modules) uit de repo
- `netlify.toml` — vertelt Netlify hoe te publiceren (statische site)
- `README.md` — korte uitleg over de site
- `CLAUDE.md` — context over band + huisstijl, zodat Claude Code de repo snapt

---

## Eenmalig: benodigdheden

1. **Git** geïnstalleerd? Test in een terminal: `git --version`.
   Zo niet: download via https://git-scm.com/download/win
2. **GitHub-account** — maak er gratis een op https://github.com als je die nog niet hebt.
3. **Netlify-account** — https://app.netlify.com — log in met je GitHub-account (makkelijkst).

---

## Stap 1 — Open de map in Claude Code

Open een terminal en start Claude Code in de website-map:

```bash
cd "C:\Users\RemcovandenBerg\OneDrive - QSBN\Documenten\Claude\Projects\The aurora project\website"
claude
```

Claude Code leest automatisch `CLAUDE.md` en kent dan de context.

---

## Stap 2 — Git initialiseren

> Er staat mogelijk een half-aangemaakte `.git`-map van mij in. Verwijder die
> eerst (Verkenner: verborgen bestanden tonen → map `.git` weggooien), of via terminal:
> `rmdir /s /q .git`  (in de website-map)

Daarna, in dezelfde map:

```bash
git init
git branch -M main
git add .
git commit -m "Eerste commit: The Aurora Project website"
```

---

## Stap 3 — Naar GitHub pushen

1. Maak op https://github.com/new een **nieuwe repo** aan, bijv. `aurora-website`.
   - Laat 'm **leeg** (geen README/gitignore aanvinken — die heb je al).
   - Public of Private mag allebei; Netlify werkt met beide.
2. GitHub toont daarna de push-commando's. Gebruik deze (vervang `<jouw-gebruikersnaam>`):

```bash
git remote add origin https://github.com/<jouw-gebruikersnaam>/aurora-website.git
git push -u origin main
```

De eerste keer vraagt Git om in te loggen op GitHub — volg de browser-prompt.

---

## Stap 4 — Netlify koppelen

1. Ga naar https://app.netlify.com → **Add new site** → **Import an existing project**.
2. Kies **GitHub** en selecteer je repo `aurora-website`.
3. Build-instellingen (Netlify leest `netlify.toml`, dus meestal automatisch goed):
   - **Build command:** leeg laten
   - **Publish directory:** `.` (punt)
4. Klik **Deploy**. Binnen een minuut staat je site live op een
   `random-naam.netlify.app`-adres.

### Eigen domein (theauroraproject.com)
In Netlify → **Domain settings** → **Add a domain** kun je later
`www.theauroraproject.com` koppelen. Dat vereist DNS-wijzigingen bij je
domeinprovider — laat het me weten wanneer je zover bent, dan help ik daarmee.

---

## Vanaf nu: wijzigen en publiceren

Elke keer dat je iets aanpast (zelf of via Claude Code):

```bash
git add .
git commit -m "korte beschrijving van de wijziging"
git push
```

Netlify pakt de push automatisch op en publiceert de nieuwe versie. Klaar.

---

## Op je andere laptop werken

Eenmalig op de tweede laptop (Git + Claude Code geïnstalleerd):

```bash
git clone https://github.com/<jouw-gebruikersnaam>/aurora-website.git
cd aurora-website
claude
```

Daarna werk je hetzelfde: `git pull` om het laatste op te halen voordat je
begint, en `git add . && git commit -m "..." && git push` als je klaar bent.

> Tip: werk niet meer vanuit de OneDrive-map als je met GitHub gaat werken —
> GitHub is nu je "waarheid". Zet de repo op beide laptops via `git clone` op
> een gewone map (bijv. `C:\dev\aurora-website`), niet in OneDrive, om
> sync-conflicten te voorkomen.
