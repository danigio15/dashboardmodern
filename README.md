<div align="center">

![Dashboard Modern](https://raw.githubusercontent.com/danigio15/dashboardmodern/main/logo.png)

# 🏠 Dashboard Modern

### La dashboard per Home Assistant che si configura da sola — e ti segue su ogni dispositivo

*A self-configuring Home Assistant dashboard that follows you on every device* 🇬🇧

<br>

![Version](https://img.shields.io/github/v/release/danigio15/dashboardmodern?label=version&color=blue&style=for-the-badge)
![HACS](https://img.shields.io/badge/HACS-custom-41BDF5?logo=homeassistant&logoColor=white&style=for-the-badge)
![Downloads](https://img.shields.io/github/downloads/danigio15/dashboardmodern/total?color=success&style=for-the-badge)

![HA](https://img.shields.io/badge/Home%20Assistant-2024.6%2B-41BDF5?logo=homeassistant&logoColor=white)
![Mobile](https://img.shields.io/badge/mobile-first-orange)
![Lang](https://img.shields.io/badge/🇮🇹%20Italiano-🇬🇧%20English-white)
[![Dona](https://img.shields.io/badge/PayPal-Offrimi%20un%20caff%C3%A8%20☕-00457C?logo=paypal&logoColor=white)](https://paypal.me/giovannidaniello15)

<br>

![Dashboard Modern — Home](https://raw.githubusercontent.com/danigio15/dashboardmodern/main/screenshots/home-light.png)

</div>

---

## 🇮🇹 Italiano

**Dashboard Modern** è una dashboard completa per Home Assistant in un **singolo file HTML**: niente YAML, niente card da comporre, niente dipendenze. La apri, il wizard trova le tue entità, e in pochi minuti hai energia, clima, stanze, telecamere, auto elettrica, boiler, luci e server sotto controllo — con lo stesso aspetto su telefono, tablet e desktop.

### ✨ Cosa sa fare (v0.10.1)

#### ⚡ Energia
- **Mappa flussi animata** in 4 viste: **Istantanea** (potenze live), **Giornaliera**, **Mensile** e **Report**
- **🧠 Motore periodi**: nei campi "oggi" e "mese" puoi mappare **qualsiasi contatore, anche TOTALE cumulativo** — i valori di giorno, mese e Report vengono ricostruiti come delta del periodo tramite le Long-Term Statistics di HA, allineati al pannello Energia di Home Assistant. Con entità che si azzerano da sole funziona uguale: il motore è universale
- **Nodi personalizzabili**: nome, icona, sensore live e **gruppo di carichi** per ogni nodo. Un nodo con un gruppo assegnato mostra automaticamente la **somma live dei suoi sottocarichi**. I nodi/le linee della mappa **compaiono solo se hai mappato un'entità** — niente linee "fantasma" su Oggi e Mese
- **Gruppi di carichi**: crea gruppi (Garage, Terrazza, Piano Terra…), aggiungi prese e dispositivi, aprili con un tap dal nodo della mappa
- **Report mensile**: KPI produzione/consumo/autosufficienza, bilancio economico, confronto settimanale e con l'anno precedente, grafico giornaliero, attività per dispositivo con ripartizione ☀️ solare / 🔌 rete — tutti i valori coerenti fra loro anche con contatori totali
- **💶 Tariffe personali**: €/kWh prelevato e €/kWh immesso configurabili

#### 📹 Telecamere — *nuovo motore in 0.9.8*
- **Streaming multi-strategia** con **fallback automatico**: prova **WebRTC nativo → HLS → MJPEG → Polling snapshot** e si ferma alla prima strategia che funziona, così vedi sempre qualcosa anche se una via non è disponibile
- **Audio**, **schermo intero** (iOS e Android) e refresh compatibile con la **WebView dell'app Home Assistant**
- La configurazione resta semplice: aggiungi nome ed entità della camera, al resto pensa il motore

#### 🔔 Quadro Avvisi — *potenziato in 0.10.x*
- Avvisi automatici per **Aperture, Batterie scariche, Luci, Clima, Riscaldamento** con contatore in Home e popup di dettaglio
- **⭐ Avvisi personalizzati**: crea un avviso su **una o più entità a scelta**, con **nome**, **condizione** (acceso/spento · uguale/diverso · maggiore/minore) e **stato/valore inserito a mano** (es. `heat`, `23.5`, `open`)
- **🔍 Ricerca entità e 😀 selettore icone** integrati; puoi **modificare** un avviso dopo averlo creato (✏️)
- La card in Home mostra il **contatore delle entità attive** e, al tap, apre il **popup con l'elenco di quali entità** stanno soddisfando la condizione

#### 💡 Luci
- **Gestione per stanza**: tab **Luci** nell'editor per creare le stanze e **assegnare ogni luce** con un menu a tendina
- **Riordino a piacimento** di stanze e luci con le frecce ▲▼; il **popup Gestione Luci** rispetta stanze e ordine (le luci senza stanza vanno in "Altre zone")
- Aggiornamento fluido: le card **non tremolano più** a ogni cambio di stato
- **Retrocompatibile**: se non organizzi nulla, continua a raggruppare dal nome come prima

#### 🌡️ Casa e comfort
- **Stanze con piani a tab**: ogni tab mostra la **temperatura media del piano**, con card premium leggibili anche su schermi stretti
- **Clima**: unità illimitate con comandi completi; se è configurata **una sola tipologia** (solo freddo o solo caldo), la vista si apre direttamente sulla zona giusta senza tab inutili
- **Meteo**: hero in home con **previsioni a 7 giorni e dettaglio orario** al tap, leggibile anche in **tema scuro**
- **Allarme**, **coperture**, **lavatrice** (anche non smart, via presa), **boiler/solare termico** con sinottico animato, **auto elettrica e wallbox** (con immagine auto personalizzabile), **server/MiniPC** (CPU, RAM dinamica, disco, temperatura, speedtest, uptime)

#### 🛠️ Configurazione
- **Wizard iniziale** con **rilevamento automatico** che riconosce centinaia di termini e brand (Solarman, Fronius, Growatt, SolarEdge, Huawei, Victron, Shelly, evcc, Reolink, Frigate, Daikin…) e ti mostra un **riepilogo** di quante entità ha assegnato e dove
- **Editor Dashboard** (⚙️): tab **Sezioni**, **Carichi** (nodi mappa, gruppi, tariffe, voci Report), **💡 Luci** (stanze e ordine), **🔔 Avvisi**, **Nascondi**
- **🔍 Ricerca entità potenziata**: il selettore carica **tutte** le entità di Home Assistant (non solo quelle già in dashboard), con ricerca **multi-parola**, ordinamento per pertinenza e **conteggio**
- **😀 Picker delle icone** ricercabile ovunque serva un'icona
- **🏷️ Logo del brand** nel wizard, nell'header dell'editor e nella pagina Configurazione
- **Le card compaiono/scompaiono da sole** in base a ciò che mappi
- **🔄 Sincronizzazione multi-dispositivo**: la configurazione viaggia via HA e ti segue su ogni browser
- **♻️ Auto-aggiornamento**: dopo un update la dashboard rileva la nuova versione e **si ricarica da sola** (versione visibile nella pagina Configurazione)
- **💾 Scarica dashboard configurata**: un tap sull'icona 💾 nell'editor scarica il file con **token e configurazione integrati** — lo metti in `/config/www` e ogni dispositivo è già pronto
- **Tema chiaro/scuro**, 100% responsive, italiano e inglese

### 📦 Installazione

**Via HACS (consigliata)**
1. HACS → menu ⋮ → *Repository personalizzati* → aggiungi `https://github.com/danigio15/dashboardmodern` (tipo: *Dashboard*)
2. Cerca **Dashboard Modern** e installa
3. Apri `http://TUO_HA:8123/local/dashboardmodern/dashboard.html` (versione inglese: `dashboard-en.html`)

**Manuale**
1. Scarica `dashboard.html` dall'ultima [release](https://github.com/danigio15/dashboardmodern/releases)
2. Copialo in `/config/www/`
3. Apri `http://TUO_HA:8123/local/dashboard.html`

### 🚀 Primi passi
1. Al primo avvio parte il **wizard**: inserisci URL di HA e un **token di lunga durata** (Profilo → Sicurezza → Token)
2. Lancia il **rilevamento automatico** e conferma le entità proposte
3. Rifinisci tutto da **⚙️ Editor** (7 tap veloci sul titolo, oppure `#setup` nell'URL)
4. Organizza le luci in stanze dal tab **💡 Luci** e crea i tuoi **🔔 Avvisi** personalizzati
5. Dall'editor, tocca **💾** per scaricare la tua copia con token integrato e mettila in `/config/www`

### 🔧 Suggerimenti
- **Apri sempre da dentro HA** (`/local/…`): così il collegamento e il token integrato funzionano senza reinserire nulla — vale identico con Nabu Casa e DuckDNS
- **Sensori totali**: per giornaliera/mensile/Report puoi usare direttamente i contatori lifetime — ci pensa il motore periodi
- **Statistiche**: le entità energia devono avere `state_class: total_increasing` (o `total`) per le Long-Term Statistics
- **Telecamere**: WebRTC richiede l'integrazione WebRTC/go2rtc; senza, il motore ripiega da solo su HLS/MJPEG/snapshot
- **Non vedi le novità dopo un update?** Controlla la versione nella pagina **Configurazione**; se resta indietro, svuota la cache del frontend dell'app

---

## 🇬🇧 English

**Dashboard Modern** is a complete Home Assistant dashboard in a **single HTML file**: no YAML, no card composing, no dependencies. Open it, let the wizard find your entities, and in minutes you have energy, climate, rooms, cameras, EV, boiler, lights and server under control — same look on phone, tablet and desktop.

### ✨ Features (v0.10.1)

#### ⚡ Energy
- **Animated flow map** in 4 views: **Live**, **Daily**, **Monthly**, **Report**
- **🧠 Period engine**: map **any counter — even cumulative TOTALS** — into the "today"/"month" fields; daily, monthly and Report values are rebuilt as period deltas via HA Long-Term Statistics, aligned with Home Assistant's Energy panel. Self-resetting entities work the same: the engine is universal
- **Customizable nodes**: name, icon, live sensor and **load group** per node — a node with a group shows the **live sum of its subloads** automatically. Map nodes/lines **appear only if you mapped an entity** — no more "ghost" lines on Daily and Monthly
- **Load groups**: create groups, add devices, open them with a tap from the map node
- **Monthly Report**: production/consumption/self-sufficiency KPIs, financial balance, weekly and year-over-year comparison, daily chart, per-device activity with ☀️ solar / 🔌 grid split — all values consistent even with cumulative counters
- **💶 Personal tariffs**: configurable €/kWh imported and exported

#### 📹 Cameras — *new engine in 0.9.8*
- **Multi-strategy streaming** with **automatic fallback**: it tries **native WebRTC → HLS → MJPEG → Polling snapshot** and stops at the first that works, so you always see something even if one path is unavailable
- **Audio**, **fullscreen** (iOS and Android) and refresh compatible with the **Home Assistant app WebView**
- Configuration stays simple: add the camera name and entity, the engine handles the rest

#### 🔔 Alerts Panel — *enhanced in 0.10.x*
- Automatic alerts for **Openings, Low batteries, Lights, Climate, Heating** with a counter on Home and a detail popup
- **⭐ Custom alerts**: create an alert on **one or more entities**, with a **name**, a **condition** (on/off · equal/different · greater/less) and a **manually entered state/value** (e.g. `heat`, `23.5`, `open`)
- Built-in **🔍 entity search** and **😀 icon picker**; you can **edit** an alert after creating it (✏️)
- The Home card shows the **count of active entities** and, on tap, opens the **popup listing which entities** currently meet the condition

#### 💡 Lights
- **Room management**: **Lights** editor tab to create rooms and **assign each light** via dropdown
- **Reorder freely** rooms and lights with ▲▼ arrows; the **Lights popup** honors rooms and order (lights without a room go to "Other zones")
- Smooth updates: the cards **no longer flicker** on every state change
- **Backward compatible**: if you organize nothing, it keeps grouping by name as before

#### 🌡️ Home & comfort
- **Rooms with floor tabs**: each tab shows the floor's **average temperature**, with premium cards that stay readable on narrow screens
- **Climate**: unlimited units with full controls; if only **one type** is configured (cold-only or hot-only) the view opens directly on the right zone, no useless tabs
- **Weather**: home hero with **7-day forecast and hourly detail** on tap, readable in **dark theme**
- **Alarm**, **covers**, **washing machine** (even non-smart, via plug), **boiler/solar thermal** with animated synoptic, **EV & wallbox** (with customizable car image), **server/MiniPC** (CPU, dynamic RAM, disk, temperature, speedtest, uptime)

#### 🛠️ Configuration
- **Setup wizard** with **auto-detection** recognizing hundreds of terms and brands (Solarman, Fronius, Growatt, SolarEdge, Huawei, Victron, Shelly, evcc, Reolink, Frigate, Daikin…) and a **summary** of how many entities were assigned and where
- **Dashboard Editor** (⚙️): **Sections**, **Loads** (map nodes, groups, tariffs, Report entries), **💡 Lights** (rooms and order), **🔔 Alerts**, **Hide**
- **🔍 Improved entity search**: the picker loads **all** Home Assistant entities (not just those already in the dashboard), with **multi-word** search, relevance ranking and a **count**
- **😀 Searchable icon picker** wherever an icon is needed
- **🏷️ Brand logo** in the wizard, the editor header and the Configuration page
- **Cards appear/disappear automatically** based on what you map
- **🔄 Multi-device sync**: your configuration travels through HA and follows you on every browser
- **♻️ Auto-update**: after an update the dashboard detects the new version and **reloads itself** (version shown on the Configuration page)
- **💾 Download configured dashboard**: one tap on the 💾 icon downloads the file with **token and configuration baked in** — drop it in `/config/www` and every device is instantly ready
- **Light/dark theme**, 100% responsive, Italian & English

### 📦 Installation

**Via HACS (recommended)**
1. HACS → ⋮ menu → *Custom repositories* → add `https://github.com/danigio15/dashboardmodern` (type: *Dashboard*)
2. Search **Dashboard Modern** and install
3. Open `http://YOUR_HA:8123/local/dashboardmodern/dashboard-en.html`

**Manual**
1. Download `dashboard-en.html` from the latest [release](https://github.com/danigio15/dashboardmodern/releases)
2. Copy it to `/config/www/`
3. Open `http://YOUR_HA:8123/local/dashboard-en.html`

### 🚀 Getting started
1. On first launch the **wizard** starts: enter your HA URL and a **long-lived token** (Profile → Security → Token)
2. Run **auto-detection** and confirm the proposed entities
3. Fine-tune everything from **⚙️ Editor** (7 quick taps on the title, or add `#setup` to the URL)
4. Organize your lights into rooms from the **💡 Lights** tab and build your custom **🔔 Alerts**
5. From the editor, tap **💾** to download your copy with the token baked in and drop it in `/config/www`

### 🔧 Tips
- **Always open from inside HA** (`/local/…`): the connection and baked token work without re-entering anything — identical for Nabu Casa and DuckDNS
- **Total sensors**: for daily/monthly/Report you can map lifetime counters directly — the period engine handles the rest
- **Statistics**: energy entities need `state_class: total_increasing` (or `total`) for Long-Term Statistics
- **Cameras**: WebRTC needs the WebRTC/go2rtc integration; without it, the engine falls back to HLS/MJPEG/snapshot on its own
- **Not seeing changes after an update?** Check the version on the **Configuration** page; if it lags behind, clear the app's frontend cache

---

<div align="center">

### ☕ Ti piace il progetto? / Enjoying the project?

[![Dona](https://img.shields.io/badge/PayPal-Offrimi%20un%20caff%C3%A8%20☕-00457C?logo=paypal&logoColor=white&style=for-the-badge)](https://paypal.me/giovannidaniello15)

**[📋 Changelog](CHANGELOG.md)** · **[🐛 Segnala un problema / Report an issue](https://github.com/danigio15/dashboardmodern/issues)**

</div>
