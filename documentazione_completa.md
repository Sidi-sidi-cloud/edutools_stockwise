# Documentazione EduTools Professional

## Introduzione

EduTools Professional è una piattaforma completa per docenti che integra strumenti di valutazione formativa basati sul modello RIZA e un assistente AI per il supporto didattico. Questa documentazione fornisce tutte le informazioni necessarie per l'installazione, la configurazione e l'utilizzo della piattaforma.

## Indice
1. [Panoramica della piattaforma](#panoramica-della-piattaforma)
2. [Requisiti di sistema](#requisiti-di-sistema)
3. [Installazione e configurazione](#installazione-e-configurazione)
4. [Guida all'uso](#guida-alluso)
5. [Funzionalità principali](#funzionalità-principali)
6. [Pannello amministrativo](#pannello-amministrativo)
7. [Integrazione AI](#integrazione-ai)
8. [Deployment su Render](#deployment-su-render)
9. [Risoluzione problemi](#risoluzione-problemi)
10. [FAQ](#faq)

## Panoramica della piattaforma

EduTools Professional è una suite di strumenti progettata specificamente per docenti, che include:

- **Dashboard principale**: Accesso rapido a tutti gli strumenti e panoramica delle attività recenti
- **Assistente Docente AI**: Chatbot intelligente che risponde a domande su didattica, metodologie, gestione della classe e altro
- **Valutazione RIZA**: Strumento per inserire osservazioni qualitative degli allievi e collegarle ai processi RIZA
- **Visualizzazione Osservazioni**: Ricerca avanzata e visualizzazione dettagliata delle osservazioni salvate
- **Pannello Amministrativo**: Gestione utenti, monitoraggio attività e analisi dell'utilizzo della piattaforma

La piattaforma è stata progettata con un'interfaccia moderna, professionale e completamente responsive, accessibile da qualsiasi dispositivo.

## Requisiti di sistema

### Per l'installazione locale:
- Python 3.8 o superiore
- Pip (gestore pacchetti Python)
- 500 MB di spazio su disco
- Connessione internet (per l'integrazione AI)

### Per il deployment su Render:
- Account Render (gratuito)
- Repository Git (opzionale, ma consigliato)

### Browser supportati:
- Chrome (versione 88+)
- Firefox (versione 85+)
- Safari (versione 14+)
- Edge (versione 88+)

## Installazione e configurazione

### Installazione locale

1. **Estrai il pacchetto**:
   ```bash
   unzip edutools_professional_final.zip -d edutools
   cd edutools
   ```

2. **Crea un ambiente virtuale Python**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Su Windows: venv\Scripts\activate
   ```

3. **Installa le dipendenze**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Configura le variabili d'ambiente**:
   Crea un file `.env` nella directory principale con il seguente contenuto:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   SECRET_KEY=una_chiave_segreta_complessa
   DEBUG=False
   AI_MODEL=gpt-3.5-turbo
   MAX_TOKENS=1000
   TEMPERATURE=0.3
   ENABLE_AI=True
   ```

5. **Avvia l'applicazione**:
   ```bash
   python app.py
   ```

6. **Accedi all'applicazione**:
   Apri il browser e vai a `http://localhost:5000`

### Credenziali predefinite

- **Amministratore**:
  - Email: admin@edutools.it
  - Password: admin123

- **Docente**:
  - Email: docente@edutools.it
  - Password: docente123

## Guida all'uso

### Navigazione principale

La piattaforma presenta un menu laterale che permette di accedere a tutte le funzionalità:

- **Dashboard**: Panoramica generale e accesso rapido agli strumenti
- **Assistente Docente**: Chatbot AI per supporto didattico
- **Valutazione RIZA**: Inserimento e classificazione osservazioni
- **Visualizza Osservazioni**: Ricerca e consultazione osservazioni salvate
- **Pannello Amministrativo**: (Solo per amministratori) Gestione utenti e monitoraggio

### Assistente Docente

1. Accedi alla sezione "Assistente Docente" dal menu laterale
2. Digita la tua domanda nella casella di testo in basso
3. Premi Invio o clicca sull'icona di invio
4. Ricevi la risposta dall'assistente AI
5. Utilizza i suggerimenti proposti per approfondire l'argomento

L'assistente può aiutarti con:
- Strategie didattiche
- Gestione della classe
- Comunicazione con genitori
- Valutazione formativa
- Inclusione e differenziazione
- Tecnologie educative
- E molto altro

### Valutazione RIZA

1. Accedi alla sezione "Valutazione RIZA" dal menu laterale
2. Compila il modulo con i dati dell'allievo e la disciplina
3. Inserisci l'osservazione dettagliata
4. Clicca su "Analizza e Suggerisci"
5. Esamina i suggerimenti proposti dal sistema
6. Seleziona il descrittore RIZA più pertinente
7. Clicca su "Salva Osservazione"

### Visualizzazione Osservazioni

1. Accedi alla sezione "Visualizza Osservazioni" dal menu laterale
2. Utilizza i filtri per cercare osservazioni specifiche (o lascia vuoto per vedere tutte le osservazioni)
3. Clicca su "Cerca"
4. Clicca su una riga della tabella per visualizzare i dettagli completi dell'osservazione
5. Nel dettaglio, puoi visualizzare tutte le informazioni e stampare l'osservazione

## Funzionalità principali

### Dashboard

La dashboard offre:
- Accesso rapido a tutti gli strumenti
- Statistiche personali sull'utilizzo della piattaforma
- Ultime osservazioni inserite
- Notifiche e aggiornamenti

### Assistente Docente AI

- Risposte basate su conoscenze pedagogiche aggiornate
- Suggerimenti correlati per approfondire gli argomenti
- Cronologia delle conversazioni
- Possibilità di salvare risposte utili

### Valutazione RIZA

- Inserimento guidato delle osservazioni
- Analisi automatica del testo con suggerimenti RIZA
- Supporto AI per l'identificazione dei processi più pertinenti
- Salvataggio e categorizzazione delle osservazioni

### Visualizzazione Osservazioni

- Ricerca avanzata con filtri multipli
- Visualizzazione dettagliata delle osservazioni
- Esportazione e stampa delle osservazioni
- Ricerca senza filtri per visualizzare tutti i record

## Pannello amministrativo

### Dashboard Admin

- Statistiche globali sull'utilizzo della piattaforma
- Grafici e visualizzazioni dati
- Monitoraggio attività recenti
- Analisi dell'utilizzo degli strumenti

### Gestione Utenti

- Creazione, modifica ed eliminazione utenti
- Assegnazione ruoli (docente, coordinatore, amministratore)
- Gestione stato utenti (attivo, inattivo, sospeso)
- Filtri di ricerca avanzati

### Monitoraggio Conversazioni

- Accesso a tutte le conversazioni con l'assistente AI
- Filtri per utente, data e contenuto
- Analisi delle domande più frequenti
- Statistiche sull'utilizzo dell'assistente

## Integrazione AI

EduTools Professional integra l'intelligenza artificiale in due componenti principali:

### Assistente Docente

Utilizza l'API di OpenAI per fornire risposte accurate e pertinenti alle domande dei docenti. L'assistente è stato configurato specificamente per il contesto educativo e didattico.

### Suggerimenti RIZA

L'AI analizza le osservazioni inserite e suggerisce i descrittori RIZA più pertinenti, facilitando la classificazione e la valutazione formativa.

### Configurazione AI

Per utilizzare le funzionalità AI, è necessario:

1. Ottenere una chiave API da OpenAI (https://platform.openai.com)
2. Inserire la chiave nel file `.env` come indicato nella sezione installazione
3. Assicurarsi che `ENABLE_AI=True` sia impostato nel file `.env`

Se l'API non è configurata o non è disponibile, il sistema utilizzerà automaticamente un algoritmo di fallback basato su TF-IDF per i suggerimenti RIZA.

## Deployment su Render

Render è una piattaforma cloud che offre hosting gratuito per applicazioni web. Ecco come deployare EduTools Professional su Render:

1. **Crea un account Render** (se non ne hai già uno): https://render.com

2. **Crea un nuovo Web Service**:
   - Vai alla dashboard di Render
   - Clicca su "New" e seleziona "Web Service"
   - Scegli "Deploy from Git repository" o "Upload files"

3. **Configura il servizio**:
   - Nome: `edutools-professional` (o altro nome a tua scelta)
   - Runtime: `Python 3`
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `gunicorn app:app`
   - Piano: Free

4. **Configura le variabili d'ambiente**:
   - Vai alla sezione "Environment"
   - Aggiungi tutte le variabili presenti nel file `.env`
   - Assicurati di includere `OPENAI_API_KEY`

5. **Deploy**:
   - Clicca su "Create Web Service"
   - Attendi il completamento del deployment

6. **Accedi all'applicazione**:
   - Render fornirà un URL (es. `https://edutools-professional.onrender.com`)
   - Usa questo URL per accedere alla tua applicazione

### Aggiornamenti

Per aggiornare l'applicazione su Render:
- Se hai utilizzato Git, puoi semplicemente fare push delle modifiche al repository
- Se hai caricato i file manualmente, dovrai caricare nuovamente i file aggiornati

## Risoluzione problemi

### Problemi di connessione all'API OpenAI

**Sintomo**: L'assistente docente non risponde o restituisce errori.

**Soluzioni**:
1. Verifica che la chiave API sia corretta nel file `.env`
2. Controlla che il tuo account OpenAI abbia credito sufficiente
3. Verifica la connessione internet
4. Controlla i log dell'applicazione per errori specifici

### Database non accessibile

**Sintomo**: Errori durante il salvataggio o la visualizzazione delle osservazioni.

**Soluzioni**:
1. Verifica che i file del database esistano nella cartella `data`
2. Controlla i permessi di lettura/scrittura sulla cartella `data`
3. Riavvia l'applicazione

### Problemi di login

**Sintomo**: Impossibile accedere con le credenziali predefinite.

**Soluzioni**:
1. Verifica di utilizzare le credenziali corrette
2. Controlla che il database degli utenti sia stato creato correttamente
3. Se necessario, ricrea il database degli utenti eseguendo:
   ```bash
   python data/create_admin_db.py
   ```

## FAQ

**D: Posso utilizzare EduTools Professional senza connessione internet?**

R: Sì, ma con funzionalità limitate. L'assistente docente e i suggerimenti AI non saranno disponibili, ma potrai comunque inserire e visualizzare osservazioni utilizzando l'algoritmo TF-IDF locale.

**D: Come posso aggiungere nuovi utenti?**

R: Gli amministratori possono aggiungere nuovi utenti dalla sezione "Gestione Utenti" nel pannello amministrativo.

**D: È possibile esportare le osservazioni in formato Excel o PDF?**

R: Attualmente è possibile stampare le singole osservazioni in formato PDF. L'esportazione in Excel sarà disponibile in una futura versione.

**D: Come posso personalizzare i descrittori RIZA?**

R: I descrittori RIZA sono memorizzati nel database. Per personalizzarli, è necessario modificare direttamente il database o contattare l'amministratore di sistema.

**D: La piattaforma è conforme al GDPR?**

R: La piattaforma è progettata per essere conforme al GDPR, ma è responsabilità dell'amministratore assicurarsi che l'implementazione specifica rispetti tutte le normative sulla privacy applicabili.

**D: Posso utilizzare un modello AI diverso da OpenAI?**

R: Attualmente la piattaforma supporta solo i modelli OpenAI. Il supporto per altri provider AI sarà aggiunto in future versioni.

---

Per ulteriore assistenza o per segnalare problemi, contatta il supporto tecnico all'indirizzo support@edutools.it
