# 🏠 Dashboard Modern per Home Assistant

![Version](https://img.shields.io/github/v/release/danigio15/dashboardmodern?label=version&color=blue)
![HACS](https://img.shields.io/badge/HACS-custom-41BDF5?logo=homeassistant&logoColor=white)
![HA](https://img.shields.io/badge/Home%20Assistant-2024.6%2B-41BDF5?logo=homeassistant&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)
![Mobile](https://img.shields.io/badge/mobile-first-orange)
[![Dona](https://img.shields.io/badge/PayPal-Offrimi%20un%20caff%C3%A8%20☕-00457C?logo=paypal&logoColor=white)](https://paypal.me/giovannidaniello15)

Dashboard HTML **standalone** per Home Assistant: un singolo file, nessuna card custom richiesta, design moderno "sculpted", **configurazione 100% da interfaccia** con setup guidato, tema chiaro/scuro/auto e **aggiornamenti automatici**.

![Home della dashboard](screenshots/home-light.png)

---

## ✨ Caratteristiche

| | |
|---|---|
| 🧙 **Setup Wizard** | Al primo avvio ti guida in 6 passi: token (verificato in tempo reale), nome casa, sezioni, luci, entità, telecamere. Zero file da modificare. |
| 📑 **8 sezioni attivabili** | Home · Energia · Auto elettrica · Solare termico · Clima · Stanze · Sicurezza · Server — attivi solo quelle che ti servono, **rinominabili** a piacere |
| 🧩 **Tutte le entità configurabili** | Oltre 100 punti dati presentati con etichette chiare ("Produzione solare oggi") e **autocomplete** sulle tue entità |
| 👻 **Auto-pulizia** | Ciò che non configuri **sparisce**: card, azioni e sezioni vuote non vengono mostrate |
| ➕ **Elementi illimitati** | Luci, stanze (temperatura/umidità), telecamere, unità clima (condizionatori e termosifoni) e azioni rapide: aggiungi e rimuovi quante ne vuoi |
| 🎨 **Tema chiaro / scuro / auto** | Dark mode completo; in Auto segue il tema del dispositivo in tempo reale |
| 🔄 **Aggiornamenti automatici** | Dopo un update HACS la dashboard rileva la nuova versione e **si ricarica da sola** — l'URL della plancia non cambia mai |
| ⚡ **Tempo reale** | WebSocket nativo Home Assistant, grafici storici a popup per ogni sensore |
| 📱 **Mobile-first** | Bottom-nav, safe-area iOS, vibrazione tattile, layout responsive |
| 👤 **Multi-utente** | La pagina di configurazione è visibile solo agli amministratori che scegli |

---

## 📦 Installazione via HACS (consigliata)

1. **HACS → menu ⋮ → Repository personalizzati** e aggiungi:
   ```
   https://github.com/danigio15/dashboardmodern
   ```
   Categoria: **Dashboard**

2. Cerca **"Dashboard Modern"** → **Scarica**

3. **Crea la plancia**: *Impostazioni → Dashboard → Aggiungi dashboard* → vista di tipo **Pannello** → aggiungi una card **Iframe** (Pagina web) con URL:
   ```
   /hacsfiles/dashboardmodern/dashboard.html
   ```

4. **Aprila**: parte automaticamente il Setup Wizard 👇

<details>
<summary>📁 Installazione manuale (senza HACS)</summary>

1. Scarica `dashboard.html` dall'ultima [release](../../releases)
2. Copialo in `/config/www/dashboards/` (File Editor o Samba)
3. Card Iframe con URL `/local/dashboards/dashboard.html`
4. Con l'installazione manuale puoi anche usare *Esporta → Scarica HTML modificato* per integrare la configurazione nel file.
</details>

---

## 🧙 Il Setup Wizard

![Setup Wizard](screenshots/wizard-connessione.png)

Al primo avvio (o quando vuoi: **7 tap veloci sul titolo** in alto nella Home) si apre la configurazione guidata:

1. **🔌 Connessione** — istruzioni per creare il token, verifica live della connessione, URL remoto facoltativo (Nabu Casa)
2. **🏠 Nome** — nome della casa, sottotitolo e utente amministratore
3. **📑 Sezioni** — attiva solo quelle che ti servono e **rinominale** (es. "Auto" → "Tesla")
4. **💡 Luci** — lette automaticamente dal tuo HA, selezionale con un tap e rinominale nel formato *"Stanza - Dettaglio"* per il raggruppamento automatico
5. **🧩 Entità** — per ogni sezione attiva, collega le tue entità con l'autocomplete. Qui aggiungi anche **stanze**, **unità clima**, **telecamere**, **azioni rapide** e l'**immagine dell'auto**
6. **🎉 Fine** — salva e avvia

![Selezione luci](screenshots/wizard-luci.png)

> 💡 Puoi saltare qualsiasi passo e completarlo in seguito: tutto è modificabile da **⚙️ Config → Configura Entità**.

---

## ⚙️ La pagina Configurazione

![Pagina configurazione](screenshots/config-page.png)

Visibile **solo agli amministratori** (impostati nel wizard), dal menu ⚙️:

| Card | Cosa fa |
|---|---|
| 🧙 **Setup Wizard** | Riapre la configurazione guidata completa |
| 🧩 **Configura Entità** | Editor avanzato a schede (vedi sotto) |
| 🎨 **Tema** | Chiaro / Scuro / Auto (segue il dispositivo) |

### L'editor Configura Entità

| Scheda | Cosa gestisce |
|---|---|
| 📑 **Sezioni** | Tutte le entità di ogni sezione + stanze, unità clima, telecamere, azioni rapide, immagine auto |
| 🔁 **Sostituzioni** | Rimappa qualsiasi entità ovunque (per utenti esperti) |
| 🔌 **Carichi** | Aggiungi elettrodomestici ai popup Cucina/Lavanderia |
| 🔔 **Avvisi** | Gestisci il Quadro Avvisi: aperture, batterie — aggiungi e **rimuovi** qualsiasi voce |
| ✏️ **Testi** | Rinomina qualsiasi etichetta della dashboard |
| 👁️ **Nascondi** | Nascondi singole card o blocchi |
| 📤 **Esporta** | Copia/importa la configurazione tra dispositivi, reset, riapri il wizard |

![Editor sezioni](screenshots/editor-sezioni.png)

---

## 🖼️ Le sezioni

![Sezione energia](screenshots/energia.png)

- **🏠 Home** — meteo, quadro avvisi (aperture/batterie), stato allarme, azioni rapide personalizzabili
- **⚡ Energia** — flussi fotovoltaico animati, produzione/consumo/batteria/rete, analisi giornaliera-mensile-annuale, costi e risparmi
- **🚗 Auto elettrica** — batteria, autonomia, sessione di ricarica, wallbox, modalità EVCC, **immagine personalizzabile**
- **🌡️ Stanze** — card temperatura/umidità illimitate con storici
- **❄️ Clima** — condizionatori e termosifoni illimitati con controlli e popup dettagliato
- **🌞 Solare termico** — boiler, sonde, pompa
- **🛡️ Sicurezza** — telecamere illimitate (snapshot + live WebRTC/go2rtc), centrale allarme
- **🖥️ Server** — CPU/RAM/disco/temperatura, speedtest, connettività

![Tema scuro](screenshots/home-dark.png)

---

## 🔄 Aggiornamenti

Gli update arrivano da **HACS** come per qualsiasi componente. Al primo avvio dopo l'update, la dashboard **rileva la nuova versione e si ricarica da sola** (controllo all'apertura e ogni 6 ore per le plance sempre accese). Non devi mai cambiare l'URL della plancia.

La tua configurazione **sopravvive sempre agli aggiornamenti**: vive nel browser del dispositivo, mai nella cartella HACS.

<details>
<summary>💾 Configurazione multi-dispositivo</summary>

La config è salvata per browser. Per condividerla:

**Opzione A — Export/Import:** ⚙️ Config → Configura Entità → 📤 Esporta → *Copia configurazione* → sull'altro dispositivo *Importa*.

**Opzione B — Config esterno:** crea `/config/www/casa-dashboard-config.js` partendo da [`config.example.js`](config.example.js) — è fuori dalla cartella HACS e sopravvive agli update.
</details>

---

## 🆘 Accessi di emergenza

| Metodo | Come |
|---|---|
| **7 tap** | Tocca rapidamente 7 volte il titolo in alto nella Home → si apre il wizard (vibra al 5° tap) |
| **#setup** | Aggiungi `#setup` all'URL della dashboard e ricarica |
| **Reset totale** | In fondo al wizard: cancella tutta la configurazione del dispositivo |

---

## 🔒 Sicurezza

- Il token a lunga scadenza dà pieno accesso al tuo HA: **trattalo come una password**
- Mai committare `config.js` / `casa-dashboard-config.js` su repository pubblici
- Token esposto? Revocalo subito dal profilo HA
- Il file distribuito non contiene credenziali né dati di alcuna installazione

## ☕ Supporta il progetto

Dashboard Modern è gratuita e open source, sviluppata nel tempo libero. Se ti è utile e vuoi supportare lo sviluppo di nuove funzionalità, puoi offrirmi un caffè:

[![PayPal](https://img.shields.io/badge/Dona%20con-PayPal-00457C?logo=paypal&logoColor=white&style=for-the-badge)](https://paypal.me/giovannidaniello15)

Ogni contributo, anche piccolo, è molto apprezzato! 🙏

## 📄 Licenza

[MIT](LICENSE) · Sviluppata da Giovanni D'Aniello con l'aiuto di Claude (Anthropic) · Grafici [Chart.js](https://www.chartjs.org/)
