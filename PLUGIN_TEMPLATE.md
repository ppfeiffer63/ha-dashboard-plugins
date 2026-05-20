# Plugin-Vorlage: hacs.json

Kopiere diese Datei in das neue Plugin-Repo und passe die Werte an.

```json
{
  "name": "PLUGIN NAME",
  "description": "KURZBESCHREIBUNG",
  "content_in_root": false,
  "filename": "PLUGIN-NAME.js",
  "render_readme": true
}
```

# Plugin-Vorlage: JS-Grundstruktur

```javascript
/**
 * PLUGIN NAME - Home Assistant Lovelace Custom Card
 */

class MyPluginCard extends HTMLElement {
  constructor() {
    super();
    this.attachShadow({ mode: "open" });
  }

  static getConfigElement() {
    return document.createElement("my-plugin-card-editor");
  }

  static getStubConfig() {
    return { entity: "sensor.example" };
  }

  setConfig(config) {
    if (!config.entity) throw new Error("'entity' ist erforderlich.");
    this._config = config;
  }

  set hass(hass) {
    this._hass = hass;
    this._render();
  }

  _render() {
    const stateObj = this._hass?.states[this._config?.entity];
    this.shadowRoot.innerHTML = `
      <ha-card>
        <div>${stateObj?.state ?? "–"}</div>
      </ha-card>`;
  }

  getCardSize() { return 1; }
}

customElements.define("my-plugin-card", MyPluginCard);

window.customCards = window.customCards || [];
window.customCards.push({
  type:        "my-plugin-card",
  name:        "My Plugin Card",
  description: "Beschreibung",
  preview:     false,
});
```
