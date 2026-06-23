# 🗺️ Antatta QGIS Plugin Repository

Repository ufficiale per la distribuzione di plugin QGIS sviluppati da **Ing. Antonio Attadia**.

## 🚀 Plugin Disponibili

### AUTOMATE v3.0.0 *(Major Release)*
**Plug-in QGIS per progetti di infrastrutture gas**

Il plugin si integra nativamente nell'interfaccia di QGIS tramite una toolbar dedicata, ottimizzando i flussi di lavoro ingegneristici grazie a un'architettura solida e funzionalità avanzate:

* 🗺️ **Gestione Lotto, Regolamento, Mappatura**: Workflow indipendente per il bootstrap dei progetti di lotto, regolamenti e mappatura.
* 📸 **Evoluzione PhotoEditor**: Gestione fotografica avanzata con integrazione Google Street View API, cattura del cono visivo e allineamento al modello dati astratto e layer-agnostic `ATTACHED_DATA`.
* ✅ **Quality Control Avanzato**: Sistema di validazione geometrica, topologica e di attributi (es. regole condizionali su materiali/diametri, controlli di distanza multi-target con logica OR, e analisi delle immagini delle sezioni tramite OpenCV). Include il sistema *Auto-Fix* per l'aggiunta automatica di campi SDI mancanti.
* 🗄️ **Attachment & Trash Manager**: Gestione completa degli allegati di progetto con controllo del ciclo di vita dei file e gestione del cestino.
* 📦 **Project Packaging**: Compressione automatizzata del progetto in formato `.zip` per la consegna, con tracciamento del progresso e risoluzione cross-platform dei percorsi.
* 🔄 **DB Master Sync & Cache**: Mirror locale SQLite sincronizzato automaticamente in background dal database principale per velocizzare le letture e minimizzare i tempi di validazione.
* 🔐 **Workspace DB Editor Autenticato**: Ambiente di editing avanzato per tabelle di metadati e tabelle private del DB Master, con gestione dei ruoli basata su token JWT (`teng_member` / `teng_admin`) e flussi di pubblicazione sicuri.
* ⚙️ **Modern Dev Stack**: Sviluppo e pipeline di deployment modernizzati basati su `pyproject.toml`, `uv`, `ruff` e `pyright` per la massima affidabilità di runtime.

---

## 📥 Come Aggiungere Questo Repository a QGIS

### Metodo 1: Interfaccia Grafica QGIS (Consigliato)
1. Apri **QGIS**.
2. Vai nel menu **Plugin** → **Gestisci e installa plugin...**
3. Seleziona la scheda **Impostazioni** sulla sinistra.
4. Clicca sul pulsante **Aggiungi...** nella sezione *Repository dei Plugin*.
5. Compila i campi come segue:
   - **Nome**: `Antatta QGIS Plugins`
   - **URL**: `https://raw.githubusercontent.com/antatta/antatta-qgis-repository/main/plugins.xml`
6. Clicca **OK**.

### Metodo 2: Configurazione Centralizzata (Avanzato)
Per deployment automatizzati o configurazioni centralizzate, è possibile inserire la voce direttamente nel file di configurazione `QGIS3.ini` sotto la sezione dedicata, prestando attenzione a non sovrascrivere gli indici di eventuali altri repository extra già configurati:
```ini
[PythonPlugins\plugin_installer]
name=Antatta QGIS Plugins
url=[https://raw.githubusercontent.com/antatta/antatta-qgis-repository/main/plugins.xml](https://raw.githubusercontent.com/antatta/antatta-qgis-repository/main/plugins.xml)

```

---

## 🔧 Installazione del Plugin

1. Dopo aver aggiunto il repository, seleziona la scheda **Tutti** nel gestore dei plugin.
2. Cerca "**AUTOMATE**" nella barra di ricerca.
3. Seleziona il plugin e clicca su **Installa plugin**.
4. Gli aggiornamenti futuri verranno notificati e gestiti in automatico dal sistema di update di QGIS.

---

## 📋 Struttura del Repository e del Codice

```text
antatta-qgis-repository/
├── plugins.xml              # Indice XML dei plugin letto da QGIS
├── plugins/
│   └── automate/
│       ├── automate.zip     # Pacchetto del plugin compresso distribuito
│       └── icon.png         # Icona ufficiale del plugin
├── README.md                # Questa documentazione
└── LICENSE                  # Licenza di utilizzo

```

### Struttura Modulare Interna del Plugin (`AUTOMATE v3.x`)

Il codice del core del plugin è organizzato secondo criteri di alta coesione e separazione delle responsabilità:

* `core/`: Utility condivise, costanti globali e gestione centralizzata del contesto (`AutomateContext`).
* `database/`: Connettività centralizzata, lettore di metadati locale/remoto e servizi di sincronizzazione del cache.
* `db/` & `icon/`: Directory radice dedicate rispettivamente ai database locali di supporto e alle risorse grafiche.
* `tools/rg_cod/`: Sistema di calcolo e generazione automatica o manuale dei codici RG_COD.
* `tools/photo/`: Interazioni dell'editor fotografico, persistenza delle scene e cattura parametri Street View.
* `tools/attachments/`: Gestione fisica dei file allegati e logica di `TrashManager`.
* `tools/controller/`: Interfaccia del validatore di qualità e motore dei controlli analitici.
* `tools/section/`: Modulo dedicato al bootstrap dei progetti regolamenti, gestione flussi GPKG e migrazione dei progetti legacy.
* `tools/db_editor/`: Interfaccia e logiche per l'editing autenticato (progetto di workspace `.qgz` dedicato).
* `tools/settings/`: Dialoghi di configurazione avanzata, preferenze e gestione chiavi API.
* `tools/zip/`: Compressione del pacchetto di consegna con callback per il tracciamento dello stato di avanzamento.

---

## ⚠️ Requisiti e Compatibilità

* **QGIS**: Versione 3.44 LTR o superiore (consigliate versioni LTR)
* **Categoria**: Vettoriale / Database
* **Sistemi Operativi**: Windows, macOS, Linux (piena compatibilità cross-platform dei percorsi e dei package installati)
* **Python**: 3.12+

---

## 🐛 Segnalazione Problemi e Supporto

Hai riscontrato un bug, un comportamento anomalo del tracker o vuoi proporre un'ottimizzazione delle regole di business?

* 🔗 **GitHub Issues**: [Segnala un problema / Apri un ticket](https://github.com/antatta/antatta-qgis-repository/issues)
* 📧 **Email**: info.antatta@gmail.com

---

## 📄 Licenza

Questo repository e i plugin distribuiti al suo interno sono rilasciati sotto licenza **Commerciale**. Tutti i diritti sul codice e sulle automazioni industriali sono riservati.
## 🔄 Ultimo Aggiornamento

**Data**: 23 giugno 2026
---

*Repository e codice mantenuti da **Ing. Antonio Attadia***

```