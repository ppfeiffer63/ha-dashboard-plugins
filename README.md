# Home Assistant Dashboard Plugins

Eine Sammlung von Lovelace Custom Cards für Home Assistant,
entwickelt und gepflegt von [ppfeiffer](https://git.pfeiffer-privat.de/ppfeiffer).

Jedes Plugin ist ein eigenständiges Repository und kann unabhängig
über HACS oder manuell installiert werden.

---

## Verfügbare Plugins

| Plugin | Beschreibung | Forgejo | GitHub / HACS |
|--------|-------------|---------|---------------|
| [SteelSeries Gauge Card](https://git.pfeiffer-privat.de/ppfeiffer/steelseries-gauge-addon) | Animierte Radial- und Linear-Gauges (SteelSeries Canvas) | [🔗](https://git.pfeiffer-privat.de/ppfeiffer/steelseries-gauge-addon) | [🔗](https://github.com/ppfeiffer63/steelseries-gauge-card) |

---

## HACS Installation

Jedes Plugin kann einzeln über HACS als benutzerdefiniertes Repository hinzugefügt werden:

**HACS → Frontend → ⋮ → Benutzerdefinierte Repositories**

| Plugin | GitHub URL | Kategorie |
|--------|-----------|-----------|
| SteelSeries Gauge Card | `https://github.com/ppfeiffer63/steelseries-gauge-card` | Dashboard |

---

## Manuelle Installation

1. Die `dist/<plugin-name>.js` Datei aus dem jeweiligen Repository herunterladen
2. Nach `/config/www/` kopieren
3. In HA unter **Einstellungen → Dashboards → ⋮ → Ressourcen** eintragen:
   - URL: `/local/<plugin-name>.js`
   - Typ: `JavaScript-Modul`

---

## Neues Plugin vorschlagen

Issue im jeweiligen Repository oder direkt hier öffnen.
