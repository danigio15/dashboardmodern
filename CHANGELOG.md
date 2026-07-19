# Changelog

🇮🇹 Italiano · [🇬🇧 English below](#-english)

Il formato segue [Keep a Changelog](https://keepachangelog.com/it/) e il versionamento [SemVer](https://semver.org).

---

## [0.10.3] — 2026-07-19

### Corretto
- **Modifica icona/nome degli avvisi personalizzati** — cambiando solo l'icona (o il nome) la card in Home non si aggiornava (restava la vecchia icona): la guardia anti-flicker non considerava questi campi. Ora la modifica si vede subito.

## [0.10.3] — 2026-07-19 (EN)

### Fixed
- **Editing a custom alert's icon/name** — changing only the icon (or name) didn't update the Home card (it kept the old icon): the anti-flicker guard ignored those fields. The change now shows immediately.

## [0.10.2] — 2026-07-19

### Corretto
- **Popup avvisi personalizzati** — si apriva un attimo poi si svuotava ("Nessun elemento attivo"): il refresh automatico lo ridisegnava con la funzione sbagliata. Ora resta popolato e **si aggiorna live** con l'elenco delle entità attive.

## [0.10.2] — 2026-07-19 (EN)

### Fixed
- **Custom alert popup** — it opened for a moment then went empty ("No active entity"): the auto-refresh redrew it with the wrong function. It now stays populated and **updates live** with the list of active entities.

## [0.10.1] — 2026-07-19

### Corretto
- **⭐ Card avvisi personalizzati** — ora mostra il **contatore delle entità attive** (non più solo lo stato "ON") e, toccandola, apre un **popup con l'elenco di quali entità** stanno soddisfando la condizione.
- **Campo entità** negli Avvisi: rimossa la fastidiosa **lista automatica di tutte le entità di HA** (datalist nativa); resta solo la ricerca con la 🔍.

## [0.10.1] — 2026-07-19 (EN)

### Fixed
- **⭐ Custom alert card** — now shows the **count of active entities** (instead of just the "ON" state) and, when tapped, opens a **popup listing which entities** currently meet the condition.
- **Entity field** in Alerts: removed the annoying **native list of all HA entities** (datalist); only the 🔍 search remains.

## [0.10.0] — 2026-07-19

### Aggiunto
- **⭐ Avvisi personalizzati potenziati** — ora un avviso può monitorare **più entità** (lista con ➕/✕: scatta se una qualsiasi soddisfa la condizione), lo puoi **modificare dopo la creazione** (✏️) e la condizione supporta lo **stato/valore inserito a mano** (es. `heat`, `23.5`, `open`).

## [0.10.0] — 2026-07-19 (EN)

### Added
- **⭐ Enhanced custom alerts** — an alert can now watch **multiple entities** (list with ➕/✕: fires if any one meets the condition), you can **edit it after creation** (✏️), and the condition supports a **manually entered state/value** (e.g. `heat`, `23.5`, `open`).

## [0.9.9] — 2026-07-19

### Migliorato
- **🔍 Ricerca entità e icona negli Avvisi** — nel tab Avvisi il campo entità ora ha la lente per cercarla per nome (come le altre sezioni), e per gli avvisi personalizzati c'è un **selettore di icone ricercabile** (scrivi "acqua", "porta", "fuoco"…). Il campo nome ("Nome dell'avviso") è sempre disponibile per dare un nome a qualsiasi avviso.

## [0.9.9] — 2026-07-19 (EN)

### Improved
- **🔍 Entity and icon search in Alerts** — in the Alerts tab the entity field now has a magnifier to search it by name (like other sections), and custom alerts get a **searchable icon picker** (type "water", "door", "fire"…). The name field ("Alert name") is always available to name any alert.

## [0.9.8] — 2026-07-19

### Aggiunto
- **📹 Nuovo motore telecamere multi-strategia** — riscritta tutta la parte streaming: cascata automatica **WebRTC nativo → HLS → MJPEG → Polling snapshot**. Il sistema prova le strategie in ordine e si ferma alla prima che funziona, con **audio**, **schermo intero** (iOS/Android) e refresh compatibile con la WebView dell'app HA. Sostituisce il vecchio player a iframe `/webrtc/embed`. La configurazione delle telecamere (nome, entità) resta invariata.

### Corretto
- **⭐ Avvisi personalizzati nel tab giusto** — l'opzione "Personalizzato" ora compare nel tab **Avvisi** dell'editor (prima era finita in un blocco diverso e non si vedeva). Crea un avviso su qualsiasi entità con nome, condizione e icona a scelta.

## [0.9.8] — 2026-07-19 (EN)

### Added
- **📹 New multi-strategy camera engine** — the whole streaming part was rewritten: automatic cascade **native WebRTC → HLS → MJPEG → Polling snapshot**. The system tries strategies in order and stops at the first that works, with **audio**, **fullscreen** (iOS/Android) and HA app WebView-compatible refresh. Replaces the old `/webrtc/embed` iframe player. Camera configuration (name, entity) stays unchanged.

### Fixed
- **⭐ Custom alerts in the right tab** — the "Custom" option now appears in the editor's **Alerts** tab (previously it ended up in a different block and wasn't visible). Create an alert on any entity with your own name, condition and icon.

## [0.9.7] — 2026-07-19

### Aggiunto
- **⭐ Avvisi personalizzati** — nel Quadro Avvisi ora puoi creare un avviso su **qualsiasi entità**, con **nome**, **condizione** (acceso/spento · uguale/diverso · maggiore/minore di un valore) e **icona** a scelta. Selezione dell'entità con ricerca integrata. L'avviso compare in Home quando la condizione è vera.
- **🏷️ Logo del brand** nel wizard di setup, nell'header dell'Editor Dashboard e nella pagina Configurazione (SVG inline, nessun file esterno).

### Corretto
- **💡 Card luci che "tremavano"** — il popup Gestione Luci veniva ricostruito da zero a ogni aggiornamento di stato; ora l'aggiornamento è **incrementale** (solo stato/LED/testo delle card esistenti): niente più flicker.
- **🖼️ Immagine auto (EV) che non compariva** — l'immagine personalizzata veniva sovrascritta dal ciclo di stato con quella di default; ora, se impostata, viene **mantenuta**.
- **🔌 Linee "fantasma" nel Flow** — nelle mappe *Oggi* e *Mese* le linee dei carichi senza entità configurata restavano visibili in grigio. Ora un carico (boiler, wallbox, clima, lavanderia, cucina…) **compare solo se ha un'entità associata**.
- **❄️🔥 Tab Clima** — se è configurata una sola tipologia (solo condizionatori o solo termosifoni) il selettore Freddo/Caldo sparisce e si apre **direttamente la zona giusta**.
- **🌡️ Nomi delle stanze troncati su smartphone** — il testo delle card temperatura ora va a capo e resta leggibile su schermi stretti.

### Migliorato
- **🔍 Ricerca entità potenziata** — nell'editor il selettore entità ora carica l'**elenco completo** delle entità di Home Assistant (non solo quelle tracciate dalla dashboard), con **ricerca multi-parola**, ordinamento per pertinenza e **conteggio delle entità disponibili**.

## [0.9.7] — 2026-07-19 (EN)

### Added
- **⭐ Custom alerts** — in the Alerts Panel you can now create an alert on **any entity**, with your own **name**, **condition** (on/off · equal/different · greater/less than a value) and **icon**. Entity selection with built-in search. The alert shows on Home when the condition is true.
- **🏷️ Brand logo** in the setup wizard, in the Editor Dashboard header and on the Configuration page (inline SVG, no external asset).

### Fixed
- **💡 Flickering light cards** — the Lights popup was fully rebuilt on every state update; it now updates **incrementally** (only on/LED/state of existing cards): no more flicker.
- **🖼️ EV car image not showing** — the custom image was overwritten by the state loop with the default one; when set, it is now **kept**.
- **🔌 "Ghost" lines in the Flow** — in the *Today* and *Month* maps, lines for loads without a configured entity stayed visible in grey. A load (boiler, wallbox, climate, laundry, kitchen…) now **appears only if it has an entity mapped**.
- **❄️🔥 Climate tabs** — if only one type is configured (only air conditioners or only radiators) the Cold/Hot switch disappears and the **right zone opens directly**.
- **🌡️ Room names truncated on phones** — temperature card text now wraps and stays readable on narrow screens.

### Improved
- **🔍 More powerful entity search** — in the editor the entity picker now loads the **full list** of Home Assistant entities (not just those tracked by the dashboard), with **multi-word search**, relevance ranking and a **count of available entities**.

## [0.9.6] — 2026-07-18

### Migliorato
- **🔍 Rilevamento automatico ancora più completo** — il wizard ora interroga l'intero motore di HA e colloca molto di più: limiti alzati (luci fino a 300, aperture e batterie fino a 80, clima/riscaldamento fino a 60) e nuovo rilevamento delle **azioni rapide** da script e scene (con nome dalla stanza HA). Lo scoring resta quello preciso già basato su device_class, state_class, unità e area ufficiale delle entità. Tutto resta modificabile: sono proposte.
- **🖼️ Logo visibile su HACS** — logo e immagini del README convertiti in Markdown puro: HACS bloccava i tag HTML img mostrandoli come link rotti. Ora il logo compare nella pagina del repository.

## [0.9.6] — 2026-07-18 (EN)

### Improved
- **🔍 Even more complete auto-detection** — the wizard now queries the entire HA engine and places much more: raised limits (lights up to 300, openings and batteries up to 80, climate/heating up to 60) and new **quick actions** detection from scripts and scenes (named from the HA area). Scoring stays the precise one based on device_class, state_class, unit and official entity area. Everything stays editable: they are proposals.
- **🖼️ Logo visible on HACS** — logo and README images converted to pure Markdown: HACS blocked HTML img tags showing them as broken links. The logo now appears on the repository page.

## [0.9.5] — 2026-07-18

### Corretto
- **📊 Consumo Casa nel Report finalmente corretto** — il Report mostrava un consumo inferiore al reale (Luglio 393 invece di 464, Giugno 784 invece di 910) perché leggeva il sensore diretto di consumo, che misura solo una PARTE dei circuiti di casa. La mappa Mensile invece calcolava già il valore giusto dal bilancio energetico. Ora anche il Report usa la stessa formula del pannello Energia di HA: consumo casa = solare − immesso + prelevato + batteria scaricata − batteria caricata. Verificato sui dati reali di due mesi: Luglio 464 kWh e Giugno 910 kWh, identici al pannello HA. Produzione, rete e batteria erano già corretti.

## [0.9.5] — 2026-07-18 (EN)

### Fixed
- **📊 Home consumption in Report finally correct** — the Report showed a consumption lower than reality (July 393 instead of 464, June 784 instead of 910) because it read the direct consumption sensor, which measures only PART of the home circuits. The Monthly map already computed the right value from the energy balance. Now the Report uses the same formula as HA's Energy panel: home consumption = solar − exported + imported + battery discharged − battery charged. Verified on two months of real data: July 464 kWh and June 910 kWh, identical to the HA panel. Production, grid and battery were already correct.

## [0.9.4] — 2026-07-18

### Corretto
- **📊 Mesi passati: valori dimezzati/errati con contatori TOTALI** — selezionando un mese concluso (es. Giugno) con contatori cumulativi, il Report mostrava circa la metà del reale (es. Solare 627 invece di 1120 kWh, Casa 392 invece di 910). La lettura con period:month restituiva un change parziale su alcuni contatori. Ora l'energia del mese è calcolata come DIFFERENZA dei valori cumulativi (sum) tra l'ultimo e il primo giorno del mese, usando period:day con un baseline preso dal giorno precedente — esattamente come il pannello Energia di HA. Verificato: Giugno solare 1119.9 kWh = pannello HA. Stesso baseline applicato al fallback History.

## [0.9.4] — 2026-07-18 (EN)

### Fixed
- **📊 Past months: halved/wrong values with TOTAL counters** — selecting a completed month (e.g. June) with cumulative counters, the Report showed about half the real value (e.g. Solar 627 instead of 1120 kWh, Home 392 instead of 910). Reading with period:month returned a partial change on some counters. The month energy is now computed as the DIFFERENCE of cumulative values (sum) between the last and first day of the month, using period:day with a baseline taken from the previous day — exactly like HA's Energy panel. Verified: June solar 1119.9 kWh = HA panel. Same baseline applied to the History fallback.

## [0.9.3] — 2026-07-18

### Corretto
- **📊 Report vs mappa: consumo allineato** — nel mese corrente il Report/Panoramica mostrava un consumo diverso dalla mappa Mensile (es. 393 kWh invece di 464 kWh) pur usando la STESSA entità. Causa: al primo caricamento del Report il motore periodi non aveva ancora calcolato il delta del mese, così il valore ripiegava sul dato grezzo del contatore. Ora il Report forza il calcolo del motore e attende il risultato prima di mostrare i numeri: consumo, produzione, autosufficienza, badge e KPI coincidono con la mappa e con il pannello Energia di HA.

## [0.9.3] — 2026-07-18 (EN)

### Fixed
- **📊 Report vs map: consumption aligned** — for the current month the Report/Overview showed a consumption different from the Monthly map (e.g. 393 kWh instead of 464 kWh) despite using the SAME entity. Cause: on first Report load the period engine hadn't computed the month delta yet, so the value fell back to the raw counter reading. The Report now forces the engine computation and waits for the result before showing numbers: consumption, production, self-sufficiency, badges and KPIs match the map and HA's Energy panel.

## [0.9.2] — 2026-07-18

### Corretto
- **📊 Report mesi passati con contatori TOTALI: valori corretti** — con contatori cumulativi (es. Solarman total production) i mesi passati mostravano numeri sballati/raddoppiati (es. Giugno 1747 kWh) o identici tra mesi. Due bug si sommavano: (1) il fallback History prendeva l'ULTIMO valore del contatore nel mese (= cumulativo lifetime) invece della differenza ultimo−primo; (2) le statistiche mensili non venivano validate. Ora l'energia del mese è calcolata come delta del periodo (change del bucket mensile o differenza dei valori cumulativi), con controllo di plausibilità e fallback History corretto che fa la differenza. Ogni mese mostra il suo valore reale.

## [0.9.2] — 2026-07-18 (EN)

### Fixed
- **📊 Past-month Report with TOTAL counters: correct values** — with cumulative counters (e.g. Solarman total production) past months showed wrong/doubled numbers (e.g. June 1747 kWh) or identical values across months. Two bugs combined: (1) the History fallback took the LAST counter value in the month (= lifetime cumulative) instead of last−first difference; (2) monthly statistics were not validated. The month energy is now computed as the period delta (monthly bucket change or cumulative-value difference), with a plausibility check and a corrected History fallback that takes the difference. Every month shows its real value.

## [0.9.1] — 2026-07-18

### Corretto
- **📊 Mesi passati con valori identici** — Report/Panoramica di mesi diversi (es. Maggio e Giugno) mostravano gli stessi identici numeri di produzione e consumo quando l'entità mappata è un contatore TOTALE cumulativo. La lettura delle Long-Term Statistics prendeva il change "massimo" tra i punti e, in mancanza, ripiegava su max/state = valore lifetime del contatore (uguale per ogni mese). Ora somma i change di ogni bucket del periodo (come già fa il motore del mese corrente): il delta di ciascun mese è sempre corretto e distinto. Corregge sia i KPI sia i badge in alto.

## [0.9.1] — 2026-07-18 (EN)

### Fixed
- **📊 Past months showing identical values** — Report/Overview for different months (e.g. May and June) showed the exact same production and consumption when the mapped entity is a cumulative TOTAL counter. The Long-Term Statistics reader took the "maximum" change across points and, failing that, fell back to max/state = the counter lifetime value (same for every month). It now sums the change of each period bucket (as the current-month engine already does): each month delta is always correct and distinct. Fixes both KPIs and the top badges.

## [0.9.0] — 2026-07-18

### Aggiunto
- **💡 Gestione luci per stanza** — nuovo tab "Luci" nell'editor: crea le stanze, assegna ogni luce a una stanza con un menu a tendina e riordina sia le stanze sia le luci dentro ogni stanza con le frecce su/giù. Il popup Gestione Luci rispetta stanze e ordine impostati; le luci senza stanza finiscono in "Altre zone". Retrocompatibile: se non organizzi nulla, continua a raggruppare dal prefisso del nome ("Stanza - Dettaglio") come prima. Tutto si sincronizza tra dispositivi.

## [0.9.0] — 2026-07-18 (EN)

### Added
- **💡 Lights by room** — new "Lights" editor tab: create rooms, assign each light to a room via dropdown, and reorder both rooms and the lights inside each room with up/down arrows. The Lights popup honors the rooms and order you set; lights without a room go to "Other zones". Backward compatible: if you organize nothing, it keeps grouping by name prefix ("Room - Detail") as before. Everything syncs across devices.

## [0.8.6] — 2026-07-18

### Corretto
- **⚡ PRODUZIONE FV e tutti i sensori allineati** — la card KPI della Panoramica e il Dettaglio Dispositivo del Report leggevano il valore GREZZO del contatore (il totale lifetime, es. 11400 kWh) invece del delta del mese come già facevano il badge in alto (608 kWh) e la mappa. Ora ogni punto usa lo stesso motore periodi: produzione, consumo, autosufficienza, risparmio e ripartizioni sono coerenti ovunque, anche quando il sensore mappato è un contatore TOTALE.
- **🔌 Connessione da file scaricato (#10)** — il wizard usava sempre l'indirizzo della pagina (`location.host`): aprendo il file da un host che non è HA puntava all'indirizzo sbagliato e il collegamento falliva. Ora verifica connessione, sync e lettura entità usano l'URL di Home Assistant salvato o inserito nei campi del wizard (funziona identico con Nabu Casa e DuckDNS); se il file è aperto fuori da HA il messaggio d'errore indica l'host tentato.
- **💾 Download configurato riparato (#10)** — c'erano due sistemi di bake in conflitto e quello usato dal pulsante 💾 cercava marcatori inesistenti, iniettando un SECONDO blocco di configurazione che rompeva il file scaricato (riapriva il wizard). Ora un unico metodo sostituisce il blocco REALE tra i marcatori `CD_BAKED_START/END`, spezzati nel sorgente perché non possano auto-corrompersi. Verificato: il file scaricato ha un solo blocco config, token e URL vengono letti all'avvio (niente wizard), e ri-scaricandolo resta identico (nessun accumulo).

### Nota d'uso (Nabu Casa / DuckDNS)
- Il file scaricato con 💾 va messo in `/config/www` e aperto **da dentro Home Assistant** (`https://tuo-indirizzo/local/dashboard.html`): vale sia per Nabu Casa sia per DuckDNS — l'indirizzo con cui apri la pagina è già quello di HA, quindi collegamento e token integrato funzionano senza reinserire nulla.

## [0.8.6] — 2026-07-18 (EN)

### Fixed
- **⚡ PV PRODUCTION and all sensors aligned** — the Overview KPI card and the Report device detail read the RAW counter value (lifetime total, e.g. 11400 kWh) instead of the month delta already used by the top badge (608 kWh) and the map. Every spot now uses the same period engine: production, consumption, self-sufficiency, savings and splits are consistent everywhere, even with cumulative TOTAL sensors.
- **🔌 Connection from downloaded file (#10)** — the wizard always used the page address (`location.host`): opening the file from a non-HA host pointed to the wrong address and the connection failed. Verification, sync and entity loading now use the Home Assistant URL saved or entered in the wizard (identical for Nabu Casa and DuckDNS); if the file is opened outside HA the error states the attempted host.
- **💾 Baked download fixed (#10)** — two conflicting bake systems existed and the 💾 button looked for non-existent markers, injecting a SECOND config block that broke the downloaded file (reopening the wizard). A single method now replaces the REAL block between `CD_BAKED_START/END` markers, split in the source so they can't self-corrupt. Verified: the downloaded file has one config block, token and URL are read at startup (no wizard), and re-downloading stays identical.

## [0.8.5] — 2026-07-17
### Corretto
- ⚡ **Flussi allineati a HA**: l'ora in corso viene aggiunta SOLO se le statistiche sono davvero in ritardo (>65 min) — le versioni recenti di HA la includono già e il valore risultava gonfiato di ~2 kWh · 💾 **Download riparato ovunque**: anche il percorso del wizard usava le stringhe intere `</head>`/marker come bersaglio (ora spezzate in tutto il file) — rifai il download da un file pulito · 🎨 Tab dei piani centrati

## [0.8.5] — 2026-07-17 (EN)
### Fixed
- ⚡ **Flows aligned with HA**: the in-progress hour is added ONLY when statistics truly lag (>65 min) — recent HA already includes it and values were inflated by ~2 kWh · 💾 **Download fixed everywhere**: the wizard path also used whole `</head>`/marker strings as targets (now split file-wide) — redo the download from a clean file · 🎨 Centered floor tabs

## [0.8.4] — 2026-07-17

### 🐛 Corretto
- **💾 Download configurato non più corrotto (#10)** — la funzione di download colpiva il proprio codice sorgente (le stringhe `</head>` e i marker nel codice facevano da bersaglio della sostituzione): ora marker e chiusura head sono spezzati nel sorgente, impossibile auto-corrompersi. Chi ha un file scaricato rotto deve ripartire dal file pulito della release e rifare il download.
- **⚡ Ora in corso inclusa nei periodi** — le Long-Term Statistics escludono l'ora parziale: il motore ora aggiunge il delta dall'ultimo punto orario allo stato attuale del contatore. Il nodo CASA (e tutti i valori giorno/mese) combaciano col pannello Energia di HA.
- **🪄 Rilevamento su impianti già configurati** — "0 novità" non sembra più un errore: il riepilogo mostra "✅ Tutto già configurato (N elementi attivi)". Il rilevamento propone solo ciò che manca.
- **🎨 Card stanze** — nome su due righe senza troncamenti, °C ben allineato. I tab dei piani usano lo stesso stile pillola degli altri tab.

### ✨ Aggiunto
- **🏠 Logo del progetto** — `logo.png` e `icon.png` nel repo (usati da README e HACS).

## [0.8.4] — 2026-07-17 (EN)

### 🐛 Fixed
- **💾 Baked download no longer corrupted (#10)** — the download function was hitting its own source code (the literal `</head>` and markers acted as replacement targets): markers are now split in the source, self-corruption impossible. Broken downloads must be redone from a clean release file.
- **⚡ In-progress hour included in periods** — LTS exclude the partial hour: the engine now adds the delta from the last hourly point to the counter's current state. The HOME node (and all day/month values) match HA's Energy panel.
- **🪄 Detection on configured systems** — "0 new" no longer looks like an error: the summary shows "✅ Everything already configured (N active items)". Detection only proposes what's missing.
- **🎨 Room cards** — two-line names without truncation, aligned °C. Floor tabs use the same pill style as other tabs.

### ✨ Added
- **🏠 Project logo** — `logo.png` and `icon.png` in the repo (used by README and HACS).

## [0.8.3] — 2026-07-17

### ✨ Aggiunto
- **🪄 Rilevamento con riepilogo** — "Rileva tutto" ora dice esattamente **quante entità ha assegnato e dove**: pannello finale con conteggio per destinazione (entità sezioni, luci, clima, telecamere, stanze, avvisi) e totale, prima di aprire l'editor. Se le entità non sono ancora caricate, il wizard le legge da solo e aspetta (fino a 15s) invece di fermarsi con "Attendi il caricamento…".
- **🔍 Rilevamento per dominio e classe** — oltre ad aperture (device_class door/window/opening) e batterie (%), il quadro avvisi ora si riempie da solo anche con luci (`light.*`), clima e riscaldamento (`climate.*`, distinti fra condizionatori e termosifoni/TRV).
- **🎨 Card stanze completamente ridisegnate** — badge icona 58px col colore della stanza, striscia colorata in alto, temperatura enorme in gradiente (44px Oswald), pillola umidità 💧, badge comfort in alto a destra, hover con ombra colorata. Design pulito senza etichette ridondanti, ottimizzato anche per mobile.

## [0.8.3] — 2026-07-17 (EN)

### ✨ Added
- **🪄 Detection with summary** — "Detect all" now tells you exactly **how many entities were assigned and where**: final panel with per-destination counts (section entities, lights, climate, cameras, rooms, alerts) and a total, before opening the editor. If entities aren't loaded yet, the wizard fetches them itself and waits (up to 15s) instead of stopping with "Wait for entities…".
- **🔍 Domain & class detection** — besides openings (device_class door/window/opening) and batteries (%), the alerts board now auto-fills with lights (`light.*`), climate and heating (`climate.*`, split between AC units and radiators/TRVs).
- **🎨 Fully redesigned room cards** — 58px icon badge in the room color, colored top strip, huge gradient temperature (44px Oswald), 💧 humidity pill, comfort badge top-right, colored hover shadow. Clean label-free design, mobile-optimized.

## [0.8.2] — 2026-07-17

### ✨ Aggiunto
- **📅 Giornaliera derivata dai totali del mese** — se hai mappato solo il campo "mese" con un contatore TOTALE cumulativo, la mappa Giornaliera si popola da sola con il delta da mezzanotte della STESSA entità (vale per tutti i nodi: casa, solare, rete ↓↑, batteria ↓↑, boiler, wallbox, clima, nodi 1-2, anche dove i nomi giorno/mese non coincidono). Funziona anche al contrario: solo "oggi" mappato → il mese si ricava da lì.

### 🐛 Corretto
- **Nodi giornalieri nascosti** — le card/nodi alimentati dal motore periodi non vengono più nascosti da cdAutoHide come "non mappati"; dopo ogni refresh del motore le card ricompaiono da sole.

## [0.8.2] — 2026-07-17 (EN)

### ✨ Added
- **📅 Daily view derived from monthly totals** — if you only mapped the "month" field with a cumulative TOTAL counter, the Daily map auto-populates with the since-midnight delta of the SAME entity (all nodes: home, solar, grid ↓↑, battery ↓↑, boiler, wallbox, climate, nodes 1-2, including pairs whose day/month names differ). Works the other way too: only "today" mapped → the month is derived from it.

### 🐛 Fixed
- **Hidden daily nodes** — cards/nodes fed by the period engine are no longer hidden by cdAutoHide as "unmapped"; after every engine refresh cards reappear on their own.

## [0.8.1] — 2026-07-17

### 🐛 Corretto
- **📊 Mesi passati e Bilancio Anno finalmente sullo storico** — le statistiche venivano richieste a HA con i riferimenti interni `dm.*` (che HA non conosce) in più punti: ora tutte le richieste risolvono le entità reali e la risposta viene rimappata. Il Bilancio Anno inoltre stima il consumo dal bilancio energetico quando manca il contatore e, se le statistiche annuali sono vuote, parte almeno dai dati del mese corrente invece di "Dati non disponibili".
- **📉 Mesi senza statistiche** — la Panoramica di un mese passato senza alcun dato mostra un avviso chiaro invece di zeri sicuri.
- **💾 RAM dinamica** — il valore si adatta al sensore: % se è in percentuale, valore con la sua unità se è in MB/GB (con conversione automatica MB→GB), percentuale calcolata se c'è l'attributo total. Niente più "—" con la barra piena.

### ✨ Aggiunto
- **🏢 Icona per ogni piano** — nel form stanza c'è il campo icona del piano (con picker 😀): il tab del piano nelle Temperature la mostra al posto del 🏢 generico.
- **🎨 Stanze più belle** — icona della stanza grande (54px) in un badge colorato col colore della card, nome più evidente.
- **🔔 Avvisi raggruppati** — l'editor Avvisi è organizzato in sezioni richiudibili (Aperture, Batterie, Luci, Clima, Riscaldamento) col conteggio per gruppo.

## [0.8.1] — 2026-07-17 (EN)

### 🐛 Fixed
- **📊 Past months and Year Balance finally read history** — statistics were requested from HA with internal `dm.*` refs (unknown to HA) in several places: all requests now resolve real entities and remap the response. The Year Balance also estimates consumption from the energy balance when the meter is missing and, if yearly statistics are empty, starts from current-month data instead of "No data".
- **📉 Months without statistics** — the Overview of an empty past month shows a clear notice instead of confident zeros.
- **💾 Dynamic RAM** — the value adapts to the sensor: % if it's a percentage, value with its unit if it's MB/GB (automatic MB→GB conversion), computed percentage when a total attribute exists. No more "—" with a full bar.

### ✨ Added
- **🏢 Per-floor icons** — the room form has a floor-icon field (with 😀 picker): the floor tab in Temperatures shows it instead of the generic 🏢.
- **🎨 Prettier rooms** — big room icon (54px) in a colored badge matching the card color, bolder name.
- **🔔 Grouped alerts** — the Alerts editor is organized in collapsible sections (Openings, Batteries, Lights, Climate, Heating) with per-group counts.

## [0.8.0] — 2026-07-17 · ⭐ Major release

### ✨ Aggiunto
- **🧠 Motore periodi (sensori TOTALI)** — nei campi "oggi" e "mese" ora puoi mappare qualsiasi contatore, anche TOTALE cumulativo: i valori di giornaliera, mensile e Report vengono ricostruiti come delta del periodo tramite le Long-Term Statistics di HA (aggiornati all'avvio e ogni 5 minuti). Sparisce per sempre il nodo CASA con il totale lifetime al posto del mese. Con entità che si azzerano da sole il comportamento è identico: il motore è universale, anche per il Report del mese corrente.
- **🔍 Rilevamento automatico ancora più potente** — il dizionario ora riconosce decine di brand e integrazioni: Solarman, Fronius, Growatt, SolarEdge, Huawei, GoodWe, Sungrow, Victron, Enphase, SMA, Pylontech, Powerwall, evcc, Keba, Easee, Zappi, Daikin, Mitsubishi, MELCloud, Sensibo, Reolink, Tapo, Hikvision, Frigate, Shelly, Hue e molti altri.
- **🎨 Bottoni Salva coerenti** — nuovo stile dedicato (gradiente verde, ombra, feedback al tocco) per "Salva sezione", "Salva nodi mappa" e "Salva costi".

### 🐛 Corretto
- **Meteo: previsioni 7 giorni** — il popup ora usa la stessa catena di fallback dell'hero (entità mappata → weather.home → meteo interno): se l'hero funziona, funzionano anche le previsioni.
- **Meteo in tema scuro** — l'hero non è più un rettangolo bianco: sfondo notturno dedicato e testi leggibili.
- **Card che non ricompaiono** — dopo un salvataggio o la chiusura dell'editor le card delle entità appena mappate (es. CPU del MiniPC) riappaiono senza ricaricare la pagina.

### 📝 Note
- Le tab Sostituzioni, Testi ed Esporta non esistono più: tutto si gestisce da Sezioni/Carichi; il download della dashboard con token e configurazione integrati è l'icona 💾 nell'header dell'editor (risolve il token da reinserire su ogni dispositivo).
- README completamente riscritto.

## [0.8.0] — 2026-07-17 · ⭐ Major release (EN)

### ✨ Added
- **🧠 Period engine (TOTAL sensors)** — you can now map any counter, even cumulative TOTALS, into the "today"/"month" fields: daily, monthly and Report values are rebuilt as period deltas via HA Long-Term Statistics (refreshed at startup and every 5 minutes). The HOME node showing a lifetime total instead of the month is gone for good. Self-resetting entities behave identically: the engine is universal, including the current-month Report.
- **🔍 Even stronger auto-detection** — the dictionary now recognizes dozens of brands and integrations: Solarman, Fronius, Growatt, SolarEdge, Huawei, GoodWe, Sungrow, Victron, Enphase, SMA, Pylontech, Powerwall, evcc, Keba, Easee, Zappi, Daikin, Mitsubishi, MELCloud, Sensibo, Reolink, Tapo, Hikvision, Frigate, Shelly, Hue and many more.
- **🎨 Coherent Save buttons** — new dedicated style (green gradient, shadow, touch feedback) for "Save section", "Save map nodes" and "Save tariffs".

### 🐛 Fixed
- **Weather: 7-day forecast** — the popup now uses the same fallback chain as the hero (mapped entity → weather.home → internal weather): if the hero works, forecasts work.
- **Weather in dark theme** — the hero is no longer a white rectangle: dedicated night background and readable text.
- **Cards not reappearing** — after a save or closing the editor, cards for newly mapped entities (e.g. MiniPC CPU) reappear without reloading.

### 📝 Notes
- The Substitutions, Texts and Export tabs are gone: everything lives in Sections/Loads; downloading the dashboard with token and configuration baked in is the 💾 icon in the editor header (fixes re-entering the token on every device).
- README fully rewritten.

## [0.7.5] — 2026-07-17

### ✨ Aggiunto
- **💾 Salva sezione** — in fondo a ogni sezione di ⚙️ → Sezioni c'è ora un bottone che raccoglie e salva TUTTI i campi in un colpo. Risolve le entità "sparite": su mobile l'evento di salvataggio automatico può non scattare se si chiude il popup con la tastiera aperta; ora la digitazione manuale è al sicuro (e ogni salvataggio parte subito verso la sincronizzazione).
- **📊 Consumo totale stimato** — se l'entità del consumo mensile non è configurata, il Report la ricava dal bilancio energetico (prodotto − immesso + prelevato + batteria scaricata − caricata) e la mostra col simbolo ≈. A cascata diventano coerenti autosufficienza, "Senza FV", risparmio e la ripartizione ☀️ solare / 🔌 rete di ogni dispositivo (prima tutto risultava "100% solare" con 0€ risparmiati).

### 🐛 Corretto
- **Confronto settimanale nei mesi passati** — mostrava 0.0/0.0: la card ora compare solo nel mese corrente.
- **Mesi senza dati principali** — se un mese non ha né produzione né consumi ma i contatori dei dispositivi riportano energia, un avviso spiega che quei valori derivano dallo storico e possono includere periodi precedenti.

## [0.7.5] — 2026-07-17 (EN)

### ✨ Added
- **💾 Save section** — at the bottom of every ⚙️ → Sections accordion a button now collects and saves ALL fields at once. Fixes "vanishing" entities: on mobile the auto-save event may never fire when closing the popup with the keyboard open; manually typed entities are now safe (and every save immediately pushes to sync).
- **📊 Estimated total consumption** — if the monthly consumption entity is not configured, the Report derives it from the energy balance (produced − exported + imported + battery discharged − charged) and shows it with ≈. Self-sufficiency, "Without PV", savings and each device's ☀️ solar / 🔌 grid split become coherent (previously everything showed "100% solar" with €0 saved).

### 🐛 Fixed
- **Weekly comparison in past months** — it showed 0.0/0.0: the card now only appears in the current month.
- **Months without main data** — if a month has neither production nor consumption but device meters report energy, a notice explains those values come from history and may include earlier periods.

## [0.7.4] — 2026-07-17

### ✨ Aggiunto
- **🗺️ Somma automatica dei sottocarichi sul nodo** — se un nodo della mappa ha un gruppo di carichi assegnato e nessun sensore, il valore mostrato è la somma live delle potenze dei suoi sottocarichi. Con un sensore impostato, il nodo mostra quel valore (prima l'entità del nodo veniva ignorata).
- **📊 Report Analisi automatico** — senza voci configurate, il Report si popola da solo con i consumi mensili dei nodi della mappa già mappati (Wallbox, Clima, Boiler, nodi 1-2), con i nomi e le icone personalizzati dei nodi. Le voci manuali, se presenti, hanno la precedenza.
- **😀 Picker delle icone** — accanto a ogni campo icona (nodi, gruppi, carichi, voci Report) c'è ora un bottone che apre una griglia di emoji: basta toccare quella desiderata.
- **🏢 Piani come tab nelle Temperature** — i piani creati nelle stanze diventano tab in alto con la temperatura media del piano in evidenza; toccando un tab si vedono le stanze di quel piano.

### 🐛 Corretto
- **Card dei gruppi rimosse dalla sezione Energia** — i gruppi si aprono dai nodi della mappa flussi, le card duplicate sotto la mappa non compaiono più.
- **Doppia lente 🔍 sul campo sensore dei nodi** — rimosso il bottone duplicato.

## [0.7.4] — 2026-07-17 (EN)

### ✨ Added
- **🗺️ Automatic subload sum on nodes** — if a map node has a load group assigned and no sensor, the value shown is the live sum of its subloads' power. With a sensor set, the node shows that value (previously the node entity was ignored).
- **📊 Automatic Analysis Report** — with no entries configured, the Report auto-populates with the monthly consumption of the mapped flow-map nodes (Wallbox, Climate, Boiler, nodes 1-2), using the nodes' custom names and icons. Manual entries take precedence.
- **😀 Icon picker** — next to every icon field (nodes, groups, loads, Report entries) a button opens an emoji grid: just tap the one you want.
- **🏢 Floors as tabs in Temperatures** — floors created in rooms become tabs at the top showing the floor's average temperature; tapping a tab shows that floor's rooms.

### 🐛 Fixed
- **Group cards removed from the Energy section** — groups open from the flow-map nodes; the duplicate cards under the map are gone.
- **Double 🔍 picker on node sensor fields** — duplicate button removed.

## [0.7.3] — 2026-07-17

### 🐛 Corretto
- **🔌 Gruppi di carichi finalmente funzionanti** — tre bug si sommavano: il blocco che caricava i gruppi personalizzati all'avvio era andato perso (il menu mostrava solo Cucina/Lavanderia e i carichi aggiunti ai gruppi venivano ignorati), la funzione delle card in Energia non era mai stata inclusa nel file pubblicato (errore silenzioso alla creazione del gruppo) e l'editor si aggiornava su un tab inesistente. Ora: crei il gruppo → appare subito nel menu, nelle card Energia e si sincronizza tra dispositivi.
- **📊 Report Analisi immediato** — le voci aggiunte in ⚙️ → Carichi → "Report Analisi — voci" ora compaiono nel Report all'istante, senza dover ricaricare la pagina; la lista nell'editor si ridisegna correttamente dopo ogni aggiunta/rimozione.

## [0.7.3] — 2026-07-17 (EN)

### 🐛 Fixed
- **🔌 Custom load groups finally working** — three stacked bugs: the block loading custom groups at startup had been lost (the menu only showed Kitchen/Laundry and loads added to groups were ignored), the Energy cards function was never included in the published file (silent error on group creation) and the editor refreshed a non-existent tab. Now: create a group → it instantly appears in the menu, in the Energy cards and syncs across devices.
- **📊 Instant Analysis Report** — entries added in ⚙️ → Loads → "Analysis Report — entries" now show up in the Report immediately, no page reload needed; the editor list redraws correctly after every add/remove.

## [0.7.2] — 2026-07-16

### 🐛 Corretto
- **✏️ Matita delle stanze che non faceva nulla** — leggeva una lista diversa da quella mostrata (config sincronizzate/integrate): ora modifica, riordino e cestino operano sempre sulla lista reale, e il form si apre e si riempie al tocco.
- **🔍 Lente anche sui sensori dei nodi mappa** e **nome del nodo precompilato** — il nome ora appare come testo reale modificabile, non come suggerimento grigio.
- **Select dei carichi popolato dai TUOI gruppi** — Cucina/Lavanderia compaiono solo se non hai creato gruppi personalizzati.
- **📊 Report senza voci: guida corretta** — il messaggio ora indirizza a ⚙️ → Carichi → Report (il vecchio rimando al wizard non esisteva più) e ricorda che funzionano sia entità mensili che TOTALI.

## [0.7.1] — 2026-07-16

### 🐛 Corretto
- **✏️ Matita e frecce ▲▼ sulle stanze anche nell'editor** — modifica (nome, icona, Piano, sensori) e riordino senza cancellare.
- **🗺️ Nodi mappa con titoli neutri** — "Nodo mappa 1 — nome attuale: …": il nome è libero, ora si vede.
- **📌 La card Barra di navigazione evidenzia davvero la scelta attiva** — il selettore del tema la ripuliva per errore.

## [0.7.0] — 2026-07-16 · "One Editor"

### 🚀 Nuova architettura di configurazione
- **Il wizard finisce in 3 passi**: connessione → nome → sezioni, poi "🪄 Rileva tutto e apri l'editor".
- **L'editor è l'unico luogo di configurazione** — luci (nuovo), sezioni con etichette rinominabili e lente 🔍, stanze con Piano, clima, telecamere, avvisi, azioni rapide, dispositivi, Report, gruppi carichi e nodi mappa.
- **♾️ Giornaliero/mensile/annuale calcolati dai TOTALI** — collega le entità cumulative (le stesse del tab Energia di HA): la dashboard calcola oggi/mese/anno dalla cronologia. Niente utility_meter.

## [0.6.8] — 2026-07-16

### ✨ Migliorato
- Etichette rinominabili ora visibili (tratteggio+matita) · Report anche in editor→Sezioni · Stanze aggiungibili dall'editor (con Piano) · card navbar con stato attivo · schede editor su più righe.

## [0.6.7] — 2026-07-16

### 🐛 Corretto
- **Tema che non si salvava mai** (errore interno di salvataggio) · **Barra fissa mai attiva su PC** (regola nel blocco solo-telefoni) · **Gruppi carichi spariti al ricaricamento**.

### ✨ Aggiunto
- Lente 🔍 ed etichette ✏️ nell'editor · **🏢 Stanze per piano** con raggruppamento automatico.

## [0.6.6] — 2026-07-16

### 🐛 Corretto
- **Wizard bloccato da "Importate N impostazioni"** (import in loop: ora solo su dispositivi nuovi) · **Tema e Navbar sovrascritti dalla sync** (ora preferenze per-dispositivo).

### ✨ Aggiunto
- Voci Report nell'editor · nodi mappa con opzione "apre lo storico".

## [0.6.5] — 2026-07-16

### 🐛 Corretto (importante)
- **Wizard bloccato dal messaggio "Importate N impostazioni"** — la sincronizzazione importava la configurazione a OGNI apertura del wizard, ricaricando la pagina in loop: ora l'import automatico avviene solo su un dispositivo nuovo (senza configurazione locale).
- **Tema e Barra di navigazione che "non funzionavano"** — le scelte venivano sovrascritte dall'import: ora tema e barra sono preferenze del singolo dispositivo, mai sincronizzate.

### ✨ Aggiunto
- **📊 Voci del Report anche nell'editor** — ⚙️ → Configura Entità → Carichi: aggiungi/rimuovi le voci del Report senza passare dal wizard.
- **📈 Nodi mappa senza popup** — nel menu di ogni nodo la prima opzione è "Nessun popup — apre lo storico" del sensore scelto.
- **🗺️ TUTTI i nodi sotto la casa personalizzabili** — anche Boiler, Wallbox e Clima si rinominano (nome, icona, sensore, gruppo) da ⚙️ → Carichi → Nodi della mappa, come Lavanderia e Cucina.

### 🐛 Corretto
- **Badge "Allarme!" senza antifurto configurato** *(segnalazione Dima)* — il controllo di rimozione non riconosceva le installazioni senza antifurto: ora il banner sparisce davvero.
- **Nodo Casa che apriva popup incoerenti** *(segnalazione Tinux)* — click su nodi con entità non configurata: ora nessuna azione invece di finestre sbagliate.

## [0.6.4] — 2026-07-16

### ✨ Aggiunto
- **✏️ Modifica senza cancellare** — le stanze si modificano con la matita (form precompilato, 💾 Salva) e si **riordinano** con le frecce ▲▼. *(grazie Francesco!)*
- **☁️ Import automatico della configurazione** — su un nuovo dispositivo la config salvata su HA viene applicata da sola, senza domande.

### 🐛 Corretto
- **Barra di navigazione "Fissa" ora funziona davvero** — la logica valeva solo su mobile: ora la scelta si applica anche su PC/tablet (e la scelta attiva è evidenziata).
- **Tema che non rispondeva** — la card della barra aveva rotto la struttura della pagina Config: riparata.
- **Avvisi persi al refresh** *(issue #5, definitivo)* — le modifiche non ancora sincronizzate sono ora protette e vengono inviate subito.
- **Confronto settimanale a zero** *(issue #6)* — ora usa le entità configurate dall'utente (produzione o consumo giornaliero) invece di un sensore fisso; se non configurate mostra "—".

## [0.6.2] — 2026-07-16

### ✨ Migliorato
- **📊 Report Analisi a voci libere** — niente più nomi blindati: nel wizard aggiungi le TUE voci con nome, icona ed entità a piacere; il selettore del Report le usa automaticamente.
- **🗺️ Nodi dei flussi personalizzabili** — i primi due gruppi di carichi creati sostituiscono Lavanderia/Cucina nella mappa: nome, icona, popup e potenza (somma del gruppo) tuoi.
- **🔔 Avvisi automatici e puliti** — luci, clima e riscaldamento del Quadro Avvisi si popolano da soli dalle sezioni configurate; i popup mostrano solo ciò che richiede attenzione (accese/aperte/scariche).

- **✏️ Etichette rinominabili nel wizard** — ogni voce degli slot (Energia, EV, Boiler…) si rinomina toccandola: niente più nomi imposti.
- **📊 "Attività Dispositivi" segue le tue voci** — la lista del Report mostra solo i dispositivi che hai configurato; senza configurazione resta vuota (niente elenchi finti a zero).

### 🐛 Corretto
- **Doppio accordion "Dispositivi" nel wizard** — rimosso il duplicato.
- **Barra di navigazione: il pulsante "Fissa" non applicava la scelta** dalla pagina Config; sistemata anche la card (era fuori layout).
- **Editor più leggibile su desktop** — finestra più larga e schede su più righe (niente più tagli).

## [0.6.1] — 2026-07-16

### ✨ Aggiunto
- **📌 Barra di navigazione fissa o a scomparsa** — nuova opzione nel wizard (step Sezioni) e in ⚙️ Config.

### 🐛 Corretto
- **Tab "Carichi" vuota nell'editor** *(issue #4)* — risolto su installazioni nuove.

## [0.6.0] — 2026-07-16

### ✨ Aggiunto
- **🔌 Gruppi di carichi personalizzati** *(issue #4)* — ⚙️ → Configura Entità → Carichi: crea i tuoi gruppi ("Garage", "Piano Terra"…), aggiungici i dispositivi e ottieni card dedicate nella sezione Energia con contatore attivi e popup.
- **📊 Report Analisi configurabile** *(issue #6)* — i consumi mensili per dispositivo (lavatrice, asciugatrice, forno…) sono ora collegabili dal wizard: nuovo accordion "Report Analisi" con lente 🔍 e rilevamento automatico. Fine dei valori a zero.

### 🐛 Corretto
- **Avvisi che sparivano al refresh** *(issue #5)* — una corsa tra salvataggio locale e sincronizzazione cloud poteva sovrascrivere le modifiche appena fatte: ora ogni modifica locale ha sempre priorità.

## [0.5.2] — 2026-07-16

### 🐛 Corretto *(issue #3 — grazie per le segnalazioni!)*
- **Avvisi aggiunti che sparivano** — le unità clima sovrascrivevano il gruppo avvisi Clima/Riscaldamento cancellando le aggiunte manuali; ora le vostre voci vengono sempre rispettate.
- **Avvisi nell'editor senza reload** — le entità aggiunte al Quadro Avvisi ora compaiono e contano subito, senza ricaricare.
- **Meteo che spariva dopo pochi secondi** — un riferimento interno non configurato bloccava il fallback verso il meteo configurato dall'utente: ora il widget resta visibile.

## [0.5.1] — 2026-07-16

### 🐛 Corretto
- **Popup gruppo luci che mostrava tutte le luci** — dopo un attimo il popup di un gruppo personalizzato veniva rigenerato senza filtro dall'aggiornamento automatico: ora filtro e titolo del gruppo vengono mantenuti.

## [0.5.0] — 2026-07-16

### ✨ Novità principali
- **🏠 Rilevamento dalle Aree di Home Assistant** — il 🪄 ora legge il registro ufficiale di HA: luci nominate "Stanza - Nome" (raggruppamento automatico), una card stanza per ogni Area con temperatura e umidità abbinate dall'area (non più dal nome), clima e telecamere già intitolati con la loro stanza. Precisione da integrazione, semplicità di un file.
- **☁️ Configurazione sincronizzata tra dispositivi** — la config viene salvata sul tuo utente Home Assistant: configuri sul telefono e il tablet si allinea da solo al prossimo avvio (e viceversa). Vale per wizard ed editor; al primo avvio su un nuovo dispositivo basta il token e tutto torna.
- **⚡ Flussi energia puliti** — i nodi Wallbox/Cucina/Lavanderia/Boiler/Clima spariscono se non configurati e si attenuano (flusso fermo) quando il carico è a riposo.

## [0.4.3] — 2026-07-16

### 🐛 Corretto
- **Menu autocomplete invasivo su mobile** — toccando un campo entità, Android apriva l'elenco nativo con tutte le entità sopra la tastiera. Rimosso ovunque: ora i campi sono a scrittura libera e la scelta guidata avviene solo con la lente 🔍 (lista completa + ricerca), presente su tutti i campi del wizard: sezioni, avvisi, dispositivi, stanze, clima e telecamere.

## [0.4.2] — 2026-07-15

### ✨ Migliorato
- **⚡ Form Azioni rapide ripensato** — "💡 Popup luci — scegli TU le luci" è ora la prima scelta e il flusso è guidato: nome → Aggiungi → selezione luci con ricerca. Il campo entità appare solo quando serve (toggle/script/scena) e ha il pulsante 🔍. Un suggerimento sotto il form spiega sempre il passo successivo.

## [0.4.1] — 2026-07-15

### ✨ Migliorato
- **🔍 Selettore entità con ricerca** — accanto a ogni campo dello step "Collega le tue entità" c'è ora un pulsante 🔍 che apre l'elenco completo delle entità del tuo HA con ricerca live: tocca per scegliere, niente più digitazione a mano su mobile.
- **✏️ Modifica dei gruppi luci** — le azioni rapide "Gruppo luci" ora si modificano: matita accanto al gruppo (nel wizard e nell'editor) per aggiungere o togliere luci, con le attuali già spuntate.

## [0.4.0] — 2026-07-15

### 🛡️ Affidabilità
- **La dashboard funziona anche se il CDN dei grafici è bloccato** (Pi-hole, AdGuard, reti filtrate, tablet offline): prima un CDN irraggiungibile impediva l'avvio di wizard e configurazione; ora tutto funziona e solo i grafici risultano non disponibili.

### ✨ Nuova funzionalità — 🔌 Dispositivi personalizzati
*(proposta da @magli74 nella issue #2)*
- **Card in Home per qualsiasi elettrodomestico o dispositivo**: lavastoviglie, asciugatrice, stufa a pellet, scaldino, irrigazione a zone… Per ognuno configuri: nome, icona, **switch** (accensione dalla card), **sensore potenza** (stato "In funzione" da soglia 5W — perfetto per prese smart su apparecchi non smart) e **sensore valore** (livello pellet, temperatura…).
- Aggiungibili dal wizard (accordion 🔌 Dispositivi) e dall'editor; tap sulla card → grafico storico; il blocco sparisce se non ne configuri.
- Il cronotermostato si aggiunge come **unità clima** (è un `climate.*`): card completa con temperature e controlli.

## [0.3.15] — 2026-07-15

### 🐛 Corretto
- **Temperature nelle card clima** *(issue #2)* — l'aggiornamento delle card clima è ora autonomo (proprio ciclo, rete di sicurezza ogni 20s): le temperature compaiono sulle card senza dover aprire il popup.
- **Allarme in "CARICAMENTO" nella pagina Sicurezza** *(issue #2)* — se la centrale non è configurata, il blocco allarme sparisce e la pagina mostra solo le telecamere.
- **Popup lavatrice per non smart** *(issue #2)* — programma/centrifuga/temperatura nascosti se non configurati: resta stato (anche da soglia watt) e presa.

### 🗺️ In roadmap
- **Elettrodomestici personalizzati** (lavastoviglie, asciugatrice, stufa a pellet, scaldino…): card generiche con switch + sensore potenza/livello — grazie a Fabrizio per la proposta!

## [0.3.14] — 2026-07-15

### 🐛 Corretto
- **Contatori del Quadro Avvisi incoerenti coi popup** — i contatori (luci accese, clima attivi, aperture, batterie scariche) ora sono **calcolati dalla dashboard sugli stessi elementi che vedi nei popup**: il numero sulla card e la lista combaciano sempre, su qualsiasi installazione. I vecchi campi "Contatore…" non servono più e sono stati rimossi.
- **Contatore "Clima attivi"** ora conta le TUE unità clima configurate (condizionatori → Clima, termosifoni → Riscaldamento).
- **Rilevamento aperture** — esclusi i sensori "bypass" dei termosifoni (rumore).

## [0.3.13] — 2026-07-15

### ✨ Aggiunto
- **☁️ Sincronizzazione multi-dispositivo** *(issue #1)* — la configurazione ora si salva automaticamente su Home Assistant. Su un nuovo dispositivo basta inserire il token: il wizard trova la configurazione esistente e propone di importarla — dashboard identica ovunque, senza rifare nulla. Pulsanti manuali "Salva su HA / Carica da HA" in Configura Entità → Esporta.

### 🐛 Corretto
- **Card clima/stanze vuote al primo caricamento** *(issue #1)* — su dispositivi lenti gli stati arrivavano prima della costruzione delle card, che restavano su "SPENTO/--°" finché qualcosa non cambiava. Ora gli stati vengono applicati subito dopo la costruzione.

## [0.3.12] — 2026-07-15

### ✨ Aggiunto
- **💡 Gruppi luci personalizzati** *(issue #2)* — nuova azione rapida "Gruppo luci": scegli nome e quali luci includere (selettore con ricerca) e ottieni un popup dedicato. Crea "Piano Terra", "Giardino", "Camere"… ognuno con le sue luci.
- **🔍 Ricerca nella scelta luci** *(issue #2)* — campo di ricerca live nello step Luci del wizard: filtra per nome o entità.

### 🐛 Corretto
- **Banner antifurto in "Caricamento…"** *(issue #2)* — se l'allarme non è configurato, il banner antifurto viene rimosso dalla Home (e il meteo non configurato ora lo dichiara chiaramente).
- **Conflitto interno nel wizard** — luci e slot condividevano la stessa struttura dati e potevano sovrascriversi a vicenda: separati definitivamente.

## [0.3.11] — 2026-07-15

### ✨ Migliorato
- **🪄 Badge "auto" sui campi rilevati** — ogni entità compilata dal rilevamento automatico è evidenziata in verde con etichetta 🪄: vedi esattamente cosa è stato riconosciuto. Modificando il campo, il badge scompare.
- **🎯 Soglia adattiva** — gli slot con etichetta breve (es. "Centrale allarme") ora vengono riconosciuti; nuovi sinonimi per solare termico e lavatrice. Sezioni prima scoperte ora rilevate.

## [0.3.10] — 2026-07-15

### ✨ Migliorato
- **🪄 Auto-rilevamento v3** — riscritto il motore di matching: riconoscimento per parole intere (niente più errori da sottostringhe casuali), distinzione dei periodi (un sensore "mensile" non viene mai proposto per un dato "di oggi"), nessuna entità assegnata due volte, supporto a sigle corte (CPU, RAM, SOC). Nei test: da 14 a 50+ riconoscimenti con ~94% di precisione.

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
