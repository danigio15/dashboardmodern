# Changelog

🇮🇹 Italiano · [🇬🇧 English below](#-english)

Il formato segue [Keep a Changelog](https://keepachangelog.com/it/) e il versionamento [SemVer](https://semver.org).

---

## [0.3.9] — 2026-07-15

### ✨ Migliorato
- **🪄 Auto-rilevamento v2** — motore molto più intelligente: punteggio di somiglianza con soglia (niente più match rigidi), sinonimi bilingue estesi (60+ termini IT/EN), vincoli sulle unità di misura (kWh per le energie, W per le potenze, % per le cariche, °C, km, bar…), abbinamento automatico umidità→stanza migliorato, rilevamento luci (se saltate nello step 4) e caldaia.

### 🐛 Corretto
- **Pulsante "Rileva automaticamente"** — nuovo colore verde ad alto contrasto con testo bianco: pienamente leggibile in entrambi i temi.

## [0.3.8] — 2026-07-15

### ✨ Aggiunto
- **🪄 Auto-rilevamento entità** — nuovo pulsante nello step "Collega le tue entità": la dashboard legge il tuo Home Assistant e propone automaticamente unità clima, telecamere, stanze (temperatura+umidità), avvisi (aperture e batterie) ed entità delle sezioni tramite riconoscimento intelligente. Tutte le proposte restano modificabili: la configurazione passa da minuti a secondi senza perdere personalizzazione.
- **📊 Indicatori di completamento** — ogni sezione mostra "N/M collegate" (verde quando inizi a collegare).
- **📋 Riepilogo finale** — l'ultimo step del wizard mostra il conteggio di tutto ciò che hai configurato.

## [0.3.7] — 2026-07-15

### ✨ Aggiunto
- **👋 Messaggio di benvenuto guidato** — se nessuna entità è ancora configurata (wizard saltato o step Entità vuoto), la Home mostra un banner che spiega perché le card sono nascoste e come aprire la configurazione (7 tap sul titolo). Risolve la confusione segnalata nella issue #1.

## [0.3.6] — 2026-07-15

### ✨ Aggiunto
- **🌍 Versione inglese** — la release ora include due file: `dashboard.html` (italiano) e `dashboard-en.html` (English). Scegli la lingua con l'URL della plancia; ogni aggiornamento futuro esce automaticamente in entrambe le lingue.
- **💗 Supporto al progetto** — pulsante Sponsor e link PayPal per le donazioni.

## [0.3.5] — 2026-07-14

### ✨ Aggiunto
- **🔔 Quadro Avvisi nel Setup Wizard** — aggiungi sensori di apertura (🚪) e batterie (🔋) con nome personalizzato ed entità con autocomplete; ogni voce è rimovibile col cestino.

### 🐛 Corretto
- **Azioni rapide duplicate nel wizard** — l'accordion dell'editor era finito per errore nel wizard; ora ognuno è al suo posto.

## [0.3.4] — 2026-07-14

### ✨ Aggiunto
- **🔄 Aggiornamenti automatici** — dopo un update HACS la dashboard rileva la nuova versione e si ricarica da sola bypassando la cache. L'URL della plancia non va mai più modificato.

### 🔧 Modificato
- **🖼️ Immagine auto** spostata dentro l'accordion "🚗 Auto elettrica".

## [0.3.3] — 2026-07-14

### 🐛 Corretto
- **Sezioni disattivate visibili su mobile** — i tab vengono ora rimossi fisicamente dal DOM.
- **Accordion Stanze duplicato** nel wizard.

## [0.3.2] — 2026-07-14

### ✨ Aggiunto
- **🌡️ Stanze nel wizard** e **🌐 URL remoto** (Nabu Casa) nello step Connessione.

### 🔧 Modificato
- **🔥 Caldaia semplificata**: unico campo facoltativo dentro "Unità clima".

## [0.3.1] — 2026-07-14

### ✨ Aggiunto
- **⚡ Azioni rapide personalizzabili** (predefinite o custom con entità/script e conferma); se vuote, il blocco sparisce dalla Home.

## [0.3.0] — 2026-07-14

### ✨ Aggiunto
- **👻 Auto-pulizia**: gli elementi senza entità configurate vengono nascosti.
- **❄️ Unità clima illimitate**: condizionatori e termosifoni aggiungibili/rimovibili da UI.

## [0.2.x] — 2026-07-14

- **🧙 Setup Wizard a 6 step**, **📑 registry di 100+ entità** con etichette umane, **📹 telecamere illimitate**, **🎨 tema chiaro/scuro/auto**, **⚙️ pagina Config** per admin, **🆘 accessi di emergenza** (7 tap, `#setup`), **🔒 neutralizzazione completa** del file distribuito.

## [0.1.1] — 2026-07-14

🎉 Prima release pubblica via HACS.

---

# 🇬🇧 English

The format follows [Keep a Changelog](https://keepachangelog.com) and [SemVer](https://semver.org).

## [0.3.9] — 2026-07-15

### ✨ Improved
- **🪄 Auto-detection v2** — much smarter engine: similarity scoring with threshold (no more rigid matches), extended bilingual synonyms (60+ IT/EN terms), unit-of-measure constraints (kWh for energy, W for power, % for charge, °C, km, bar…), improved humidity→room pairing, lights detection (if skipped in step 4) and boiler detection.

### 🐛 Fixed
- **"Auto-detect" button** — new high-contrast green with white text: fully readable in both themes.

## [0.3.8] — 2026-07-15

### ✨ Added
- **🪄 Entity auto-detection** — new button in the "Link your entities" step: the dashboard reads your Home Assistant and automatically proposes climate units, cameras, rooms (temperature+humidity), alerts (openings and batteries) and section entities via smart matching. Every proposal remains editable: setup goes from minutes to seconds without losing customization.
- **📊 Completion indicators** — each section shows "N/M linked" (green once you start linking).
- **📋 Final summary** — the wizard's last step shows a count of everything you configured.

## [0.3.7] — 2026-07-15

### ✨ Added
- **👋 Guided welcome message** — if no entities are configured yet (wizard skipped or empty Entities step), Home shows a banner explaining why cards are hidden and how to open the setup (7 taps on the title). Fixes the confusion reported in issue #1.

## [0.3.6] — 2026-07-15

### ✨ Added
- **🌍 English version** — the release now ships two files: `dashboard.html` (Italian) and `dashboard-en.html` (English). Pick your language via the panel URL; every future update ships in both languages automatically.
- **💗 Project support** — Sponsor button and PayPal link for donations.

## [0.3.5] — 2026-07-14

### ✨ Added
- **🔔 Alerts Panel in the Setup Wizard** — add opening sensors (🚪) and batteries (🔋) with a custom name and entity autocomplete; every item is removable.

### 🐛 Fixed
- **Duplicated quick actions in the wizard** — the editor accordion had ended up inside the wizard by mistake; each is now in its own place.

## [0.3.4] — 2026-07-14

### ✨ Added
- **🔄 Automatic updates** — after a HACS update the dashboard detects the new version and reloads itself bypassing the cache. You never need to touch the panel URL again.

### 🔧 Changed
- **🖼️ Car image** moved inside the "🚗 Electric car" accordion.

## [0.3.3] — 2026-07-14

### 🐛 Fixed
- **Disabled sections still visible on mobile** — tabs are now physically removed from the DOM.
- **Duplicated Rooms accordion** in the wizard.

## [0.3.2] — 2026-07-14

### ✨ Added
- **🌡️ Rooms in the wizard** and **🌐 remote URL** (Nabu Casa) in the Connection step.

### 🔧 Changed
- **🔥 Simplified boiler**: single optional field inside "Climate units".

## [0.3.1] — 2026-07-14

### ✨ Added
- **⚡ Customizable quick actions** (built-in or custom with entity/script and confirmation); if none are configured, the block disappears from Home.

## [0.3.0] — 2026-07-14

### ✨ Added
- **👻 Auto-cleanup**: elements without configured entities are hidden.
- **❄️ Unlimited climate units**: air conditioners and radiators can be added/removed from the UI.

## [0.2.x] — 2026-07-14

- **🧙 6-step Setup Wizard**, **📑 registry of 100+ entities** with human labels, **📹 unlimited cameras**, **🎨 light/dark/auto theme**, **⚙️ admin Config page**, **🆘 emergency access** (7 taps, `#setup`), **🔒 fully neutralized** distributed file.

## [0.1.1] — 2026-07-14

🎉 First public release via HACS.
