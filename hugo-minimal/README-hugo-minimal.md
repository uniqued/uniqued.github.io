# README - Hugo Portfolio Setup

Dieses Projekt ist eine minimal lauffähige Hugo-Basis für ein persönliches Portfolio mit den Bereichen **About**, **Work** und **Writing**.

## Voraussetzungen

Bevor du das Projekt lokal startest, brauchst du:

- **Hugo Extended**
- optional **Git**
- einen Code-Editor wie VS Code

### Hugo installieren

Die aktuelle Installationsanleitung findest du hier:

- https://gohugo.io/installation/

Prüfe danach, ob Hugo verfügbar ist:

```bash
hugo version
```

## Projekt lokal starten

1. ZIP-Datei entpacken
2. im Terminal in den Projektordner wechseln
3. lokalen Entwicklungsserver starten

```bash
cd hugo-minimal
hugo server
```

Danach ist die Website lokal erreichbar unter:

```text
http://localhost:1313/
```

Wenn du Draft-Inhalte sehen willst:

```bash
hugo server -D
```

## Produktionsbuild erzeugen

Um die statische Website zu bauen:

```bash
hugo
```

Die generierten Dateien liegen danach im Ordner:

```text
public/
```

## Projektstruktur

```text
hugo-minimal/
├── hugo.toml
├── archetypes/
├── assets/
│   └── css/
├── content/
│   ├── about/
│   ├── work/
│   └── writing/
└── layouts/
    ├── _default/
    └── partials/
```

## Inhalte pflegen

### Menü bearbeiten

Das Hauptmenü konfigurierst du in:

```text
hugo.toml
```

Dort findest du den Abschnitt:

```toml
[menus]
  [[menus.main]]
```

Hier kannst du Menüpunkte hinzufügen, entfernen oder umsortieren.

### Startseiten-Statement bearbeiten

Das große Statement auf der Startseite pflegst du ebenfalls in:

```text
hugo.toml
```

Relevant sind diese Felder:

```toml
[params.hero]
  eyebrow = "UX Consulting"
  title = "..."
  intro = "..."
  primaryCtaLabel = "..."
  primaryCtaUrl = "..."
  secondaryCtaLabel = "..."
  secondaryCtaUrl = "..."
```

### Featured-Inhalte auf der Startseite steuern

Die Startseite zeigt aktuell **ausgewählte Projekte** und **ausgewählte Artikel**.

Das steuerst du in den jeweiligen Markdown-Dateien über:

```yaml
featured: true
```

Wenn ein Inhalt nicht auf der Startseite erscheinen soll:

```yaml
featured: false
```

### Neue Projekte anlegen

Neue Projekte kommen in den Ordner:

```text
content/work/
```

Am einfachsten mit Hugo Archetype:

```bash
hugo new work/neues-projekt.md
```

### Neue Artikel anlegen

Neue Artikel kommen in den Ordner:

```text
content/writing/
```

Mit Archetype:

```bash
hugo new writing/neuer-artikel.md
```

## Front Matter

### Beispiel für Work

```yaml
---
title: "Projektname"
date: 2026-07-16
summary: "Kurze Zusammenfassung"
industry: "Öffentlicher Sektor"
client: "Kundenname"
role: "UX Consultant"
team: "Teamkontext"
project_type: "Redesign"
methods:
  - Workshop
  - Research
  - Wireframing
tags:
  - UX
  - Service Design
featured: true
---
```

### Beispiel für Writing

```yaml
---
title: "Artikeltitel"
date: 2026-07-16
summary: "Kurze Zusammenfassung"
tags:
  - UX
categories:
  - Essay
featured: true
---
```

## Styling anpassen

Das Styling liegt in:

```text
assets/css/main.css
```

Dort kannst du unter anderem anpassen:

- Farben
- Typografie
- Kartenlayout
- Header
- Hero-Bereich
- Abstände

## Wichtige Dateien

- `hugo.toml` - zentrale Konfiguration
- `content/about/_index.md` - About-Seite
- `content/work/` - Projekte
- `content/writing/` - Artikel
- `layouts/index.html` - Startseite
- `layouts/partials/` - wiederverwendbare Template-Bausteine
- `assets/css/main.css` - Design und Layout

## Deployment

Du kannst das Projekt später z. B. deployen auf:

- Netlify
- Vercel
- GitHub Pages
- Cloudflare Pages

Für die meisten Hosting-Plattformen reicht als Build-Command:

```bash
hugo
```

und als Publish-Verzeichnis:

```text
public
```

## Nächste sinnvolle Schritte

Wenn du das Projekt weiterentwickeln willst, sind diese Erweiterungen sinnvoll:

1. Impressum und Datenschutz ergänzen
2. Social Links im Footer hinzufügen
3. Cover-Bilder für Work und Writing ergänzen
4. Tags und Kategorien als Filterseiten ausbauen
5. SEO und Open Graph Metadaten ergänzen
6. Mehrsprachigkeit vorbereiten

## Kurzworkflow für den Alltag

```bash
# lokalen Server starten
hugo server

# neues Projekt anlegen
hugo new work/neues-projekt.md

# neuen Artikel anlegen
hugo new writing/neuer-artikel.md

# Produktionsbuild erzeugen
hugo
```

Wenn du möchtest, kann ich dir als Nächstes auch noch ein **technisch sauberes README direkt für das Projekt selbst** formulieren - also etwas knapper und repository-tauglich.