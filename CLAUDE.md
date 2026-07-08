# CLAUDE.md — The Aurora Project website

Context voor Claude Code bij het bewerken van deze repo.

## Wat dit is

Statische website (één `index.html` + `assets/`) voor de band The Aurora Project.
Geen build-stap, geen framework — gewoon HTML/CSS/JS in één bestand.
Gehost op Netlify, gekoppeld aan GitHub. Elke push naar `main` = nieuwe deploy.

## Over de band

- Nederlandse progressive rock / metal band uit Katwijk, opgericht 1998.
- Label: FREIA Music. Website: https://www.theauroraproject.com
- Bezetting: Dennis Binnekade (zang), Remco van den Berg (gitaar/backings),
  Alex Ouwehand (gitaar/backings), Marcel 'Mox' Guijt (keys),
  Rob Krijgsman (bas), Joris Bol (drums).
- Nieuwste album: **EVOS12** (21 feb 2025), deel 1 van tweedelig concept.
- Eerdere albums: Unspoken Words (2005), Shadow Border (2009),
  Selling the Aggression (2013), World of Grey (2016).

## Huisstijl (kort)

Brutalist / stark richting: strak, hoog contrast, monospace + schreefloos.
Fonts op de site: **Archivo** (tekst) en **Space Mono** (accenten/mono).
Logo- en zon-assets staan in `assets/` (`logo_bone_hd.png`, `sun_bone.png`,
`sun_ink.png`). De volledige huisstijlgids-PDF's staan in de bovenliggende
projectmap, niet in deze repo.

## Werkafspraken

- Houd alles in één `index.html` tenzij het echt uit de hand loopt.
- Wijzig geen canonical/OG-URL's zonder reden (SEO).
- Afbeeldingen in `assets/`; comprimeer grote foto's voor het commit.
- Nederlands in commits en overleg; Engelse tekst op de site zelf blijft Engels.
