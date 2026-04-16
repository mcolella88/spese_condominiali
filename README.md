# Gestione Spese Condominiali

Applicazione web per la gestione delle spese condominiali tra due proprietari.

## Funzionalità

- Gestione fatture di luce comune, acqua e assicurazione annuale
- Calcolo automatico della ripartizione delle spese
- Gestione letture contatore acqua con calcolo consumi effettivi
- Storico periodi chiusi
- Esportazione in Excel
- **Backup e ripristino dati in formato JSON**
- **Salvataggio automatico periodico**

## Utilizzo

1. Aprire il file `src/spese_condominiali.html` in un browser web moderno
2. Configurare i nomi dei proprietari
3. Aggiungere le fatture man mano che arrivano
4. Chiudere i periodi per archiviare i dati

## Backup e Ripristino

L'applicazione supporta tre modalità di salvataggio dei dati:

### 1. Salvataggio Automatico
- I dati vengono salvati automaticamente nel localStorage del browser ogni 30 secondi
- Il salvataggio è silenzioso e non richiede interazione dell'utente
- I dati persistono tra le sessioni dello stesso browser

### 2. Backup Manuale
- Clicca sul pulsante "💾 Backup Dati" per esportare tutti i dati in un file JSON
- Il file include: fatture, storico periodi, configurazione nomi, letture acqua
- Il file viene scaricato con nome `backup_spese_condominiali_YYYY-MM-DD.json`
- **Consigliato**: Fai backup regolari e salvali in una posizione sicura

### 3. Ripristino da Backup
- Clicca sul pulsante "📥 Importa Backup" per caricare un file di backup precedente
- Seleziona il file JSON del backup
- L'applicazione mostrerà la data del backup e chiederà conferma
- Tutti i dati attuali verranno sostituiti con quelli del backup

## Struttura del Progetto

```
app_calcoli/
├── src/
│   └── spese_condominiali.html    # Applicazione principale
├── docs/
│   └── (documentazione aggiuntiva)
├── .gitignore                      # File ignorati da Git
├── .gitlab-ci.yml                  # Configurazione GitLab CI/CD
├── README.md                       # Documentazione principale
├── CONTRIBUTING.md                 # Guida contributi
├── LICENSE                         # Licenza MIT
└── CHANGELOG.md                    # Storico modifiche
```

## Tecnologia

- HTML5, CSS3, JavaScript vanilla
- SheetJS per l'esportazione in Excel
- LocalStorage per il salvataggio dati
- File API per backup/restore

## Deployment su GitLab

Questo progetto è pronto per essere caricato su GitLab. La struttura include:

- `.gitignore` configurato per ignorare file di backup e dipendenze
- `.gitlab-ci.yml` per CI/CD (opzionale)
- Documentazione completa

Per caricare su GitLab:

1. Inizializza il repository Git:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. Crea un nuovo progetto su GitLab

3. Aggiungi il remote e push:
   ```bash
   git remote add origin <tuo-gitlab-url>
   git push -u origin main
   ```

## Sicurezza dei Dati

- I dati vengono salvati localmente nel browser dell'utente
- Nessun dato viene inviato a server esterni
- I file di backup contengono tutti i dati e dovrebbero essere trattati come file sensibili
- È responsabilità dell'utente mantenere backup regolari in posizioni sicure

## Licenza

MIT License - vedi file LICENSE per dettagli
