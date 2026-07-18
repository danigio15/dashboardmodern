<div align="center">

<img src="https://raw.githubusercontent.com/danigio15/dashboardmodern/main/logo.png" width="120" alt="Dashboard Modern logo">

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

<img src="https://raw.githubusercontent.com/danigio15/dashboardmodern/main/screenshots/home-light.png" width="380" alt="Dashboard Modern — Home">

</div>

---

## 🇮🇹 Italiano

**Dashboard Modern** è una dashboard completa per Home Assistant in un **singolo file HTML**: niente YAML, niente card da comporre, niente dipendenze. La apri, il wizard trova le tue entità, e in pochi minuti hai energia, clima, stanze, telecamere, auto elettrica, boiler, luci e server sotto controllo — con lo stesso aspetto su telefono, tablet e desktop.

### ✨ Cosa sa fare (v0.9.0)

#### ⚡ Energia
- **Mappa flussi animata** in 4 viste: **Istantanea** (potenze live), **Giornaliera**, **Mensile** e **Report**
- **🧠 Motore periodi**: nei campi "oggi" e "mese" puoi mappare **qualsiasi contatore, anche TOTALE cumulativo** — i valori di giorno, mese e Report vengono ricostruiti come delta del periodo tramite le Long-Term Statistics di HA, allineati al pannello Energia di Home Assistant. Con entità che si azzerano da sole funziona uguale: il motore è universale
- **Nodi personalizzabili**: nome, icona, sensore live e **gruppo di carichi** per ogni nodo. Un nodo con un gruppo assegnato mostra automaticamente la **somma live dei suoi sottocarichi**
- **Gruppi di carichi**: crea gruppi (Garage, Terrazza, Piano Terra…), aggiungi prese e dispositivi, aprili con un tap dal nodo della mappa
- **Report mensile**: KPI produzione/consumo/autosufficienza, bilancio economico, confronto settimanale e con l'anno precedente, grafico giornaliero, attività per dispositivo con ripartizione ☀️ solare / 🔌 rete — tutti i valori coerenti fra loro anche con contatori totali
- **Report automatico**: senza configurare nulla, si popola dai consumi mensili dei nodi mappati; le voci manuali hanno la precedenza
- **💶 Tariffe personali**: €/kWh prelevato e €/kWh immesso configurabili

#### 💡 Luci — *novità 0.9.0*
- **Gestione per stanza**: nuovo tab **Luci** nell'editor per creare le stanze e **assegnare ogni luce** a una stanza con un menu a tendina
- **Riordino a piacimento**: riordina sia le stanze sia le luci dentro ogni stanza con le frecce su/giù
- Il **popup Gestione Luci** rispetta stanze e ordine impostati; le luci senza stanza finiscono in "Altre zone"
- **Retrocompatibile**: se non organizzi nulla, continua a raggruppare dal nome ("Salone - Faretti") come prima

<div align="center">
<table>
<tr>
<td width="50%"><img src="https://raw.githubusercontent.com/danigio15/dashboardmodern/main/screenshots/lights-editor.jpg" alt="Editor Luci — stanze e assegnazione"></td>
<td width="50%"><img src="https://raw.githubusercontent.com/danigio15/dashboardmodern/main/screenshots/lights-popup.jpg" alt="Popup Gestione Luci raggruppato per stanza"></td>
</tr>
<tr>
<td align="center"><sub><b>Editor → tab 💡 Luci:</b> crea le stanze e assegna ogni luce con il menu a tendina. Le <b>frecce ▲▼</b> a sinistra riposizionano stanze e luci nell'ordine che preferisci.</sub></td>
<td align="center"><sub><b>Popup Gestione Luci:</b> le luci appaiono raggruppate per stanza, nell'ordine impostato. Le luci senza stanza finiscono in <b>Altre zone</b>.</sub></td>
</tr>
</table>
</div>

