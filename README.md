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

<br>

**Un solo file HTML · Zero card custom · Zero YAML · Si configura leggendo le tue Aree**

[🎬 Video](#-video-tutorial) · [📦 Installazione](#-installazione-in-3-minuti) · [🪄 Auto-configurazione](#-si-configura-da-sola) · [🖼️ Sezioni](#%EF%B8%8F-le-sezioni) · [☕ Supporta](#-supporta-il-progetto)

</div>

---

## ✨ Perché Dashboard Modern?

<table>
<tr>
<td width="50%" valign="top">

### 🏠 Legge le tue Aree
Il rilevamento automatico usa il **registro ufficiale** di Home Assistant: luci raggruppate per stanza vera, card temperatura+umidità per ogni Area, clima e telecamere già intitolati con la loro stanza. **Da zero a dashboard completa in 60 secondi.**

### ☁️ Ti segue ovunque
La configurazione si salva **sul tuo utente Home Assistant**: configuri sul telefono e il tablet si allinea da solo. Su un nuovo dispositivo basta il token e tutto torna.

</td>
<td width="50%" valign="top">

### 👻 Mostra solo ciò che hai
Niente card vuote: ciò che non configuri **sparisce** — anche i flussi energia. 8 sezioni attivabili e rinominabili, elementi illimitati: luci, stanze, clima, camere, **dispositivi personalizzati** (lavastoviglie, stufa a pellet…) e **popup luci su misura**.

### 🔄 Sempre aggiornata, ovunque
Update da HACS → si ricarica da sola. Funziona anche con **Pi-hole/AdGuard** o reti filtrate. Tema chiaro/scuro/auto, italiano e inglese.

</td>
</tr>
</table>

<div align="center">
<img src="screenshots/home-light.png" width="260" alt="Tema chiaro">&nbsp;&nbsp;
<img src="screenshots/home-dark.png" width="260" alt="Tema scuro">
<br><sub>☀️ Tema chiaro · 🌙 Tema scuro (o automatico col sistema)</sub>
</div>

---

## 🎬 Video tutorial

Dall'installazione alla dashboard configurata, in meno di 2 minuti:

https://github.com/user-attachments/assets/52371288-9070-4111-81ba-69f13ce1dd3f

---

## 📦 Installazione in 3 minuti

> **Prerequisito**: [HACS](https://hacs.xyz) installato. *(In alternativa: [installazione manuale](#-installazione-manuale-senza-hacs))*

**1️⃣ Aggiungi il repository** — HACS → menu **⋮** → *Repository personalizzati*:

```
https://github.com/danigio15/dashboardmodern
```
Categoria: **Dashboard**

**2️⃣ Scarica** — cerca **"Dashboard Modern"** in HACS → *Scarica*

**3️⃣ Crea la plancia** — *Impostazioni → Dashboard → Aggiungi* → vista **Pannello** → card **Iframe** con URL:

| Lingua | URL |
|---|---|
| 🇮🇹 Italiano | `/hacsfiles/dashboardmodern/dashboard.html` |
| 🇬🇧 English | `/hacsfiles/dashboardmodern/dashboard-en.html` |

**4️⃣ Aprila** — parte il Setup Wizard 👇

<details>
<summary>📁 <b>Installazione manuale (senza HACS)</b></summary>
<br>

1. Scarica `dashboard.html` (o `dashboard-en.html`) dall'ultima [release](../../releases)
2. Copialo in `/config/www/dashboards/` (File Editor o Samba)
3. Card Iframe con URL `/local/dashboards/dashboard.html`
</details>

---

## 🪄 Si configura da sola

<div align="center">
<img src="screenshots/wizard-connessione.png" width="300" alt="Wizard — connessione">&nbsp;&nbsp;
<img src="screenshots/wizard-luci.png" width="300" alt="Wizard — luci">
</div>

Sei passi guidati, nessun file da toccare:

1. **🔌 Connessione** — crea il token (istruzioni incluse), verifica live. Se avevi già configurato su un altro dispositivo, **la config torna da sola** ☁️
2. **🏠 Nome** — il nome della tua casa + utenti amministratori
3. **📑 Sezioni** — attiva solo quelle che ti servono e **rinominale**
4. **💡 Luci** — lette dal tuo HA, selezione a tap **con ricerca 🔍**
5. **🧩 Entità** — **premi 🪄**: il rilevamento legge le **Aree ufficiali** di HA e propone tutto — luci per stanza, temperatura+umidità abbinate per area, clima, telecamere, avvisi, sezioni. Badge "N/M collegate", campi verdi su ciò che è stato rilevato, lente 🔍 su ogni campo per scegliere da lista con ricerca.
6. **🎉 Fine** — riepilogo e via!

> 💡 **Riapri il wizard quando vuoi**: 7 tap veloci sul titolo della Home, oppure `#setup` nell'URL.

---

## 🖼️ Le sezioni

<div align="center">
<img src="screenshots/energia.png" width="380" alt="Sezione Energia">
<br><sub>⚡ Energia: flussi animati — i carichi non configurati spariscono, quelli a riposo si attenuano</sub>
</div>
<br>

| Sezione | Cosa offre |
|---|---|
| 🏠 **Home** | Meteo, quadro avvisi (contatori sempre coerenti coi popup), allarme, **azioni rapide** e **dispositivi personalizzati** |
| ⚡ **Energia** | Flussi fotovoltaico animati, produzione/consumo/batteria/rete, analisi giorno-mese-anno, costi |
| 🚗 **Auto elettrica** | Batteria, autonomia, sessione ricarica, wallbox, modalità EVCC |
| 🌡️ **Stanze** | Card temperatura/umidità illimitate con grafici storici |
| ❄️ **Clima** | Condizionatori e termosifoni illimitati, controlli e popup dettagliato |
| 🌞 **Solare termico** | Boiler, sonde, pompa |
| 🛡️ **Sicurezza** | Telecamere illimitate (snapshot + live WebRTC/go2rtc), centrale allarme |
| 🖥️ **Server** | CPU/RAM/disco/temperatura, speedtest, connettività |

### 🔌 Dispositivi personalizzati
Lavastoviglie, asciugatrice, stufa a pellet, scaldino… **qualsiasi elettrodomestico**: nome, icona, switch, sensore di potenza (>5W = in funzione, perfetto per i non-smart su presa) e sensore extra (es. livello pellet).

### 💡 Popup luci su misura
Crea azioni rapide "Piano Terra", "Giardino", "Camere"… **scegliendo tu le luci** da una lista con ricerca — e modificale quando vuoi con la ✏️.

---

## ⚙️ Personalizzazione totale

<div align="center">
<img src="screenshots/config-page.png" width="300" alt="Pagina configurazione">&nbsp;&nbsp;
<img src="screenshots/editor-sezioni.png" width="300" alt="Editor sezioni">
</div>

La pagina **⚙️ Config** (solo per gli admin che scegli) dà accesso a tutto: wizard, editor completo (sostituzioni, carichi, avvisi, testi, elementi nascosti, export/import) e tema. Ogni etichetta è rinominabile, ogni card nascondibile, ogni entità rimappabile.

<details>
<summary>☁️ <b>Più dispositivi? Ci pensa la sync</b></summary>
<br>

La configurazione si salva automaticamente sul tuo **utente Home Assistant**: ogni modifica (wizard o editor) viene propagata agli altri dispositivi al loro prossimo avvio. In alternativa resta disponibile 📤 Esporta/Importa manuale.
</details>

<details>
<summary>🆘 <b>Accessi di emergenza</b></summary>
<br>

| Metodo | Come |
|---|---|
| **7 tap** | Tocca 7 volte il titolo nella Home → wizard |
| **#setup** | Aggiungi `#setup` all'URL e ricarica |
| **Reset totale** | In fondo al wizard: riparti da zero |
</details>

---

## 🔒 Sicurezza

- Il token dà pieno accesso al tuo HA: **trattalo come una password** (revocabile in ogni momento dal profilo)
- Il file distribuito non contiene credenziali né dati di alcuna installazione

---

## ☕ Supporta il progetto

<div align="center">

Dashboard Modern è **gratuita e open source**, sviluppata nel tempo libero.
Se ti è utile e vuoi supportare lo sviluppo di nuove funzionalità:

[![PayPal](https://img.shields.io/badge/Dona%20con-PayPal-00457C?logo=paypal&logoColor=white&style=for-the-badge)](https://paypal.me/giovannidaniello15)

Ogni contributo, anche piccolo, è molto apprezzato! 🙏
E se ti piace, lascia una ⭐ — aiuta il progetto a crescere!

</div>

---

<div align="center">
<sub>

[MIT License](LICENSE) · Sviluppata da **Giovanni D'Aniello** con l'aiuto di Claude (Anthropic) · Grafici [Chart.js](https://www.chartjs.org)

🐛 Problemi o idee? [Apri una issue](../../issues) · 📋 [Changelog completo](CHANGELOG.md)

</sub>
</div>
