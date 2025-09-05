# 🗺️ Antatta QGIS Plugin Repository

Repository per la distribuzione di plugin QGIS sviluppati da **Ing. Antonio Attadia**.

## 🚀 Plugin Disponibili

### AUTOMATE v2.0
**Plug-in QGIS per progetti di infrastrutture gas**
- ✅ Gestione RG_COD con automazione
- ✅ PhotoEditor con integrazione Google Street View
- ✅ Sistema di controllo qualità
- ✅ Architettura modulare professionale

## 📥 Come Aggiungere Questo Repository a QGIS

### Metodo 1: Interfaccia Grafica QGIS
1. Apri **QGIS**
2. Vai su **Plugin** → **Gestisci e installa plugin**
3. Clicca sulla scheda **Impostazioni**
4. Clicca su **Aggiungi...** nella sezione "Repository dei Plugin"
5. Inserisci i seguenti dati:
   - **Nome**: `Antatta QGIS Plugins`
   - **URL**: `https://raw.githubusercontent.com/antatta/antatta-qgis-repository/main/plugins.xml`
6. Clicca **OK**

### Metodo 2: File di Configurazione (Avanzato)
Aggiungi queste righe al file `QGIS3.ini`:
```ini
[PythonPlugins\plugin_installer]
name=Antatta QGIS Plugins
url=https://raw.githubusercontent.com/antatta/antatta-qgis-repository/main/plugins.xml
```

## 🔧 Dopo l'Aggiunta del Repository

1. I plugin di questo repository appariranno nella scheda **Tutti**
2. Cerca "**AUTOMATE**" nella barra di ricerca
3. Installa il plugin desiderato
4. Gli aggiornamenti saranno disponibili automaticamente

## 📋 Struttura Repository

```
antatta-qgis-repository/
├── plugins.xml              # Indice dei plugin disponibili
├── plugins/
│   └── automate/
│       ├── automate.zip     # Plugin compresso
│       └── icon.png         # Icona del plugin
├── README.md               # Questa documentazione
└── LICENSE                 # Licenza di utilizzo
```

## ⚠️ Compatibilità

- **QGIS**: Versione 3.0 o superiore
- **Sistema operativo**: Windows, macOS, Linux
- **Python**: 3.6+

## 🐛 Segnalazione Problemi

Hai trovato un bug o hai un suggerimento?
- 📧 Email: info.antatta@gmail.com
- 🔗 Issues: [Segnala un problema](https://github.com/antatta/antatta-qgis-repository/issues)

## 📄 Licenza

Questo repository e i plugin contenuti sono distribuiti sotto licenza [Commerciale](LICENSE).

## 🔄 Ultimo Aggiornamento

**Data**: 24 agosto 2025  
**Plugin**: AUTOMATE v2.0.0

---

*Repository mantenuto da **Ing. Antonio Attadia***
