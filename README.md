# Gestione Spese Condominiali

Applicazione web per la gestione delle spese condominiali, sviluppata come single-page application HTML/JavaScript.

## Funzionalità

### Gestione Spese
- **Luce Comune**: Ripartizione 50/50 tra proprietari
- **Acqua**: Ripartizione proporzionale ai consumi individuali calcolati sul periodo
- **Assicurazione Annuale**: Ripartizione 50/50 tra proprietari

### Gestione Acqua
La logica di gestione dell'acqua segue il sistema usato tradizionalmente:
- **Caricamento fatture**: Inserimento solo dei dati SMAT (numero bolletta, periodo, tipo lettura, lettura SMAT in m³, bolli, acconto)
- **Letture iniziali periodo**: Impostazione delle letture individuali iniziali all'inizio di ogni periodo
- **Chiusura periodo**: Inserimento delle letture individuali finali per il calcolo dei consumi
- **Calcolo consumi**: Consumo individuale = Lettura finale - Lettura iniziale
- **Calcolo prezzo al mq**: Prezzo/m³ = Totale fatture / Consumo totale periodo
- **Ripartizione proporzionale**: Importo dovuto = Consumo individuale × Prezzo/m³

### Dettagli Fatture
Per ogni fattura è possibile inserire:
- **Tutte le fatture**: Bolli/Commissioni (€)
- **Fatture Acqua**: Numero bolletta, Periodo (DAL - AL), Tipo lettura (stimata/rilevata), Lettura SMAT (m³), Acconto (€)

### Funzionalità Aggiuntive
- **Configurazione nomi**: Personalizzazione dei nomi dei proprietari
- **Modifica fatture**: Possibilità di modificare fatture già inserite
- **Storico periodi**: Archiviazione e consultazione dei periodi chiusi
- **Esportazione Excel**: Export completo di tutti i dati in formato Excel
- **Backup/Restore**: Salvataggio e ripristino dei dati in formato JSON
- **Auto-salvataggio**: Salvataggio automatico ogni 30 secondi
- **Persistenza dati**: Utilizzo di localStorage per mantenere i dati

## Utilizzo

### Configurazione Iniziale
1. Imposta i nomi dei proprietari nella sezione "Configurazione"
2. All'inizio di ogni periodo, imposta le letture iniziali dei contatori individuali nella sezione "Letture Iniziali Periodo"

### Caricamento Fatture Acqua
Quando aggiungi una fattura acqua:
- Inserisci solo i dati della fattura SMAT (numero, periodo, tipo lettura, lettura SMAT in m³, bolli, acconto)
- NON inserire le letture individuali (mio contatore e vicino contatore)

### Chiusura Periodo
Quando chiudi il periodo:
1. Se ci sono fatture acqua, il sistema chiederà le letture finali dei contatori individuali
2. Verranno calcolati i consumi: Lettura finale - Lettura iniziale
3. Verrà calcolato il prezzo al mq: Totale fatture / Consumo totale
4. L'importo verrà ripartito proporzionalmente ai consumi individuali
5. Le fatture verranno archiviate nello storico
6. Le letture iniziali verranno resettate per il nuovo periodo

### Reset Letture Acqua
È possibile resettare le letture iniziali dell'acqua per iniziare un nuovo periodo manualmente usando il pulsante "Reset Letture Acqua".

## Tecnologie

- HTML5
- CSS3 (con design responsive e gradienti)
- JavaScript (vanilla)
- SheetJS (per esportazione Excel)
- LocalStorage (per persistenza dati)

## Installazione

Non è richiesta alcuna installazione. Basta aprire il file `spese_condominiali.html` in un browser web moderno.

## Deployment

### GitLab Pages
Il progetto include configurazione per GitLab Pages (`.gitlab-ci.yml`).

### Server Web Qualsiasi
Essendo un file HTML statico, può essere deployato su qualsiasi server web.

## Backup e Sicurezza

I dati vengono salvati nel localStorage del browser. Si consiglia di:
- Fare regolarmente backup dei dati usando la funzione "Backup Dati"
- Salvare i file di backup in una posizione sicura
- Non salvare i file di backup nel repository (contengono dati personali)

## Licenza

Progetto privato per uso personale.

## Versione

Versione 3.2 - Riepilogo bolli/commissioni e totali comprensivi