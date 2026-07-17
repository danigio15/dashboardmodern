<div align="center">

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

<img src="screenshots/home-light.png" width="380" alt="Dashboard Modern — Home">

</div>

---

## 🇮🇹 Italiano

**Dashboard Modern** è una dashboard completa per Home Assistant in un **singolo file HTML**: niente YAML, niente card da comporre, niente dipendenze. La apri, il wizard trova le tue entità, e in pochi minuti hai energia, clima, stanze, telecamere, auto elettrica, boiler e server sotto controllo — con lo stesso aspetto su telefono, tablet e desktop.

### ✨ Cosa sa fare (v0.8.0)

#### ⚡ Energia
- **Mappa flussi animata** in 4 viste: **Istantanea** (potenze live), **Giornaliera**, **Mensile** e **Report**
- **🧠 Motore periodi** *(novità 0.8.0)*: nei campi "oggi" e "mese" puoi mappare **qualsiasi contatore, anche TOTALE cumulativo** — i valori di giorno, mese e Report vengono ricostruiti come delta del periodo tramite le Long-Term Statistics di HA. Con entità che si azzerano da sole funziona uguale: il motore è universale
- **Nodi personalizzabili**: nome, icona, sensore live e **gruppo di carichi** per ogni nodo. Un nodo con un gruppo assegnato mostra automaticamente la **somma live dei suoi sottocarichi**
- **Gruppi di carichi**: crea gruppi (Garage, Terrazza, Piano Terra…), aggiungi prese e dispositivi, aprili con un tap dal nodo della mappa
- **Report mensile**: KPI produzione/consumo/autosufficienza, bilancio economico, confronto settimanale e con l'anno precedente, grafico giornaliero, attività per dispositivo con ripartizione ☀️ solare / 🔌 rete
- **Report automatico**: senza configurare nulla, il Report si popola da solo con i consumi mensili dei nodi mappati; le voci manuali hanno la precedenza
- **Consumo stimato**: se non hai il contatore del consumo totale, viene ricavato dal bilancio energetico (mostrato con ≈)
- **💶 Tariffe personali**: €/kWh prelevato e €/kWh immesso configurabili — tutti i calcoli del Report li usano

#### 🌡️ Casa e comfort
- **Stanze con piani a tab**: organizza le stanze per piano; ogni tab mostra la **temperatura media del piano** ed evidenzia le stanze di quel livello
- **Clima**: unità illimitate con comandi completi
- **Meteo**: hero in home con **previsioni a 7 giorni e dettaglio orario** al tap, perfettamente leggibile anche in **tema scuro**
- **Telecamere** WebRTC/go2rtc, **allarme**, **luci**, **coperture**, **lavatrice** (anche non smart, via presa), **boiler/solare termico** con sinottico animato, **auto elettrica e wallbox**, **server/MiniPC** (CPU, RAM, disco, temperatura, speedtest, uptime)

#### 🛠️ Configurazione
- **Wizard iniziale** con **rilevamento automatico potenziato**: dizionario IT/EN con centinaia di termini e brand (Solarman, Fronius, Growatt, SolarEdge, Huawei, Victron, Shelly, evcc, Reolink, Frigate, Daikin…)
- **Editor Dashboard** (⚙️): tab **Sezioni** (entità di ogni pagina, con 🔍 ricerca entità e **💾 Salva sezione**), **Carichi** (nodi mappa, gruppi, tariffe, voci Report), **Avvisi**, **Nascondi**
- **😀 Picker delle icone** ovunque serva un'icona: griglia di emoji, un tap e via
- **Le card compaiono/scompaiono da sole**: ciò che non mappi non esiste, ciò che mappi appare subito
- **🔄 Sincronizzazione multi-dispositivo**: la configurazione viaggia via HA e ti segue su ogni browser
- **💾 Scarica dashboard configurata**: un tap sull'icona 💾 nell'editor scarica il file con **token e configurazione integrati** — lo metti in `/config/www` e ogni dispositivo è già pronto, senza reinserire nulla
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
4. Dall'editor, tocca **💾** per scaricare la tua copia con token integrato e mettila in `/config/www`

