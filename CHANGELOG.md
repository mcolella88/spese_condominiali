# Changelog

Tutte le modifiche notevoli a questo progetto saranno documentate in questo file.

## [1.1.0] - 2024-04-16

### Aggiunte
- Funzione di backup dati in formato JSON
- Funzione di import/restore da file di backup
- Salvataggio automatico periodico (ogni 30 secondi)
- Struttura del progetto organizzata per GitLab
- Documentazione completa (README, CONTRIBUTING, LICENSE)

### Modifiche
- Spostamento del file HTML nella cartella src/
- Miglioramento della gestione dei dati con backup locale

### Note
- I dati vengono salvati nel localStorage del browser
- I backup manuali possono essere salvati in qualsiasi percorso
- Consigliato fare backup regolari per evitare perdita di dati

## [1.0.0] - Versione Iniziale

### Funzionalità
- Gestione fatture di luce comune, acqua e assicurazione
- Calcolo automatico ripartizione spese
- Gestione letture contatore acqua
- Storico periodi chiusi
- Esportazione in Excel
