# Changelog

Tutte le modifiche importanti del progetto vengono documentate in questo file.

## [3.2.0] - 2025-04-17

### Aggiornamento Minore - Visualizzazione Migliorata Riepilogo

**Miglioramenti nella visualizzazione del riepilogo spese:**

### Modifiche
- **Aggiunta visualizzazione bolli/commissioni nel riepilogo**:
  - Per luce: mostra importo, bolli, e totale comprensivo
  - Per assicurazione: mostra importo, bolli, e totale comprensivo
  - Per acqua: mostra totale fatture, bolli, e totale + bolli nella card statistiche
- **Calcolo totali comprensivi**:
  - I totali ora includono sia l'importo delle fatture che i bolli/commissioni
  - Per acqua: i bolli vengono ripartiti proporzionalmente ai consumi alla chiusura periodo
- **Aggiornata esportazione Excel**:
  - Colonne aggiuntive per bolli di ogni tipo di spesa
  - Riepilogo periodi più dettagliato con separazione bolli

### Miglioramenti
- Maggiore trasparenza nella composizione dei costi
- Possibilità di vedere esattamente quanto si paga di bolli/commissioni
- Totali finali più accurati comprensivi di tutti i costi

### Compatibilità
- Compatibile con periodi precedenti (gestione valori null per vecchi periodi)
- Backup precedenti compatibili con migrazione automatica

## [3.1.0] - 2025-04-17

### Aggiornamento Minore - Nuove Funzionalità

**Aggiunte funzionalità richieste dall'utente:**

### Modifiche
- **Aggiunto campo "Bolli/Commissioni" per tutte le fatture**: 
  - Prima disponibile solo per le fatture acqua
  - Ora disponibile per luce, acqua e assicurazione
  - Campo generale nel form fatture
- **Aggiunta funzionalità modifica fatture**:
  - Pulsante "Modifica" nella tabella fatture
  - Form popolato automaticamente con dati della fattura esistente
  - Pulsante "Annulla Modifica" per cancellare la modifica
  - Pulsante submit cambia testo in "Aggiorna Fattura" durante modifica
  - Scroll automatico al form quando si modifica una fattura

### Miglioramenti
- Maggiore flessibilità nella gestione delle fatture
- Possibilità di correggere errori senza dover eliminare e reinserire
- UI migliorata con feedback visuale dello stato di modifica

### Compatibilità
- Nessuna modifica alla struttura dati esistente
- Backup precedenti completamente compatibili

## [3.0.0] - 2025-04-17

### Aggiornamento Maggiore - Logica Gestione Acqua (Versione Definitiva)

**Modifiche alla logica di gestione dell'acqua per allinearla completamente al sistema tradizionale:**

### Modifiche
- **Rimossi campi letture individuali dal form fattura acqua**
- **Aggiunto campo "Lettura SMAT"**: Inserimento della lettura riportata sulla fattura SMAT
- **Nuova sezione "Letture Iniziali Periodo"**: Impostazione delle letture individuali all'inizio di ogni periodo
- **Modificata logica chiusura periodo**: 
  - Richiesta delle letture individuali finali tramite prompt
  - Calcolo consumi: Lettura finale - Lettura iniziale
  - Calcolo prezzo al mq: Totale fatture / Consumo totale
  - Ripartizione proporzionale automatica
- **Aggiornata UI**:
  - Rimossi campi letture individuali dalla tabella fatture
  - Aggiunta colonna "Lettura SMAT"
  - Card statistiche acqua mostra solo totali fatture (calcolo finale alla chiusura)
- **Reset automatico letture**: Le letture iniziali vengono resettate alla chiusura del periodo
- **Versione backup aggiornata a 3.0**

### Nuovo Flusso di Lavoro Acqua
1. **Inizio periodo**: Impostare letture iniziali dei contatori individuali
2. **Caricamento fatture**: Inserire solo dati SMAT (numero, periodo, tipo lettura, lettura SMAT, bolli, acconto)
3. **Chiusura periodo**: Inserire letture finali individuali per calcolo consumi e ripartizione

### Miglioramenti
- Logica ora corrisponde esattamente al sistema manuale tradizionale
- Separazione chiara tra dati SMAT e letture individuali
- Calcolo ripartizione solo alla chiusura periodo (come nel sistema Excel)
- Maggiore chiarezza nel flusso di lavoro

### Compatibilità
- I backup delle versioni precedenti sono compatibili con migrazione automatica
- Gestione automatica della transizione da vecchia struttura dati

## [2.0.0] - 2025-04-17

### Aggiornamento Maggiore - Logica Gestione Acqua (Versione Intermedia)

**Modifiche alla logica di gestione dell'acqua per allinearla al sistema tradizionale:**

### Modifiche
- **Rimosso campo "Lettura Totale Fattura"** - Non più necessario
- **Nuova logica calcolo consumo:**
  - Calcolo consumo totale del periodo (differenza ultima-prima lettura)
  - Consumo individuale = ultima lettura - prima lettura
  - Prezzo/m³ = Totale fatture acqua / Consumo totale periodo
  - Importo dovuto = Consumo individuale × Prezzo/m³
- **Semplificata prima fattura acqua:**
  - Richiede solo letture individuali precedenti (mia e vicino)
  - Rimossa richiesta lettura totale precedente
- **Aggiornata UI:**
  - Rimossa colonna "Lettura Totale" dalla tabella fatture
  - Migliorata card "Statistiche Acqua" con consumi individuali
  - Reset automatico letture alla chiusura periodo
- **Aggiornata esportazione Excel:**
  - Rimossi campi non più necessari
  - Semplificata struttura colonne
- **Versione backup aggiornata a 2.0**

### Nuovi campi per fatture acqua
- Numero bolletta
- Periodo DAL - AL
- Tipo lettura (stimata/rilevata)
- Bolli (€)
- Acconto (€)

### Miglioramenti
- Logica di calcolo ora corrisponde esattamente al sistema Excel tradizionale
- Calcolo automatico del prezzo al metro cubo in tempo reale
- Visualizzazione dettagliata dei consumi individuali nel riepilogo

### Compatibilità
- I backup della versione 1.0 sono compatibili (miglior gestione importazione)
- I vecchi dati vengono migrati automaticamente al nuovo formato

## [1.0.0] - 2025-04-16

### Release Iniziale

### Funzionalità Base
- Gestione fatture (luce, acqua, assicurazione)
- Configurazione nomi proprietari
- Calcolo ripartizione spese
- Storico periodi chiusi
- Esportazione Excel
- Backup/Restore dati
- Auto-salvataggio
- Persistenza localStorage

### Tecnologie
- HTML5 single-page application
- CSS3 con design responsive
- JavaScript vanilla
- SheetJS per esportazione Excel