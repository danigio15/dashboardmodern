# Changelog

🇮🇹 Italiano · [🇬🇧 English below](#-english)

Il formato segue [Keep a Changelog](https://keepachangelog.com/it/) e il versionamento [SemVer](https://semver.org).

---

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
