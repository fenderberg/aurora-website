# The Aurora Project — Website

Statische website voor de Nederlandse progressive rock band The Aurora Project.
Eén pagina (`index.html`) met bijbehorende `assets/`.

## Lokaal bekijken

Open `index.html` direct in de browser, of start een simpele webserver:

```bash
python3 -m http.server 8000
# open daarna http://localhost:8000
```

## Deploy

De site wordt automatisch naar Netlify gepubliceerd bij elke push naar de
`main`-branch op GitHub. Configuratie staat in `netlify.toml`.

## Structuur

```
index.html        # de volledige pagina
assets/           # afbeeldingen, logo's, albumcovers
netlify.toml      # Netlify build/deploy-config
CLAUDE.md         # context voor Claude Code
```