### 🔧 Suggerimenti
- **Sensori totali**: per giornaliera/mensile/Report puoi usare direttamente i contatori lifetime (es. `sensor.energia_totale_casa`) — ci pensa il motore periodi
- **Statistiche**: le entità energia devono avere `state_class: total_increasing` (o `total`) per le Long-Term Statistics
- **Lavatrici non smart**: basta una presa con misurazione — lo stato è dedotto dalla potenza

---

## 🇬🇧 English

**Dashboard Modern** is a complete Home Assistant dashboard in a **single HTML file**: no YAML, no card composing, no dependencies. Open it, let the wizard find your entities, and in minutes you have energy, climate, rooms, cameras, EV, boiler and server under control — same look on phone, tablet and desktop.

### ✨ Features (v0.8.0)

#### ⚡ Energy
- **Animated flow map** in 4 views: **Live**, **Daily**, **Monthly**, **Report**
- **🧠 Period engine** *(new in 0.8.0)*: map **any counter — even cumulative TOTALS** — into the "today"/"month" fields; daily, monthly and Report values are rebuilt as period deltas via HA Long-Term Statistics. Self-resetting entities work the same: the engine is universal
- **Customizable nodes**: name, icon, live sensor and **load group** per node — a node with a group shows the **live sum of its subloads** automatically
- **Load groups**: create groups (Garage, Terrace…), add devices, open them with a tap from the map node
- **Monthly Report**: production/consumption/self-sufficiency KPIs, financial balance, weekly and year-over-year comparison, daily chart, per-device activity with ☀️ solar / 🔌 grid split
- **Auto Report**: with zero config it populates from the mapped monthly nodes; manual entries take precedence
- **Estimated consumption** from the energy balance when the total-consumption meter is missing (shown with ≈)
- **💶 Personal tariffs**: configurable €/kWh imported and exported — used across the whole Report

#### 🌡️ Home & comfort
- **Rooms with floor tabs**: each tab shows the floor's **average temperature** and its rooms
- **Climate**: unlimited units with full controls
- **Weather**: home hero with **7-day forecast and hourly detail** on tap, fully readable in **dark theme**
- **Cameras** (WebRTC/go2rtc), **alarm**, **lights**, **covers**, **washing machine** (even non-smart, via plug), **boiler/solar thermal** with animated synoptic, **EV & wallbox**, **server/MiniPC** (CPU, RAM, disk, temperature, speedtest, uptime)

#### 🛠️ Configuration
- **Setup wizard** with a **boosted auto-detection** dictionary: hundreds of IT/EN terms and brands (Solarman, Fronius, Growatt, SolarEdge, Huawei, Victron, Shelly, evcc, Reolink, Frigate, Daikin…)
- **Dashboard Editor** (⚙️): **Sections** (per-page entities with 🔍 entity search and **💾 Save section**), **Loads** (map nodes, groups, tariffs, Report entries), **Alerts**, **Hide**
- **😀 Icon picker** wherever an icon is needed
- **Cards appear/disappear automatically** based on what you map
- **🔄 Multi-device sync**: your configuration travels through HA and follows you on every browser
- **💾 Download configured dashboard**: one tap on the 💾 icon in the editor downloads the file with **token and configuration baked in** — drop it in `/config/www` and every device is instantly ready
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
4. From the editor, tap **💾** to download your copy with the token baked in and drop it in `/config/www`

### 🔧 Tips
- **Total sensors**: for daily/monthly/Report you can map lifetime counters directly (e.g. `sensor.total_house_energy`) — the period engine handles the rest
- **Statistics**: energy entities need `state_class: total_increasing` (or `total`) for Long-Term Statistics
- **Non-smart washing machines**: a metering plug is enough — the state is derived from power

---

<div align="center">

### ☕ Ti piace il progetto? / Enjoying the project?

[![Dona](https://img.shields.io/badge/PayPal-Offrimi%20un%20caff%C3%A8%20☕-00457C?logo=paypal&logoColor=white&style=for-the-badge)](https://paypal.me/giovannidaniello15)

**[📋 Changelog](CHANGELOG.md)** · **[🐛 Segnala un problema / Report an issue](https://github.com/danigio15/dashboardmodern/issues)**

</div>
