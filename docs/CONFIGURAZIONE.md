# Guida alla configurazione

> 💡 La via più semplice è il **Setup Wizard** (parte al primo avvio) e l'**editor visuale** (⚙️ Configurazione → Configura Entità). Questa guida documenta la configurazione testuale `config.js` per utenti avanzati.

## Priorità delle impostazioni

1. **Wizard/Editor** (localStorage del dispositivo)
2. **Config salvata nel file** (dopo "Scarica HTML modificato")
3. **config.js** (questo file)
4. Default interni

## connection

| Chiave | Descrizione |
|---|---|
| `token` | Token a lunga scadenza (Profilo HA → Sicurezza) |
| `remote_url` | URL remoto https (Nabu Casa/dominio) — facoltativo |
| `local_ip` | `IP:porta` in LAN — facoltativo (default: host corrente) |
| `dashboard_path` | Path Lovelace per "Editor Plancia", es. `/lovelace/0?disable_km=` |

## admin_users

Array di nomi utente HA che vedono la pagina ⚙️ Configurazione. Match parziale case-insensitive (`["mario"]` matcha "Mario Rossi"). `[]` = tutti.

## branding · sections

`title`/`subtitle` nell'header. `sections`: chiavi `home, energy, ev, boiler, clima, temp, security, server` — `false` rimuove tab e pagina.

## entities

Mappa `"riferimento": "tua_entità"`, applicata ovunque. Suggerimento: usa l'editor visuale che ha l'autocomplete su tutte le tue entità, poi esporta.

## luci

Sostituisce l'elenco luci. `"entity": "Stanza - Dettaglio"` — il trattino attiva il raggruppamento per stanza.

## carichi · avvisi · avvisi_names

Si sommano ai default. Stessi formati dell'editor visuale (vedi tab Esporta per esempi già compilati).
