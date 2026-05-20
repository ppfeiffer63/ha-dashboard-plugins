# Neues Plugin hinzufügen

## Repo-Struktur pro Plugin

```
<plugin-name>/
├── dist/
│   └── <plugin-name>.js      ← Haupt-Datei (HACS installiert diese)
├── hacs.json                 ← HACS-Metadaten
├── README.md                 ← Dokumentation
└── (optional: Installer-Addon für HA Supervisor)
```

## hacs.json Vorlage

```json
{
  "name": "Mein Plugin Name",
  "description": "Kurzbeschreibung",
  "content_in_root": false,
  "filename": "mein-plugin.js",
  "render_readme": true
}
```

## Namenskonvention

- Forgejo-Repo: `ppfeiffer/<plugin-name>` (z.B. `ppfeiffer/steelseries-gauge-addon`)
- GitHub-Repo:  `ppfeiffer63/<plugin-name>` (z.B. `ppfeiffer63/steelseries-gauge-card`)
- JS-Datei:     `<plugin-name>.js`
- Card-Typ:     `custom:<plugin-name>`

## Checkliste für neue Plugins

- [ ] Forgejo-Repo angelegt
- [ ] GitHub-Repo angelegt
- [ ] Push-Mirror Forgejo → GitHub eingerichtet
- [ ] `hacs.json` vorhanden
- [ ] `dist/<plugin-name>.js` vorhanden
- [ ] `README.md` mit YAML-Beispielen
- [ ] `window.customCards` Eintrag im JS
- [ ] Plugin in `README.md` dieses Index-Repos eingetragen
