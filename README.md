# Familien-Werkstatt · Family Workshop

Kleine interaktive Webseiten, die Eltern zusammen mit ihren Kindern durchspielen können — eine pro Thema. Astronomie, Physik, Sprache, Geschichte, was gerade kommt.

Small interactive pages parents can play through with their kids — one per topic. Astronomy, physics, language, history, whatever comes up next.

🌐 **Live**: https://rangulvers.github.io/familien-werkstatt/

## Wie ist das aufgebaut?

Jedes Projekt ist ein eigener Ordner mit einer `index.html` und einer `meta.json`. Die Landing-Seite liest alle `meta.json`-Dateien zur Laufzeit ein und baut daraus einen suchbaren Katalog. Pure HTML/CSS/JS, kein Build-Step.

Each project lives in its own folder containing an `index.html` and a `meta.json`. The landing page reads every `meta.json` at runtime and turns them into a searchable catalog. Pure HTML/CSS/JS — no build step.

```
.
├── index.html              ← landing with search
├── projects.json           ← auto-generated index of all projects
├── assets/
│   ├── style.css
│   └── search.js
├── ekliptik/               ← one project per folder
│   ├── index.html
│   └── meta.json
└── .github/workflows/
    └── build-index.yml     ← regenerates projects.json on push
```

## Neues Projekt hinzufügen / Adding a new project

1. Ordner anlegen, z. B. `papierflieger/`.
2. `index.html` mit dem fertigen Lerninhalt reinlegen (alle Pfade relativ — keine Annahmen über die URL).
3. `meta.json` daneben:

```json
{
  "title": "Wie fliegen Papierflieger?",
  "summary": "Auftrieb, Schwerkraft und ein Faltvorlagen-Generator. Mit Mess-Schleuder.",
  "tags": ["physik", "experiment"],
  "ages": ["6-8", "9-12"],
  "subjects": ["physik"],
  "language": "de",
  "created_at": "2026-05-04"
}
```

4. Push auf `main`. Die Action regeneriert `projects.json` und GitHub Pages deployt in unter einer Minute.

## Lizenz / License

[MIT](./LICENSE). Du darfst das ganze Repo forken, einzelne Projekte adaptieren oder eigene beisteuern. Pull-Requests willkommen.

[MIT](./LICENSE). Fork the whole repo, adapt individual projects, or contribute your own. Pull requests welcome.
