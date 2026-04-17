# Changelog

Tutte le modifiche notevoli del progetto.

## [4.0.0] - 2026-04-17

### Aggiunto
- Migrazione da localStorage a IndexedDB per persistenza dati
- Integrazione libreria idb-keyval per gestione semplificata IndexedDB
- Fallback automatico a localStorage se IndexedDB non disponibile
- Maggiore capacità di storage (50MB+ vs 5MB localStorage)
- Performance migliorate con operazioni asincrone
- Maggiore affidabilità e resistenza alla corruzione dati

### Modificato
- Tutte le funzioni di salvataggio ora usano IndexedDB
- Funzioni di caricamento dati aggiornate per IndexedDB
- Auto-salvataggio aggiornato per operazioni asincrone
- Backup/restore JSON mantengono compatibilità con vecchi backup

### Risolto
- Bug: Card statistiche acqua rimaneva visibile dopo chiusura periodo
- Card "Fatture Acqua Periodo" ora rimossa correttamente quando non ci sono fatture

### Tecnologie
- Aggiunto idb-keyval (CDN) per IndexedDB
- Sostituito localStorage con IndexedDB
- Mantenuta compatibilità con localStorage come fallback

## [3.3.0] - Data precedente

### Aggiunto
- Supporto per bolli/commissioni su tutte le fatture
- Riepilogo dettagliato bolli per categoria (luce, acqua, assicurazione)
- Totali comprensivi di bolli/commissioni
- Migliorata logica caricamento bolletta acqua
- Migliorata logica generale
- Migliorata logica calcolo spese acqua

### Modificato
- Struttura dati fatture per includere bolli
- Calcoli ripartizione per includere bolli proporzionali
- Export Excel aggiornato per includere bolli
- Backup JSON aggiornato per nuova versione

## [3.2.0] - Data precedente

### Aggiunto
- Riepilogo bolli/commissioni e totali comprensivi
- Migliorata visualizzazione riepilogo spese

## [3.1.0] - Data precedente

### Aggiunto
- Gestione letture iniziali periodo acqua
- Calcolo consumi individuali acqua
- Ripartizione proporzionale spese acqua
- Storico periodi chiusi
- Export Excel completo

### Modificato
- Logica gestione acqua completamente riscritta
- Struttura dati periodi

## [3.0.0] - Data precedente

### Aggiunto
- Configurazione nomi proprietari
- Modifica fatture esistenti
- Backup/restore JSON
- Auto-salvataggio periodico
- Reset letture acqua
- Esportazione Excel

### Modificato
- Migliorata UI con design moderno
- Responsive design
- Gradienti e animazioni

## [2.0.0] - Data precedente

### Aggiunto
- Gestione multipla tipo spese (luce, acqua, assicurazione)
- Dettagli specifici per fatture acqua
- Calcolo ripartizione automatico

## [1.0.0] - Data precedente

### Aggiunto
- Prima versione
- Gestione base fatture
- Calcolo 50/50 spese comuni
- localStorage per persistenza
