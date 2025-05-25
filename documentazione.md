# Documentazione Applicazione Valutazione Formativa RIZA (con AI)

## Introduzione
Questa applicazione è un prototipo funzionale per supportare la valutazione formativa basata sui processi RIZA. Permette ai docenti di inserire osservazioni qualitative sul comportamento degli allievi e ricevere suggerimenti automatici che collegano l'osservazione ai processi RIZA, ai processi specifici e ai livelli di competenza.

## Funzionalità principali
1. **Inserimento osservazioni**: Interfaccia per inserire dati dell'allievo, disciplina e osservazione qualitativa
2. **Suggerimento automatico con AI**: Analisi dell'osservazione tramite intelligenza artificiale e suggerimento di dimensioni RIZA, processi e livelli pertinenti
3. **Salvataggio osservazioni**: Memorizzazione delle osservazioni con le classificazioni validate dal docente
4. **Visualizzazione osservazioni**: Consultazione delle osservazioni salvate per allievo e disciplina

## Tecnologie utilizzate
- **Backend**: Python con Flask
- **Frontend**: HTML, CSS, JavaScript con Bootstrap
- **Database**: SQLite
- **Analisi testuale**: OpenAI API (GPT-3.5 Turbo) e scikit-learn (TF-IDF come fallback)

## Struttura del progetto
```
riza_app/
├── app.py                  # Applicazione principale Flask
├── config.py               # Configurazione dell'applicazione e API key
├── .env                    # File per variabili d'ambiente (inclusa API key)
├── data/
│   ├── create_database.py  # Script per creare e popolare il database
│   └── riza_database.db    # Database SQLite
├── static/
│   ├── css/
│   │   └── style.css       # Stili CSS personalizzati
│   └── js/
│       └── script.js       # Logica JavaScript per l'interfaccia utente
└── templates/
    ├── index.html          # Pagina principale per inserimento osservazioni
    └── view_observations.html  # Pagina per visualizzare le osservazioni salvate
```

## Istruzioni per l'uso

### Accesso all'applicazione
L'applicazione è accessibile all'URL: https://5000-iud8y07ukma1ecpg7sctp-97f7cde9.manus.computer

### Inserimento di una nuova osservazione
1. Dalla pagina principale, compilare i campi:
   - Classe
   - Allievo
   - Disciplina/Ambito
   - Situazione-Problema o Attività (opzionale)
   - Osservazione qualitativa
2. Cliccare su "Ottieni Suggerimenti"
3. Esaminare i suggerimenti proposti dal sistema (generati dall'AI)
4. Selezionare il suggerimento più appropriato (o modificare manualmente i campi)
5. Cliccare su "Salva Osservazione"

### Visualizzazione delle osservazioni salvate
1. Cliccare su "Visualizza Osservazioni" nel menu in alto
2. Inserire il nome dell'allievo
3. Selezionare una disciplina specifica (opzionale)
4. Cliccare su "Cerca Osservazioni"
5. Visualizzare l'elenco delle osservazioni salvate

## Note tecniche
- Il motore di suggerimento utilizza l'API di OpenAI (GPT-3.5 Turbo) per analizzare le osservazioni e generare suggerimenti pertinenti
- In caso di errore nella chiamata all'API, il sistema utilizza un fallback basato su TF-IDF e similarità del coseno
- I suggerimenti sono ordinati per rilevanza e includono una spiegazione del motivo per cui sono stati proposti
- Il database contiene rubriche per Matematica e Scienze Umane/Sociali/Naturali del secondo ciclo
- I descrittori RIZA sono classificati nelle dimensioni: Interpretazione, Azione e Autoregolazione

## Configurazione dell'API OpenAI
L'applicazione utilizza l'API di OpenAI per generare suggerimenti più accurati. La configurazione può essere gestita in due modi:

1. **Tramite file .env** (metodo consigliato):
   - Creare un file `.env` nella directory principale dell'applicazione
   - Aggiungere la seguente riga: `OPENAI_API_KEY=your_api_key_here`
   - È possibile configurare anche altri parametri come `AI_MODEL`, `MAX_TOKENS`, `TEMPERATURE`, `ENABLE_AI`

2. **Tramite variabili d'ambiente**:
   - Impostare la variabile d'ambiente `OPENAI_API_KEY` con la chiave API
   - Altre variabili configurabili: `AI_MODEL`, `MAX_TOKENS`, `TEMPERATURE`, `ENABLE_AI`, `DEBUG`

3. **Tramite file config.py**:
   - Modificare direttamente il file `config.py` (sconsigliato per la produzione)

## Limitazioni del prototipo
- Non include funzionalità multi-utente o gestione avanzata dei permessi
- Non implementa reportistica avanzata o analisi cumulative
- Non copre tutti gli ambiti disciplinari esistenti
- L'interfaccia utente è funzionale ma non altamente rifinita

## Sviluppi futuri
- Estensione a più discipline e cicli scolastici
- Implementazione di reportistica avanzata
- Miglioramento dell'algoritmo di suggerimento con tecniche NLP più avanzate
- Interfaccia utente più ricca e personalizzabile
- Implementazione di un sistema di feedback per migliorare la qualità dei suggerimenti AI