> 💡 **Come si riordina:** ogni riga (stanza o luce) ha due frecce a sinistra — **▲ sale**, **▼ scende**. L'ordine che imposti nell'editor è esattamente quello che vedrai nel popup Gestione Luci, su tutti i dispositivi grazie alla sincronizzazione.

#### 🌡️ Casa e comfort
- **Stanze con piani a tab**: organizza le stanze per piano; ogni tab mostra la **temperatura media del piano**, con card premium (icona grande in badge colorato, temperatura in gradiente, umidità in evidenza) e icona per ogni piano
- **Clima**: unità illimitate con comandi completi
- **Meteo**: hero in home con **previsioni a 7 giorni e dettaglio orario** al tap, leggibile anche in **tema scuro**
- **Telecamere** WebRTC/go2rtc, **allarme**, **coperture**, **lavatrice** (anche non smart, via presa), **boiler/solare termico** con sinottico animato, **auto elettrica e wallbox**, **server/MiniPC** (CPU, RAM dinamica, disco, temperatura, speedtest, uptime)

#### 🛠️ Configurazione
- **Wizard iniziale** con **rilevamento automatico** che riconosce centinaia di termini e brand (Solarman, Fronius, Growatt, SolarEdge, Huawei, Victron, Shelly, evcc, Reolink, Frigate, Daikin…) e ti mostra un **riepilogo** di quante entità ha assegnato e dove
- **Editor Dashboard** (⚙️): tab **Sezioni** (entità di ogni pagina, con 🔍 ricerca entità e 💾 Salva sezione), **Carichi** (nodi mappa, gruppi, tariffe, voci Report), **💡 Luci** (stanze e ordine), **Avvisi**, **Nascondi**
- **😀 Picker delle icone** ovunque serva un'icona
- **Le card compaiono/scompaiono da sole** in base a ciò che mappi
- **🔄 Sincronizzazione multi-dispositivo**: la configurazione viaggia via HA e ti segue su ogni browser
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
4. Organizza le luci in stanze dal tab **💡 Luci**
5. Dall'editor, tocca **💾** per scaricare la tua copia con token integrato e mettila in `/config/www`

### 🔧 Suggerimenti
- **Apri sempre da dentro HA** (`/local/…`): così il collegamento e il token integrato funzionano senza reinserire nulla — vale identico con Nabu Casa e DuckDNS
- **Sensori totali**: per giornaliera/mensile/Report puoi usare direttamente i contatori lifetime — ci pensa il motore periodi
- **Statistiche**: le entità energia devono avere `state_class: total_increasing` (o `total`) per le Long-Term Statistics
- **Lavatrici non smart**: basta una presa con misurazione — lo stato è dedotto dalla potenza

---

## 🇬🇧 English

**Dashboard Modern** is a complete Home Assistant dashboard in a **single HTML file**: no YAML, no card composing, no dependencies. Open it, let the wizard find your entities, and in minutes you have energy, climate, rooms, cameras, EV, boiler, lights and server under control — same look on phone, tablet and desktop.

### ✨ Features (v0.9.0)

#### ⚡ Energy
- **Animated flow map** in 4 views: **Live**, **Daily**, **Monthly**, **Report**
- **🧠 Period engine**: map **any counter — even cumulative TOTALS** — into the "today"/"month" fields; daily, monthly and Report values are rebuilt as period deltas via HA Long-Term Statistics, aligned with Home Assistant's Energy panel. Self-resetting entities work the same: the engine is universal
- **Customizable nodes**: name, icon, live sensor and **load group** per node — a node with a group shows the **live sum of its subloads** automatically
- **Load groups**: create groups, add devices, open them with a tap from the map node
- **Monthly Report**: production/consumption/self-sufficiency KPIs, financial balance, weekly and year-over-year comparison, daily chart, per-device activity with ☀️ solar / 🔌 grid split — all values consistent even with cumulative counters
- **Auto Report** from the mapped monthly nodes; manual entries take precedence
- **💶 Personal tariffs**: configurable €/kWh imported and exported

