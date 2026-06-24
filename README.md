# Home Assistant Dashboard Plugins

Eine Sammlung von Lovelace Custom Cards für Home Assistant,
entwickelt und gepflegt von [ppfeiffer](https://git.pfeiffer-privat.de/ppfeiffer).

Jedes Plugin ist ein eigenständiges Repository und kann unabhängig
über HACS oder manuell installiert werden.

---

## Verfügbare Plugins

| Plugin | Beschreibung | Forgejo | GitHub / HACS |
|--------|-------------|---------|-----------------|
| [SteelSeries Gauge Card](https://git.pfeiffer-privat.de/ppfeiffer/steelseries-gauge-addon) | Animierte Radial- und Linear-Gauges | [🔗](https://git.pfeiffer-privat.de/ppfeiffer/steelseries-gauge-addon) | [🔗](https://github.com/ppfeiffer63/steelseries-gauge-card) |
| [ChartJS Card](https://git.pfeiffer-privat.de/ppfeiffer/chartjs-card) | Linie & Balken Charts mit HA History API | [🔗](https://git.pfeiffer-privat.de/ppfeiffer/chartjs-card) | [🔗](https://github.com/ppfeiffer63/chartjs-card) |
| [Analytic Plot Card](https://git.pfeiffer-privat.de/ppfeiffer/analytic-plot-card) | Charts mit HA History API & Glassmorphism Design | [🔗](https://git.pfeiffer-privat.de/ppfeiffer/analytic-plot-card) | [🔗](https://github.com/ppfeiffer63/analytic-plot-card) |

---

## HACS Installation

**HACS → Frontend → ⋮ → Benutzerdefinierte Repositories**

| Plugin | GitHub URL | Kategorie |
|--------|-----------|-----------:|
| SteelSeries Gauge Card | `https://github.com/ppfeiffer63/steelseries-gauge-card` | Dashboard |
| ChartJS Card | `https://github.com/ppfeiffer63/chartjs-card` | Dashboard |
| Analytic Plot Card | `https://github.com/ppfeiffer63/analytic-plot-card` | Dashboard |

Nach dem Hinzufügen: **Home Assistant neuladen** (F5), dann sollte das Plugin unter **HACS → Frontend → Discover & Download** verfügbar sein.

---

## Plugin Features

### 🎨 SteelSeries Gauge Card
- **Type:** LitElement Web Component
- **Features:** Animierte Radial-Gauges, Linear-Gauges, Bargraphs
- **Design:** SteelSeries Design, individuell anpassbar
- **Daten:** Live entity values mit Update-Animation
- **Größen:** 150px - 500px+ responsiv

### 📊 ChartJS Card
- **Type:** LitElement Web Component
- **Features:** Line Charts, Bar Charts, Mixed Charts
- **Data:** Home Assistant History API (24h default)
- **Design:** Chart.js + Custom Styling
- **Responsiv:** Mobile, Tablet, Desktop

### 📈 Analytic Plot Card
- **Type:** LitElement 3 Web Component
- **Features:** History Charts mit Glassmorphism Design
- **Data:** HA History API (24h trend analysis)
- **Design:** Cyber-Blue + Glassmorphism, Dark Theme
- **Interactive:** Tooltips, Responsive Legend

---

## Installation (Manual)

Falls HACS nicht funktioniert oder du bevorzugst manuelle Installation:

```bash
# 1. Custom Cards Ordner erstellen
mkdir -p /config/www/community/<plugin-name>

# 2. JS-Datei herunterladen
# Von GitHub Release oder Forgejo Release

# 3. HA Web Interface
Settings → Dashboards → Resources
→ Create Resource
→ /local/community/<plugin-name>/<plugin>.js
→ Type: JavaScript Module

# 4. Home Assistant neuladen (F5)

# 5. Karte zum Dashboard hinzufügen
type: custom:<plugin-name>
```

---

## Konfiguration Beispiele

### SteelSeries Gauge Card
```yaml
type: custom:steelseries-gauge-card
entity: sensor.wohnzimmer_temperatur
gauge_type: radial
min: 0
max: 50
unit: °C
```

### ChartJS Card
```yaml
type: custom:chartjs-card
entity: sensor.wohnzimmer_temperatur
title: "Wohnzimmer Temperatur"
chart_type: line
```

### Analytic Plot Card
```yaml
type: custom:analytic-plot-card
entity: sensor.wohnzimmer_temperatur
title: "Wohnzimmer - 24h Trend"
name: "Temperatur"
```

---

## Beitragen

Bugs, Features oder Verbesserungen?

1. **Issue öffnen** im entsprechenden Repository
2. **Pull Request** erstellen
3. **Dokumentation** aktualisieren

Siehe [CONTRIBUTING.md](CONTRIBUTING.md) für Details.

---

## Support & Dokumentation

- **Forgejo:** Alle Repositories mit DOCS.md
- **GitHub:** README.md + Wiki
- **Home Assistant:** [Custom Cards Guide](https://developers.home-assistant.io/docs/frontend/custom-ui/)

---

## Lizenz

Alle Plugins sind **MIT License** - frei nutzbar, modifizierbar und verbreitbar.

---

## Roadmap

### SteelSeries Gauge Card
- v2.0.0: WebGL Rendering
- v1.5.0: Theme System

### ChartJS Card
- v1.5.0: Multi-Entity Support
- v2.0.0: Custom Themes

### Analytic Plot Card
- v1.1.0: Time Range Selector
- v1.2.0: Multi-Entity Support
- v1.3.0: Statistics (Min/Max/Avg)
- v2.0.0: WebGL + CSV Export

---

## Credits

Entwickelt mit ❤️ für die Home Assistant Community

**Maintainer:** [ppfeiffer](https://git.pfeiffer-privat.de/ppfeiffer)

**Community:** MeshDresden Developers

---

Made with 💪 by [ppfeiffer63](https://github.com/ppfeiffer63)
