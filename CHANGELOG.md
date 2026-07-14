# Changelog

## [1.0.0] — 2026-07-14

Prima release pubblica. 🎉

### Aggiunto
- **Distribuzione via HACS** (repository personalizzato, categoria Dashboard) con aggiornamenti automatici; config caricabile da `/local/casa-dashboard-config.js` esterno che sopravvive agli update
- **GitHub Actions**: release automatica dello zip al tag + validazione HACS
- **Configuratore per sezione** (editor → 📑 Sezioni): ogni sezione elenca le proprie entità con etichette umane ("Produzione solare oggi") e autocomplete — tutto configurabile da UI senza conoscere il codice
- **Stanze dinamiche**: le card temperatura si generano dalla configurazione utente (aggiungi/rimuovi stanze con nome, icona, sensori da UI)
- **Setup Wizard** al primo avvio: connessione con verifica token live, branding, scelta sezioni, selezione luci lette da HA
- **Tema chiaro / scuro / auto** con dark mode completo e inseguimento del tema di sistema
- **Pagina ⚙️ Configurazione** riservata agli admin: Editor Plancia, Configura Entità, Tema
- **Editor visuale a 6 tab**: sostituzioni entità (autocomplete), carichi, avvisi, rinomina testi, nascondi elementi, esporta/importa
- **Download HTML configurato**: le personalizzazioni vengono integrate nel file scaricato (persistenza multi-dispositivo)
- **Gestione luci** raggruppata per stanza con card luminose e "Spegni tutte"
- **8 sezioni** attivabili: Home, Energia, Auto elettrica, Solare termico, Clima, Stanze, Sicurezza, MiniPC
- Sistema `admin_users` configurabile (wizard o config.js)
- Configurazione testuale opzionale via `config.js`

### Sicurezza
- Nessuna credenziale nel file distribuito; token fornito da wizard o config
