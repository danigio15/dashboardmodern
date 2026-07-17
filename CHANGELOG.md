# Changelog

🇮🇹 Italiano · [🇬🇧 English below](#-english)

Il formato segue [Keep a Changelog](https://keepachangelog.com/it/) e il versionamento [SemVer](https://semver.org).

---

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

## [0.8.2] — 2026-07-17

### ✨ Aggiunto
- **📅 Derivazione giornaliera automatica** — se un campo "oggi" non è mappato ma il corrispondente "mese" sì (il caso tipico: contatore TOTALE inserito solo nel campo mese), il valore di oggi viene calcolato dalla STESSA entità come delta da mezzanotte. Vale per tutte le coppie mese→giorno (casa, solare, boiler, wallbox, clima, nodi 1-2) incluse le tre con nomi diversi (rete prelevata/immessa, batteria scaricata). Un campo "oggi" mappato esplicitamente ha sempre la precedenza. In pratica: basta inserire i totali nei campi mese e la dashboard ricostruisce da sola giornaliera, mensile e Report.

## [0.8.2] — 2026-07-17 (EN)

### ✨ Added
- **📅 Automatic daily derivation** — if a "today" field is not mapped but its "month" counterpart is (the typical case: a TOTAL counter entered only in the month field), today's value is computed from the SAME entity as a delta since midnight. Applies to every month→day pair (home, solar, boiler, wallbox, climate, nodes 1-2) including the three with different stems (grid import/export, battery discharged). An explicitly mapped "today" field always wins. In short: enter your totals in the month fields and the dashboard rebuilds daily, monthly and Report on its own.

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

## [0.3.14] — 2026-07-15

### 🐛 Corretto — coerenza contatori/popup
- **Contatori del Quadro Avvisi e popup ora combaciano SEMPRE** — contatori e liste sono calcolati dalla stessa fonte (le entità configurate nella dashboard), non più da sensori esterni. Fine dei "CLIMA 4" con popup vuoto.
- **Popup aperture/batterie a due sezioni** — prima "⚠️ APERTE/SCARICHE (N)" (esattamente ciò che conta il numero), poi "✓ TUTTO OK".
- **Clima attivi** contati dalle unità clima configurate (condizionatori → Clima, termosifoni → Riscaldamento).
- **Meteo non configurato** — il widget viene nascosto del tutto (niente più "UNAVAILABLE --°").

## [0.3.13] — 2026-07-15

### 🐛 Corretto — CRITICO
- **Dashboard che non si aggiornava con configurazione parziale** *(issues #1 e #2 — il "non vedo nulla")* — un riferimento non configurato poteva interrompere l'aggiornamento dell'intera interfaccia: card clima "spente" coi puntini anche se configurate, sezioni ferme. Ora i riferimenti non mappati sono innocui e tutto il resto si aggiorna sempre. **Dopo l'update rifate un giro di wizard (7 tap sul titolo) se avevate configurato con versioni precedenti.**

### ✨ Aggiunto
- **🔋 Popup batterie completo** *(issue #2)* — mostra TUTTE le batterie con la percentuale, le più scariche in cima (🪫 rosso ≤20%).
- **🚪 Popup aperture completo** *(issue #2)* — tutte le porte/finestre con stato APERTA/Chiusa, le aperte in cima.
- **🧺 Lavatrici non smart** *(issue #2)* — nuovo campo "Potenza presa lavatrice": collega la presa smart e lo stato (in funzione/spenta) è derivato dai watt (soglia 5W).

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

## [0.7.2] — 2026-07-16

### 🐛 Fixed
- **✏️ Rooms pencil doing nothing** — it read a different list from the one shown (synced/baked configs): edit, reorder and delete now always operate on the real list, and the form opens and fills on tap.
- **🔍 Picker on map-node sensors too** and **node name pre-filled** — the name now appears as real editable text, not a grey hint.
- **Loads select populated by YOUR groups** — Kitchen/Laundry only appear if you have no custom groups.
- **📊 Report with no entries: correct guidance** — the message now points to ⚙️ → Loads → Report (the old wizard reference no longer existed) and reminds that both monthly and TOTAL entities work.

## [0.7.1] — 2026-07-16

### 🐛 Fixed
- **✏️ Pencil and ▲▼ arrows on rooms in the editor** · **🗺️ neutral map-node titles** · **📌 Navigation bar card now truly highlights the active choice** (the theme selector was clearing it).

## [0.7.0] — 2026-07-16 · "One Editor"

### 🚀 New configuration architecture
- **3-step wizard** → "🪄 Detect everything and open the editor". **The editor is the single configuration place** (lights new, renamable labels, 🔍 picker, rooms with Floor, Report, load groups, map nodes).
- **♾️ Daily/monthly/yearly computed from TOTALS** — link your cumulative entities: the dashboard computes periods from history. No utility_meter.

## [0.6.8] — 2026-07-16
- Visible renamable labels · Report in editor→Sections · rooms addable from editor · navbar active state · multi-row tabs.

## [0.6.7] — 2026-07-16
- **Fixed**: theme never saving · fixed bar never active on PC · load groups disappearing on reload. **Added**: 🔍/✏️ in the editor · 🏢 rooms by floor.

## [0.6.6] — 2026-07-16
- **Fixed**: wizard locked by sync import loop · theme/navbar overwritten by sync. **Added**: Report entries in editor · map nodes "opens history" option.

## [0.6.5] — 2026-07-16

### 🐛 Fixed (important)
- **Wizard locked by the "Imported N settings" message** — sync imported the configuration at EVERY wizard opening, reloading in a loop: automatic import now happens only on a fresh device (no local configuration).
- **Theme and Navigation bar "not working"** — choices were being overwritten by the import: theme and bar are now per-device preferences, never synced.

### ✨ Added
- **📊 Report entries in the editor too** — ⚙️ → Configure Entities → Loads: add/remove Report entries without the wizard.
- **📈 Map nodes without popup** — each node's menu now starts with "No popup — opens history" of the chosen sensor.
- **🗺️ ALL nodes under the house are customizable** — Boiler, Wallbox and Climate can be renamed too (name, icon, sensor, group) via ⚙️ → Loads → Map nodes, like Laundry and Kitchen.

### 🐛 Fixed
- **"Alarm!" badge without a configured alarm** *(reported by Dima)* — the removal check missed unconfigured installs: the banner now truly disappears.
- **Home node opening wrong popups** *(reported by Tinux)* — clicking nodes with unconfigured entities now does nothing instead of showing mismatched windows.

## [0.6.4] — 2026-07-16

### ✨ Added
- **✏️ Edit without deleting** — rooms can be edited via pencil (pre-filled form, 💾 Save) and **reordered** with ▲▼ arrows. *(thanks Francesco!)*
- **☁️ Automatic config import** — on a new device the config saved on HA is applied silently, no prompts.

### 🐛 Fixed
- **"Fixed" navigation bar now really works** — the logic was mobile-only: the choice now applies on PC/tablet too (active choice highlighted).
- **Unresponsive theme** — the nav card had broken the Config page structure: repaired.
- **Alerts lost on refresh** *(issue #5, final)* — unsynced local changes are now protected and pushed immediately.
- **Weekly comparison at zero** *(issue #6)* — now uses the user's configured entities (daily production or consumption) instead of a fixed sensor; shows "—" if unconfigured.


## [0.6.2] — 2026-07-16

### ✨ Improved
- **📊 Free-form Analysis Report** — no more locked names: add YOUR entries (name, icon, entity) from the wizard; the Report selector uses them automatically.
- **🗺️ Customizable flow nodes** — the first two load groups you create replace Laundry/Kitchen on the map: your name, icon, popup and power (group sum).
- **🔔 Automatic, clean alerts** — lights, climate and heating populate themselves from your sections; popups only show what needs attention (on/open/low).

- **✏️ Renamable labels in the wizard** — every slot label (Energy, EV, Boiler…) can be renamed by tapping it: no more imposed names.
- **📊 "Device Activity" follows your entries** — the Report list only shows devices you configured; unconfigured means empty (no fake zero rows).

### 🐛 Fixed
- **Duplicate "Devices" accordion in the wizard** — removed.
- **Navigation bar: the "Fixed" button did not apply** from the Config page; the card layout was also fixed.
- **More readable editor on desktop** — wider window and multi-row tabs (no more clipping).

## [0.6.1] — 2026-07-16

### ✨ Added
- **📌 Fixed or auto-hide navigation bar** — new option in the wizard (Sections step) and in ⚙️ Config.

### 🐛 Fixed
- **Empty "Loads" tab in the editor** *(issue #4)* — fixed on fresh installs.

## [0.6.0] — 2026-07-16

### ✨ Added
- **🔌 Custom load groups** *(issue #4)* — ⚙️ → Configure Entities → Loads: create your own groups ("Garage", "Ground Floor"…), add devices and get dedicated cards in the Energy section with active counter and popup.
- **📊 Configurable Analysis Report** *(issue #6)* — monthly per-device energy (washer, dryer, oven…) can now be linked from the wizard: new "Analysis Report" accordion with 🔍 picker and auto-detection. No more zeros.

### 🐛 Fixed
- **Alerts disappearing on refresh** *(issue #5)* — a race between local save and cloud sync could overwrite just-made changes: local edits now always win.

## [0.5.2] — 2026-07-16

### 🐛 Fixed *(issue #3 — thanks for the reports!)*
- **Added alerts disappearing** — climate units were overwriting the Climate/Heating alert group, wiping manual additions; your entries are now always preserved.
- **Editor alerts without reload** — entities added to the Alerts Panel now appear and count immediately, no reload needed.
- **Weather vanishing after a few seconds** — an unconfigured internal reference blocked the fallback to the user-configured weather: the widget now stays visible.

## [0.5.1] — 2026-07-16

### 🐛 Fixed
- **Light-group popup showing all lights** — after a moment the custom group popup was regenerated without its filter by the auto-refresh: group filter and title are now preserved.

## [0.5.0] — 2026-07-16

### ✨ Highlights
- **🏠 Detection from Home Assistant Areas** — 🪄 now reads HA's official registry: lights named "Room - Name" (auto grouping), one room card per Area with temperature and humidity paired by area (no longer by name), climate and cameras titled with their room. Integration-grade precision, single-file simplicity.
- **☁️ Config synced across devices** — the configuration is stored on your Home Assistant user: set up on your phone and the tablet aligns on next start (and vice versa). Works for wizard and editor; on a new device just enter the token and everything comes back.
- **⚡ Clean energy flows** — Wallbox/Kitchen/Laundry/Boiler/Climate nodes disappear when not configured and dim (flow paused) when the load is idle.

## [0.4.3] — 2026-07-16

### 🐛 Fixed
- **Invasive autocomplete menu on mobile** — tapping an entity field made Android open the native list of all entities above the keyboard. Removed everywhere: fields are now free-typing and guided selection happens only via the 🔍 button (full list + search), now available on every wizard field: sections, alerts, devices, rooms, climate and cameras.

## [0.4.2] — 2026-07-15

### ✨ Improved
- **⚡ Quick Actions form redesigned** — "💡 Lights popup — YOU pick the lights" is now the first choice with a guided flow: name → Add → searchable light selection. The entity field only appears when needed (toggle/script/scene) and has the 🔍 button. A hint under the form always explains the next step.

## [0.4.1] — 2026-07-15

### ✨ Improved
- **🔍 Entity picker with search** — every field in the "Link your entities" step now has a 🔍 button opening the full list of your HA entities with live search: tap to pick, no more manual typing on mobile.
- **✏️ Edit light groups** — "Light group" quick actions are now editable: pencil next to the group (wizard and editor) to add or remove lights, current ones pre-ticked.

## [0.4.0] — 2026-07-15

### ✨ New feature — 🔌 Custom appliances
*(proposed by @magli74 in issue #2)*
- **Home cards for any appliance or device**: dishwasher, dryer, pellet stove, bathroom heater, zone irrigation… For each you configure: name, icon, **switch** (toggle from the card), **power sensor** ("Running" state from a 5W threshold — perfect for smart plugs on non-smart appliances) and **value sensor** (pellet level, temperature…).
- Add them from the wizard (🔌 Appliances accordion) or the editor; tap the card → history chart; the block disappears if none are configured.
- A thermostat should be added as a **climate unit** (it is a `climate.*`): full card with temperatures and controls.

## [0.3.15] — 2026-07-15

### 🐛 Fixed
- **Temperatures on climate cards** *(issue #2)* — climate card updates are now autonomous (own cycle, 20s safety net): temperatures appear on cards without opening the popup.
- **Alarm stuck on "LOADING" in Security page** *(issue #2)* — if no alarm panel is configured, the alarm block disappears and the page shows cameras only.
- **Washer popup for non-smart machines** *(issue #2)* — program/spin/temperature hidden when not configured: state (incl. watt threshold) and plug remain.

### 🗺️ Roadmap
- **Custom appliances** (dishwasher, dryer, pellet stove, bathroom heater…): generic cards with switch + power/level sensor — thanks Fabrizio for the idea!

## [0.3.14] — 2026-07-15

### 🐛 Fixed
- **Alerts Panel counters inconsistent with popups** — the counters (lights on, active climate, openings, low batteries) are now **computed by the dashboard on the same items you see in the popups**: the card number and the list always match, on any installation. The old "Counter…" fields are no longer needed and were removed.
- **"Active climate" counter** now counts YOUR configured climate units (ACs → Climate, radiators → Heating).
- **Openings detection** — radiator "bypass" sensors excluded (noise).

## [0.3.13] — 2026-07-15

### ✨ Added
- **☁️ Multi-device sync** *(issue #1)* — the configuration is now automatically saved to Home Assistant. On a new device just enter the token: the wizard finds the existing configuration and offers to import it — identical dashboard everywhere, no redo. Manual "Save to HA / Load from HA" buttons in Configure Entities → Export.

### 🐛 Fixed
- **Empty climate/room cards on first load** *(issue #1)* — on slow devices states arrived before the cards were built, leaving them stuck on "OFF/--°" until something changed. States are now applied right after building.

## [0.3.14] — 2026-07-15

### 🐛 Fixed — counter/popup consistency
- **Alerts Panel counters and popups now ALWAYS match** — both are computed from the same source (the entities configured in the dashboard), no longer from external sensors. No more "CLIMATE 4" with an empty popup.
- **Openings/batteries popup in two sections** — first "⚠️ OPEN/LOW (N)" (exactly what the counter counts), then "✓ ALL OK".
- **Active climate** counted from configured climate units (AC → Climate, radiators → Heating).
- **Unconfigured weather** — the widget is hidden entirely (no more "UNAVAILABLE --°").

## [0.3.13] — 2026-07-15

### 🐛 Fixed — CRITICAL
- **Dashboard not updating with partial configuration** *(issues #1 & #2 — the "I see nothing")* — an unconfigured reference could stop the whole UI from updating: climate cards stuck "off" with dashes even when configured. Unmapped references are now harmless and everything else always updates. **After updating, re-run the wizard (7 taps on the title) if you configured with earlier versions.**

### ✨ Added
- **🔋 Full battery popup** *(issue #2)* — shows ALL batteries with their percentage, lowest first (🪫 red ≤20%).
- **🚪 Full openings popup** *(issue #2)* — every door/window with OPEN/Closed state, open ones first.
- **🧺 Non-smart washers** *(issue #2)* — new "Washer plug power" field: connect a smart plug and the running/off state is derived from watts (5W threshold).

## [0.3.12] — 2026-07-15

### ✨ Added
- **💡 Custom light groups** *(issue #2)* — new "Light group" quick action: pick a name and the lights to include (searchable selector) and get a dedicated popup. Create "Ground Floor", "Garden", "Bedrooms"… each with its own lights.
- **🔍 Search in lights selection** *(issue #2)* — live search field in the wizard Lights step: filter by name or entity.

### 🐛 Fixed
- **Alarm banner stuck on "Loading…"** *(issue #2)* — if the alarm is not configured, the alarm banner is removed from Home (and unconfigured weather now says so clearly).
- **Internal wizard conflict** — lights and slots shared the same data structure and could overwrite each other: now fully separated.

## [0.3.11] — 2026-07-15

### ✨ Improved
- **🪄 "auto" badge on detected fields** — every entity filled by auto-detection is highlighted in green with a 🪄 label: you can see exactly what was recognized. Editing the field removes the badge.
- **🎯 Adaptive threshold** — slots with short labels (e.g. "Alarm panel") are now recognized; new synonyms for solar thermal and washing machine. Previously uncovered sections now detected.

## [0.3.10] — 2026-07-15

### ✨ Improved
- **🪄 Auto-detection v3** — matching engine rewritten: whole-word recognition (no more random-substring errors), period awareness (a "monthly" sensor is never proposed for a "today" value), no entity assigned twice, short-acronym support (CPU, RAM, SOC). In tests: from 14 to 50+ matches at ~94% precision.

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
