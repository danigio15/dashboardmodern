# Changelog

Tutte le modifiche rilevanti di Dashboard Modern sono documentate in questo file.
Il formato segue [Keep a Changelog](https://keepachangelog.com/it/) e il versionamento [SemVer](https://semver.org/lang/it/).

---

## [0.3.5] — 2026-07-14

### ✨ Aggiunto
- **🔔 Quadro Avvisi nel Setup Wizard** — nuovo accordion nello step "Collega le tue entità": aggiungi sensori di apertura (🚪 porte/finestre) e batterie (🔋) con nome personalizzato ed entità con autocomplete; ogni voce è rimovibile col cestino. Le voci alimentano i contatori della Home e il popup Avvisi.

### 🐛 Corretto
- **Azioni rapide duplicate nel wizard** — l'accordion delle azioni rapide dell'editor era finito per errore dentro il wizard (che quindi lo mostrava due volte), mentre l'editor ne era rimasto privo. Ora ogni contesto ha il proprio: uno nel wizard, uno in Configura Entità → Sezioni.

---

## [0.3.4] — 2026-07-14

### ✨ Aggiunto
- **🔄 Aggiornamenti automatici** — dopo un update HACS la dashboard rileva la nuova versione sul server (controllo all'apertura e ogni 6 ore) e **si ricarica da sola** bypassando la cache. L'URL della plancia non va mai più modificato. Protezione anti-loop inclusa.

### 🔧 Modificato
- **🖼️ Immagine auto** spostata dentro l'accordion "🚗 Auto elettrica" (wizard ed editor) — niente più accordion separato.

---

## [0.3.3] — 2026-07-14

### 🐛 Corretto
- **Sezioni disattivate visibili su mobile** — la bottom-nav mobile ha regole CSS `!important` che vincevano sul nascondi-tab: ora i tab delle sezioni disattivate vengono **rimossi fisicamente dal DOM** e non possono riapparire su nessun dispositivo.
- **Accordion Stanze duplicato** nello step Entità del wizard.

---

## [0.3.2] — 2026-07-14

### ✨ Aggiunto
- **🌡️ Stanze nel wizard** — aggiungi le stanze (icona, nome, sensore temperatura, umidità facoltativa) direttamente dallo step Entità.
- **🌐 URL remoto nel wizard** — campo facoltativo per Nabu Casa/dominio proprio nello step Connessione.

### 🔧 Modificato
- **🔥 Caldaia semplificata** — rimosso il gruppo "Impianto termico"; l'unica entità richiesta (caldaia, facoltativa) ora è un campo dentro l'accordion "Unità clima".

---

## [0.3.1] — 2026-07-14

### ✨ Aggiunto
- **⚡ Azioni rapide personalizzabili** — crea le tue azioni per la Home: predefinite (Gestione Luci, Clima, Antifurto, Lavatrice) o personalizzate (nome, icona, colore, entità/script da eseguire, conferma opzionale). Se non ne configuri nessuna, il blocco sparisce dalla Home.

### 🔧 Modificato
- Etichette clima disambiguate tra "Unità clima" e impianto.

---

## [0.3.0] — 2026-07-14

### ✨ Aggiunto
- **👻 Auto-pulizia** — gli elementi le cui entità non sono state configurate vengono **nascosti** dalla dashboard (niente card vuote con "—").
- **❄️ Unità clima illimitate** — condizionatori e termosifoni non sono più fissi: aggiungi/rimuovi le tue unità da wizard ed editor; zona Freddo e zona Caldo si popolano di conseguenza.

---

## [0.2.x] — 2026-07-14

### ✨ Aggiunto
- **🧙 Setup Wizard a 6 step** con verifica token live, luci lette da HA, entità con autocomplete, telecamere, immagine auto e rinomina sezioni
- **📑 Registry entità completo** — oltre 100 punti dati con etichette umane, configurabili per sezione
- **📹 Telecamere illimitate** (entità + stream go2rtc per il live WebRTC)
- **🎨 Tema chiaro / scuro / auto** con inseguimento del tema di sistema
- **⚙️ Pagina Configurazione** riservata agli admin (Wizard, Configura Entità, Tema)
- **🆘 Accessi di emergenza** — 7 tap sul titolo o `#setup` nell'URL; reset totale della configurazione
- **🔢 Versione visibile** in console, wizard e pagina Config

### 🔒 Sicurezza
- **Neutralizzazione completa del file distribuito**: nessuna credenziale, entità, nome o riferimento di alcuna installazione reale; chiavi interne neutre (`dm.*`) che non possono collidere con entità esistenti; gli slot non mappati non leggono alcun dato.

---

## [0.1.1] — 2026-07-14

🎉 **Prima release pubblica** — distribuzione via HACS (repository personalizzato, categoria Dashboard) con `zip_release`.
