# Scripts Directory

Questa cartella contiene gli script di automazione per la gestione del repository di plugin QGIS.

## Script Disponibili

### `deploy_plugin.py`
Script principale per il deployment automatico dei plugin:
- Lettura automatica del file `metadata.txt`
- Creazione del file ZIP con esclusioni appropriate
- Aggiornamento del file `plugins.xml`
- Upload su GitHub via API

### `update_xml.py`
Script per aggiornare solo il file `plugins.xml` senza creare nuovi package.

### Configurazione

Gli script utilizzano variabili d'ambiente per l'autenticazione GitHub:
```bash
export GITHUB_TOKEN="your_personal_access_token"
```

## Utilizzo

```bash
# Deploy completo del plugin
python scripts/deploy_plugin.py --plugin automate --version 1.99.0

# Solo aggiornamento XML
python scripts/update_xml.py --plugin automate --version 1.99.0
```