#### 💡 Lights — *new in 0.9.0*
- **Room management**: new **Lights** editor tab to create rooms and **assign each light** to a room via dropdown
- **Reorder freely**: reorder both rooms and the lights inside each room with up/down arrows
- The **Lights popup** honors the rooms and order you set; lights without a room go to "Other zones"
- **Backward compatible**: if you organize nothing, it keeps grouping by name ("Living room - Spots") as before

<div align="center">
<table>
<tr>
<td width="50%"><img src="https://raw.githubusercontent.com/danigio15/dashboardmodern/main/screenshots/lights-editor.jpg" alt="Lights editor — rooms and assignment"></td>
<td width="50%"><img src="https://raw.githubusercontent.com/danigio15/dashboardmodern/main/screenshots/lights-popup.jpg" alt="Lights popup grouped by room"></td>
</tr>
<tr>
<td align="center"><sub><b>Editor → 💡 Lights tab:</b> create rooms and assign each light via dropdown. The <b>▲▼ arrows</b> on the left reorder rooms and lights however you like.</sub></td>
<td align="center"><sub><b>Lights popup:</b> lights appear grouped by room, in the order you set. Lights without a room go to <b>Other zones</b>.</sub></td>
</tr>
</table>
</div>

> 💡 **How to reorder:** each row (room or light) has two arrows on the left — **▲ up**, **▼ down**. The order you set in the editor is exactly what you'll see in the Lights popup, on every device thanks to sync.

#### 🌡️ Home & comfort
- **Rooms with floor tabs**: each tab shows the floor's **average temperature**, with premium cards (big icon in a colored badge, gradient temperature, prominent humidity) and a per-floor icon
- **Climate**: unlimited units with full controls
- **Weather**: home hero with **7-day forecast and hourly detail** on tap, readable in **dark theme**
- **Cameras** (WebRTC/go2rtc), **alarm**, **covers**, **washing machine** (even non-smart, via plug), **boiler/solar thermal** with animated synoptic, **EV & wallbox**, **server/MiniPC** (CPU, dynamic RAM, disk, temperature, speedtest, uptime)

#### 🛠️ Configuration
- **Setup wizard** with **auto-detection** recognizing hundreds of terms and brands (Solarman, Fronius, Growatt, SolarEdge, Huawei, Victron, Shelly, evcc, Reolink, Frigate, Daikin…) and a **summary** of how many entities were assigned and where
- **Dashboard Editor** (⚙️): **Sections** (per-page entities with 🔍 search and 💾 Save section), **Loads** (map nodes, groups, tariffs, Report entries), **💡 Lights** (rooms and order), **Alerts**, **Hide**
- **😀 Icon picker** wherever an icon is needed
- **Cards appear/disappear automatically** based on what you map
- **🔄 Multi-device sync**: your configuration travels through HA and follows you on every browser
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
4. Organize your lights into rooms from the **💡 Lights** tab
5. From the editor, tap **💾** to download your copy with the token baked in and drop it in `/config/www`

### 🔧 Tips
- **Always open from inside HA** (`/local/…`): the connection and baked token work without re-entering anything — identical for Nabu Casa and DuckDNS
- **Total sensors**: for daily/monthly/Report you can map lifetime counters directly — the period engine handles the rest
- **Statistics**: energy entities need `state_class: total_increasing` (or `total`) for Long-Term Statistics
- **Non-smart washing machines**: a metering plug is enough — the state is derived from power

---

<div align="center">

### ☕ Ti piace il progetto? / Enjoying the project?

[![Dona](https://img.shields.io/badge/PayPal-Offrimi%20un%20caff%C3%A8%20☕-00457C?logo=paypal&logoColor=white&style=for-the-badge)](https://paypal.me/giovannidaniello15)

**[📋 Changelog](CHANGELOG.md)** · **[🐛 Segnala un problema / Report an issue](https://github.com/danigio15/dashboardmodern/issues)**

</div>
