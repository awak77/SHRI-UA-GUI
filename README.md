# SHRI-Upload-Assistant-GUI
Interfaccia grafica per Audionut Upload-Assistant, Uno strumento semplice per semplificare il lavoro di upload.

Questo progetto è una GUI basata sul lavoro originale di Audionut https://github.com/Audionut/Upload-Assistant
Un ringraziamento speciale a lui per aver creato questo progetto.

## Cosa può fare la GUI:

### 🖥️ **Interfaccia Grafica Intuitiva:**
  - **Interfaccia user-friendly** con layout responsive per tutti i tipi di schermo
  - **Selezione file/cartelle** tramite dialog grafici (niente linea di comando!)
  - **Campi compilabili** per IMDb ID, TMDb ID, TYPE, TAG gruppo, piattaforma streaming, edizione (tutti su una sola riga per risparmiare spazio)
  - **Campo parametri custom** per aggiungere argomenti personalizzati al comando upload
  - **Combobox intelligenti** per tipo rilascio (Film MKV/Disco, Serie Episodio/Stagione)
  - **Checkbox compatte** su una riga: Seed automatico, Personal Release, Debug Mode
  - **Tooltip informativi** su ogni elemento per guidare l'utente
  - **Sistema di logging** con salvataggio automatico su file timestampati nella cartella logs/

### 🔧 **Setup e Configurazione Automatica:**
  - **Setup completamente automatico** con un solo click
  - **Controllo dipendenze** automatico (Git, Python, pip, FFmpeg)
  - **Download automatico** di Upload-Assistant se non presente
  - **Creazione ambiente virtuale** automatica
  - **Installazione dipendenze** automatica con progress feedback
  - **Configurazione API keys** tramite dialog guidato
  - **Verifica FFmpeg** con guida di installazione Winget integrata

### 💻 **Terminale Integrato:**
  - **PowerShell integrato** direttamente nell'interfaccia
  - **Esecuzione comandi** in tempo reale con output colorato
  - **Controlli avanzati**: INVIO, Interrompi (Ctrl+C), Reset completo
  - **Cronologia comandi** e auto-scroll intelligente
  - **Gestione processi** con indicatori di stato visivi
  - **Font ingranditi** e output ottimizzato per la lettura

### 🚀 **Funzionalità Avanzate:**
  - **Aggiornamenti automatici** di Upload-Assistant tramite git pull
  - **Test integrati** per verificare FFmpeg e configurazioni
  - **Gestione errori robusta** con timeout e fallback automatici
  - **Salvataggio preferenze** per geometria finestra e modalità compatta
  - **Supporto finestre multiple** con ridimensionamento dinamico
  - **Modalità compatta** per schermi piccoli

### 📦 **Gestione Upload Semplificata:**
  - **Un click per l'upload** - tutti i parametri vengono passati automaticamente
  - **Validazione input** con controlli pre-upload
  - **Feedback visivo** durante tutte le operazioni
  - **Gestione tracker** ottimizzata per ShareIsland (SHRI)
  - **Configurazione rapida** di parametri avanzati senza editing manuale

### 🔄 **Manutenzione e Aggiornamenti:**
  - **Pulsanti dedicati** per aggiornare bot e dipendenze
  - **Editor config.py integrato** (Notepad++ o Notepad)
  - **Controllo stato sistema** con diagnostica integrata
  - **Backup automatico** delle configurazioni
  - **Log dettagliati** nel terminale per troubleshooting

### ✨ **Tutto il Potere di Upload-Assistant, Zero Complessità:**
Mantiene tutte le funzionalità avanzate del bot originale:
  - Generazione e analisi MediaInfo/BDInfo
  - Screenshot automatici con tonemapping HDR
  - Correzione nomi scena via srrdb
  - Recupero descrizioni da tracker esistenti
  - Gestione identificatori TMDb/IMDb/MAL/TVDB/TVMAZE
  - Creazione .torrent ottimizzati
  - Integrazione qBitTorrent automatica
  - **TUTTO CON INTERFACCIA GRAFICA - ZERO LINEA DI COMANDO!**

## Tracker supportati:

ShareIsland

## **Setup Automatico (Consigliato):**

### 📋 **Prerequisiti:**
Prima di iniziare, assicurati di avere installato:

