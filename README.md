# 🏠 Dashboard Modern per Home Assistant

![Version](https://img.shields.io/github/v/release/danigio15/dashboardmodern?label=version&color=blue)
![HACS](https://img.shields.io/badge/HACS-custom-41BDF5?logo=homeassistant&logoColor=white)
![HA](https://img.shields.io/badge/Home%20Assistant-2024.6%2B-41BDF5?logo=homeassistant&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)

Dashboard HTML **standalone** per Home Assistant: un singolo file, zero card custom richieste, design moderno "sculpted", **configurazione 100% da interfaccia** e **tema chiaro/scuro/auto**.

> 📸 *Screenshot in `screenshots/`*

## ✨ Caratteristiche

- **🧙 Setup Wizard al primo avvio** — token (verificato live), nome casa, sezioni, luci lette dal tuo HA con checkbox. Zero file da editare.
- **📑 Configuratore per sezione** — ogni entità presentata con etichetta umana ("Produzione solare oggi") e autocomplete sulle TUE entità
- **🌡️ Stanze dinamiche** — aggiungi/rimuovi le card temperatura da UI (nome, icona, sensori)
- **🎨 Tema chiaro / scuro / auto** — dark mode completo, Auto segue il dispositivo in tempo reale
- **📑 8 sezioni attivabili**: Home · Energia (flussi FV animati, analisi) · Auto elettrica (EVCC) · Solare termico · Clima · Stanze · Sicurezza (Frigate) · MiniPC
- **💡 Gestione luci** raggruppata per stanza con card luminose
- **🧩 Editor visuale** (pagina ⚙️ riservata agli admin): sostituzioni, carichi, avvisi, testi, visibilità
- **⚡ Tempo reale** WebSocket · **📱 Mobile-first**

## 📦 Installazione via HACS (consigliata)

1. **HACS → menu ⋮ → Repository personalizzati** → aggiungi:
   ```
   https://github.com/danigio15/dashboardmodern
   ```
   Categoria: **Dashboard** (Frontend/Plugin)

2. **Installa** "Dashboard Modern" da HACS e riavvia il browser (Ctrl+Shift+R)

3. **Crea la dashboard**: *Impostazioni → Dashboard → Aggiungi* → vista **Pannello** → card **Iframe**:
   ```
   /hacsfiles/dashboardmodern/dashboard.html
   ```

4. **Aprila**: parte il **Setup Wizard** → configuri tutto da UI

5. **Aggiornamenti**: arrivano da HACS come per qualsiasi componente. La tua configurazione **sopravvive agli update** (vive nel browser e/o nel file config esterno, mai nella cartella HACS).

<details>
<summary>💾 Rendere la configurazione multi-dispositivo (con HACS)</summary>

La config del wizard/editor è salvata per browser. Per condividerla tra dispositivi:

**Opzione A — Export/Import**: ⚙️ Configurazione → Configura Entità → 📤 Esporta → "Copia configurazione" → sull'altro dispositivo "Importa".

**Opzione B — Config esterno**: crea `/config/www/casa-dashboard-config.js` (FUORI dalla cartella HACS, sopravvive agli update) partendo da [`config.example.js`](config.example.js). La dashboard lo carica automaticamente da `/local/casa-dashboard-config.js`.

⚠️ Con HACS **non usare** "Scarica HTML modificato": l'update HACS sovrascriverebbe il file. Quel flusso è per le installazioni manuali.
</details>

<details>
<summary>📁 Installazione manuale (alternativa senza HACS)</summary>

1. Scarica `dashboard.html` dall'ultima [release](../../releases)
2. Copialo in `/config/www/dashboards/`
3. Card Iframe → `/local/dashboards/dashboard.html`
4. Con l'installazione manuale puoi usare "⬇ Scarica HTML modificato" per integrare la config nel file.
</details>

<details>
<summary>🖥️ Modalità kiosk (facoltativa)</summary>

Con [kiosk-mode](https://github.com/NemesisRE/kiosk-mode):
```yaml
kiosk_mode:
  hide_header: true
```
Il pulsante "Editor Plancia" (pagina ⚙️) riapre la vista con `?disable_km=`.
</details>

## ⚙️ Personalizzazione

| Cosa | Dove |
|---|---|
| Entità di ogni sezione (etichette umane + autocomplete) | ⚙️ Configurazione → Configura Entità → 📑 Sezioni |
| Stanze temperatura (aggiungi/rimuovi) | → 📑 Sezioni → 🌡️ Stanze |
| Sostituire un sensore ovunque | → 🔁 Sostituzioni |
| Carichi (popup Cucina/Lavanderia) · Avvisi | → 🔌 / 🔔 |
| Rinominare etichette · Nascondere card | → ✏️ / 👁️ |
| Tema chiaro/scuro/auto | ⚙️ Configurazione → 🎨 Tema |
| Rifare il setup | → 📤 Esporta → Riapri Setup Wizard |

Le entità non configurate mostrano "—" senza errori.

## 👤 Amministratori

La pagina ⚙️ Configurazione è visibile solo agli admin (impostati nel wizard o `admin_users` nel config). Lista vuota = visibile a tutti.

## 🔒 Sicurezza

- Il token dà pieno accesso al tuo HA: trattalo come una password
- Mai committare `config.js`/`casa-dashboard-config.js` su repo pubblici
- Token esposto? Revocalo dal profilo HA

## 📄 Licenza

[MIT](LICENSE) · Sviluppata da Giovanni D'Aniello con l'aiuto di Claude (Anthropic) · Grafici [Chart.js](https://www.chartjs.org/)