1. **Git** - [Scarica da qui](https://git-scm.com/install/windows)
2. **Python 3.9+** - [Scarica da qui](https://www.python.org/downloads/)
   - ⚠️ Durante l'installazione, assicurati di spuntare **"Add Python to PATH"**
3. **FFmpeg** - Installa da un terminale PowerShell con: `winget install ffmpeg`

### 🚀 **Installazione Rapida:**

1. **Scarica ed estrai l'applicazione:**
   - **Scarica lo ZIP** dai [Releases](https://github.com/tiberio87/SHRI-UA-GUI/releases)
   - **Estrai lo ZIP sul Desktop** (consigliato per evitare problemi di permessi)
   - Dovresti ottenere una cartella `SHRI-UA-GUI` sul Desktop con questi file:
     - `SHRI - Upload Assistant.py` (il file principale)
     - `README.md`
     - `requirements.txt`
   - **Oppure** clona con Git: `git clone https://github.com/tiberio87/SHRI-UA-GUI`
     - In questo caso ti consiglio di clonare direttamente sul Desktop: `cd Desktop` e poi `git clone ...`

2. **Installa le dipendenze GUI:**
   - Apri PowerShell o Prompt dei Comandi
   - Esegui: `pip install customtkinter pywinpty`
   - Queste sono le uniche dipendenze necessarie per avviare la GUI

3. **Crea il file API Keys:**
   - **Apri il Blocco Note** (o un editor di testo)
   - **Copia e incolla** questa struttura:
   ```json
   {
     "tmdb_api": "la_tua_api_key_tmdb",
     "shri_api": "la_tua_api_key_shri",
     "ptscreens_api": "la_tua_api_key_ptscreens",
     "discord_webhook": "",
     "qbit_url": "http://localhost",
     "qbit_port": "8080",
     "qbit_user": "",
     "qbit_pass": ""
   }
   ```
   - **Sostituisci** `la_tua_api_key_tmdb` e `la_tua_api_key_shri` e `la_tua_api_key_ptscreens` con le tue chiavi vere
   - **Salva il file** come `api_keys.json` nella cartella `SHRI-UA-GUI` sul Desktop
   - **Percorso finale esempio**: `C:\Users\TuoNome\Desktop\SHRI-UA-GUI\api_keys.json`
   - ⚠️ **IMPORTANTE**: 
     - Il file deve stare **nella stessa cartella** dove si trova `SHRI - Upload Assistant.py`
     - Il file deve chiamarsi esattamente `api_keys.json` (NON `api_keys.json.txt`)
     - Quando salvi, seleziona "Tutti i file" come tipo, non "File di testo"

4. **Avvia l'applicazione:**
   
   **Metodo consigliato (da terminale):**
   - Apri **PowerShell** o **Prompt dei Comandi**
   - **Spostati nella cartella** dove hai estratto i file:
     ```powershell
     cd Desktop\SHRI-UA-GUI
     ```
   - **Avvia il programma** con Python:
     ```powershell
     python '.\SHRI - Upload Assistant.py'
     ```
   
   **Perché non funziona il doppio click?**
   - Se facendo doppio click sul file `.py` non succede nulla o si apre con un editor di testo, significa che i file Python non sono associati correttamente al Python Launcher
   - Il modo più semplice e affidabile è **sempre usare il terminale** come mostrato sopra
   
   **Prima esecuzione:**
   - Al primo avvio, clicca **"Setup da locale"**
   - L'applicazione farà tutto automaticamente:
     - ✅ Controlla le dipendenze di sistema
     - ✅ Verifica FFmpeg (con guida di installazione se mancante)
     - ✅ Scarica Upload-Assistant di Audionut
     - ✅ Crea l'ambiente virtuale
     - ✅ Installa tutte le dipendenze
     - ✅ Configura automaticamente i file

### 🔑 **Configurazione API Keys:**

**Dove ottenere le chiavi:**
- **TMDB API**: [Registrati su TMDB](https://www.themoviedb.org/settings/api)
- **PTscreens API**: [Registrati su PTScreens](https://ptscreens.com/)
- **SHRI API**: Fornita dal tracker

**Durante il setup automatico:**
- L'applicazione rileverà automaticamente le chiavi mancanti
- Ti mostrerà un dialog per compilare solo quelle obbligatorie
- Le chiavi opzionali possono essere configurate in seguito

### ⚙️ **Test della Configurazione:**

Dopo il setup, verifica che tutto funzioni:
- **🎬 Test FFmpeg**: Clicca il pulsante per verificare FFmpeg
- **🔄 Controlla aggiornamenti**: Testa la connessione a GitHub
- **📦 Installa req.**: Verifica l'ambiente virtuale

### 🔧 **Setup Manuale (Avanzato):**

Se preferisci configurare tutto manualmente:

1. **Clona Upload-Assistant:**
   ```bash
   git clone https://github.com/Audionut/Upload-Assistant.git
   ```

2. **Crea ambiente virtuale:**
   ```bash
   cd Upload-Assistant
   python -m venv .venv
   .venv\Scripts\activate
   ```

3. **Installa dipendenze:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configura i file:**
   - Copia `data/example-config.py` in `data/config.py`
   - Modifica `config.py` con le tue API keys
   - Avvia la GUI e seleziona le cartelle manualmente

## **Aggiornamenti:**

### 🔄 **Aggiornamenti Automatici dalla GUI:**
- **"🔄 Controlla aggiornamenti Upload-Assistant"** - Aggiorna il bot tramite git pull
- **"📦 Installa req."** - Aggiorna le dipendenze Python
- **"🎬 Test FFmpeg"** - Verifica lo stato di FFmpeg

### 📥 **Aggiornamento della GUI:**
Per aggiornare questa GUI:
```bash
cd SHRI-UA-GUI
git pull origin master
```

## **Troubleshooting:**

### ❌ **Problemi Comuni:**

**"Git non trovato":**
- Installa Git da [git-scm.com](https://git-scm.com/install/windows)
- Riavvia l'applicazione dopo l'installazione

**"Python non trovato":**
- Installa Python 3.9+ da [python.org](https://www.python.org/downloads/)
- Durante l'installazione, spunta "Add Python to PATH"

**"FFmpeg non trovato":**
- Apri PowerShell e esegui: `winget install ffmpeg`
- Riavvia l'applicazione per verificare

**"API Keys mancanti":**
- L'applicazione ti guiderà nella configurazione
- Solo TMDB e SHRI API sono obbligatorie

**"Timeout durante il clone":**
- Verifica la connessione internet
- Prova a clonare manualmente: `git clone https://github.com/Audionut/Upload-Assistant.git`

**"La GUI si blocca":**
- Premere il tasto giallo RESET GUI

### 🆘 **Supporto:**
- Controlla i [Issues](https://github.com/tiberio87/SHRI-UA-GUI/issues) per problemi noti
- Crea un nuovo issue per segnalare bug
- Il terminale integrato mostra log dettagliati per il debugging

## **Attribuzioni:**

<p>
  <a href="https://github.com/Audionut/Upload-Assistant"><img src="https://avatars.githubusercontent.com/u/13182387?s=48&v=4" alt="UA" height="30px;"></a>&nbsp;&nbsp;
</p>
