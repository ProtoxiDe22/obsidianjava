---
{"dg-publish":true,"permalink":"/java/postgre-sql/"}
---

 ## Introduzione ai Database

### Cos'è un Database?

Un database è una raccolta organizzata di dati che può essere facilmente accessibile, gestita e aggiornata. I database sono utilizzati in quasi tutte le applicazioni moderne per memorizzare informazioni come utenti, transazioni, inventari, ecc.

### Esempio di Database

Pensiamo a un database come a un grande archivio di schede. Ogni scheda contiene informazioni specifiche, e l'archivio è organizzato in modo da poter trovare facilmente la scheda che ci interessa.

---

## Perché Usare un Database?

### Vantaggi di un Database

1. **Organizzazione dei Dati**: I database permettono di organizzare grandi quantità di dati in modo strutturato e logico.
2. **Efficienza**: I database sono ottimizzati per operazioni di lettura e scrittura rapide e efficienti.
3. **Affidabilità**: I database moderni offrono funzioni di backup e ripristino per proteggere i dati dalla perdita.
4. **Sicurezza**: I database permettono di controllare l'accesso ai dati, garantendo che solo utenti autorizzati possano vedere o modificare i dati.
5. **Scalabilità**: I database possono essere scalati per gestire grandi volumi di dati e utenti.
6. **Integrazione**: I database possono essere facilmente integrati con altre applicazioni e sistemi.

### Esempi di Utilizzo dei Database

- **E-commerce**: Per gestire informazioni su prodotti, clienti, ordini e transazioni.
- **Social Media**: Per memorizzare profili utenti, post, commenti e relazioni tra utenti.
- **Banche**: Per tracciare conti correnti, transazioni e informazioni sui clienti.
- **Sanità**: Per conservare cartelle cliniche, appuntamenti e dati dei pazienti.

---

## Tipi di Database

### Database Relazionali

I database relazionali organizzano i dati in tabelle composte da righe e colonne. Ogni riga rappresenta un record unico e ogni colonna rappresenta un attributo dei dati.

### Database NoSQL

I database NoSQL sono progettati per lavorare con grandi quantità di dati non strutturati o semi-strutturati. Includono documenti, grafici, key-value e colonne larghe.

---

## Modello Relazionale

### Concetti Chiave

- **Tabelle**: Collezioni di dati organizzate in righe e colonne.
- **Righe**: Ciascuna riga rappresenta un record.
- **Colonne**: Ciascuna colonna rappresenta un attributo del record.

### Esempio di Tabella

Immaginiamo una tabella chiamata `studenti`:

| ID | Nome   | Cognome | Età |
|----|--------|---------|-----|
| 1  | Mario  | Rossi   | 21  |
| 2  | Luca   | Bianchi | 22  |
| 3  | Anna   | Verdi   | 20  |

---

## SQL: Linguaggio di Query

### Cos'è SQL?

SQL (Structured Query Language) è il linguaggio standard per interagire con i database relazionali. Permette di creare, leggere, aggiornare ed eliminare dati.

### Comandi SQL Principali

- **SELECT**: Recupera dati dalle tabelle.
- **INSERT**: Inserisce nuovi dati.
- **UPDATE**: Aggiorna dati esistenti.
- **DELETE**: Elimina dati.

### Esempio di Query

```sql
-- Selezionare tutti gli studenti
SELECT * FROM studenti;
```

---

## Tabelle e Schemi

### Creazione di Tabelle

Una tabella viene creata con il comando `CREATE TABLE`:

```sql
CREATE TABLE studenti (
    ID serial PRIMARY KEY,
    Nome VARCHAR(50),
    Cognome VARCHAR(50),
    Età INT
);
```

### Schemi di Database

Uno schema è una collezione di oggetti di database (come tabelle e viste) associati a un nome specifico.

---

## Chiavi Primarie e Esterne

### Chiavi Primarie

Una chiave primaria è un attributo o un insieme di attributi che identificano univocamente una riga in una tabella.

```sql
-- ID è la chiave primaria
CREATE TABLE studenti (
    ID serial PRIMARY KEY,
    Nome VARCHAR(50),
    Cognome VARCHAR(50),
    Età INT
);
```

### Chiavi Esterne

Una chiave esterna è un attributo che crea un collegamento tra due tabelle.

```sql
CREATE TABLE corsi (
    CorsoID serial PRIMARY KEY,
    NomeCorso VARCHAR(50)
);

CREATE TABLE iscrizioni (
    StudenteID INT REFERENCES studenti(ID),
    CorsoID INT REFERENCES corsi(CorsoID),
    DataIscrizione DATE
);
```

---

## Operazioni CRUD

### CREATE (Inserire Dati)

```sql
INSERT INTO studenti (Nome, Cognome, Età)
VALUES ('Giulia', 'Neri', 23);
```

### READ (Leggere Dati)

```sql
SELECT * FROM studenti;
```

### UPDATE (Aggiornare Dati)

```sql
UPDATE studenti
SET Età = 24
WHERE Nome = 'Giulia';
```

### DELETE (Eliminare Dati)

```sql
DELETE FROM studenti
WHERE Nome = 'Giulia';
```

---

## Indici e Ottimizzazione

### Creazione di Indici

Gli indici migliorano le performance delle query.

```sql
CREATE INDEX idx_nome
ON studenti (Nome);
```

### Uso degli Indici

Gli indici rendono le query di ricerca più veloci.

```sql
SELECT * FROM studenti
WHERE Nome = 'Mario';
```

### Altre Ottimizzazioni

- **Normalizzazione**: Organizzare i dati per ridurre la ridondanza e migliorare l'integrità.
- **Denormalizzazione**: Talvolta si introduce una certa ridondanza per migliorare le performance di lettura.
- **Query Tuning**: Ottimizzare le query per migliorarne le performance, ad esempio utilizzando subquery, join ottimizzati e query più specifiche.
- **Gestione degli Indici**: Creare indici sui campi più utilizzati nelle query, ma evitando un eccesso di indici che potrebbero rallentare le operazioni di scrittura.

---

## Backup e Ripristino

### Backup

Creare un backup dei dati è fondamentale per prevenire la perdita di informazioni.

```bash
pg_dump -U username -d nome_database -F c -f backup_file
```

### Ripristino

Ripristinare i dati da un backup:

```bash
pg_restore -U username -d nome_database -F c -c backup_file
```

### Strategie di Backup

- **Backup Completo**: Eseguito periodicamente per avere una copia completa del database.
- **Backup Incrementale**: Salva solo le modifiche effettuate dopo l'ultimo backup.
- **Backup Differenziale**: Salva tutte le modifiche effettuate dopo l'ultimo backup completo.

---

## Sicurezza dei Database

### Controllo degli Accessi

Assicurarsi che solo utenti autorizzati possano accedere al database.

```sql
CREATE USER nuovo_utente WITH PASSWORD 'password';
GRANT ALL PRIVILEGES ON DATABASE nome_database TO nuovo_utente;
```

---

## Data Definition Language (DDL)

### Cos'è il DDL?

Il Data Definition Language (DDL) è un sottoinsieme di SQL utilizzato per definire e gestire le strutture di dati nei database. Include comandi per creare, modificare e eliminare tabelle e altri oggetti di database.

### Comandi DDL Principali

1. **CREATE**: Utilizzato per creare oggetti di database come tabelle, viste, indici, ecc.
2. **ALTER**: Utilizzato per modificare la struttura di oggetti di database esistenti.
3. **DROP**: Utilizzato per eliminare oggetti di database.

### Creazione di Tabelle

Il comando `CREATE TABLE` viene utilizzato per creare una nuova tabella nel database.

```sql
CREATE TABLE studenti (
    ID serial PRIMARY KEY,
    Nome VARCHAR(50),
    Cognome VARCHAR(50),
    Età INT
);
```

### Modifica di Tabelle

Il comando `ALTER TABLE` viene utilizzato per modific

are una tabella esistente. Ad esempio, per aggiungere una nuova colonna:

```sql
ALTER TABLE studenti
ADD COLUMN Indirizzo VARCHAR(100);
```

Per modificare una colonna esistente:

```sql
ALTER TABLE studenti
ALTER COLUMN Età SET NOT NULL;
```

### Eliminazione di Tabelle

Il comando `DROP TABLE` viene utilizzato per eliminare una tabella dal database.

```sql
DROP TABLE studenti;
```

### Best Practices nella Creazione di un Database

1. **Pianificazione**: Prima di creare un database, è importante pianificare la struttura dei dati. Identificare le tabelle necessarie e le relazioni tra di esse.
2. **Normalizzazione**: Applicare i principi di normalizzazione per ridurre la ridondanza dei dati e migliorare l'integrità.
3. **Nomi Significativi**: Utilizzare nomi chiari e significativi per tabelle e colonne per rendere il database più leggibile.
4. **Documentazione**: Documentare la struttura del database e i dettagli delle tabelle e delle relazioni.
5. **Utilizzo di Indici**: Creare indici sui campi utilizzati frequentemente nelle query per migliorare le performance.
6. **Controllo degli Accessi**: Definire ruoli e permessi per garantire la sicurezza dei dati.
7. **Backup Regolari**: Pianificare backup regolari del database per prevenire la perdita di dati.
8. **Monitoraggio e Ottimizzazione**: Monitorare le performance del database e ottimizzare le query e la struttura quando necessario.

---


## Tipi di Dati in PostgreSQL

## Tipi di Dati Numerici

### Interi

- `SMALLINT`: Intero a 2 byte, range da -32,768 a 32,767.
- `INTEGER`: Intero a 4 byte, range da -2,147,483,648 a 2,147,483,647.
- `BIGINT`: Intero a 8 byte, range da -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807.

```sql
CREATE TABLE esempio_interi (
    id SERIAL PRIMARY KEY,
    piccolo SMALLINT,
    medio INTEGER,
    grande BIGINT
);
```

### Numeri a Virgola Mobile

- `REAL`: Numero a virgola mobile a precisione singola (4 byte).
- `DOUBLE PRECISION`: Numero a virgola mobile a precisione doppia (8 byte).
- `NUMERIC(p, s)`: Numero esatto con precisione p e scala s.

```sql
CREATE TABLE esempio_decimali (
    id SERIAL PRIMARY KEY,
    valore_reale REAL,
    valore_doppio DOUBLE PRECISION,
    valore_numerico NUMERIC(10, 2)
);
```

---

## Tipi di Dati di Carattere

### Caratteri

- `CHAR(n)`: Stringa di lunghezza fissa n.
- `VARCHAR(n)`: Stringa di lunghezza variabile fino a n caratteri.
- `TEXT`: Stringa di lunghezza variabile senza limite specifico.

```sql
CREATE TABLE esempio_caratteri (
    id SERIAL PRIMARY KEY,
    codice CHAR(10),
    descrizione VARCHAR(255),
    commento TEXT
);
```

---

## Tipi di Dati Data e Ora

### Date e Ora

- `DATE`: Data (anno, mese, giorno).
- `TIME`: Ora del giorno (senza fuso orario).
- `TIMESTAMP`: Data e ora (senza fuso orario).
- `TIMESTAMPTZ`: Data e ora con fuso orario.
- `INTERVAL`: Periodo di tempo.

```sql
CREATE TABLE esempio_temporali (
    id SERIAL PRIMARY KEY,
    data_nascita DATE,
    ora_evento TIME,
    data_ora TIMESTAMP,
    data_ora_fuso TIMESTAMPTZ,
    durata INTERVAL
);
```

---

## Tipi di Dati Booleani

### Booleani

- `BOOLEAN`: Vero (`TRUE`), falso (`FALSE`), o nullo (`NULL`).

```sql
CREATE TABLE esempio_booleano (
    id SERIAL PRIMARY KEY,
    attivo BOOLEAN
);
```
## Tipi di Dati Monetari

### Monetari

- `MONEY`: Tipo di dati monetari.

```sql
CREATE TABLE esempio_moneta (
    id SERIAL PRIMARY KEY,
    valore MONEY
);
```


## Tipi di Dati UUID

### UUID

- `UUID`: Identificatore univoco universale.

```sql
CREATE TABLE esempio_uuid (
    id UUID PRIMARY KEY,
    nome VARCHAR(50)
);
```

---

## Tipi di Dati Personalizzati

### Creazione di Tipi di Dati Personalizzati

PostgreSQL permette di creare tipi di dati personalizzati per adattarsi a esigenze specifiche.

```sql
CREATE TYPE stato_ordine AS ENUM ('nuovo', 'in lavorazione', 'spedito', 'consegnato');

CREATE TABLE esempio_personalizzato (
    id SERIAL PRIMARY KEY,
    stato stato_ordine
);
```

---
## Funzioni Utilizzate nelle Tabelle PostgreSQL

### Introduzione alle Funzioni in PostgreSQL

PostgreSQL offre diverse funzioni che possono essere utilizzate per semplificare la gestione e la manipolazione dei dati nelle tabelle. Queste funzioni possono aiutare a creare identificatori unici, gestire date e ore, e molto altro.

### Funzione `SERIAL`

La funzione `SERIAL` è un tipo speciale di dato che viene utilizzato per generare automaticamente valori unici incrementali per una colonna. È spesso usata per le chiavi primarie.

```sql
CREATE TABLE esempio_serial (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50)
);
```

---
### Funzione `NOW()`

La funzione `NOW()` restituisce la data e l'ora corrente. È utile per impostare timestamp di creazione o aggiornamento dei record.

```sql
CREATE TABLE esempio_timestamp (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50),
    creato_il TIMESTAMP DEFAULT NOW()
);
```

### Funzione `CURRENT_DATE` e `CURRENT_TIME`

Queste funzioni restituiscono rispettivamente la data corrente e l'ora corrente.

```sql
CREATE TABLE esempio_data_ora (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50),
    data_corrente DATE DEFAULT CURRENT_DATE,
    ora_corrente TIME DEFAULT CURRENT_TIME
);
```

### Funzione `AGE()`

La funzione `AGE()` calcola la differenza tra due date, restituendo un intervallo di tempo.

```sql
CREATE TABLE esempio_eta (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50),
    data_nascita DATE,
    eta INTERVAL GENERATED ALWAYS AS (AGE(NOW(), data_nascita)) STORED
);
```

---
### Funzione `UUID_GENERATE_V4()`

Per generare identificatori unici universali (UUID), è possibile utilizzare la funzione `UUID_GENERATE_V4()`. Prima di utilizzare questa funzione, è necessario installare l'estensione `uuid-ossp`.

```sql
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";

CREATE TABLE esempio_uuid (
    id UUID DEFAULT uuid_generate_v4() PRIMARY KEY,
    nome VARCHAR(50)
);
```

### Funzione `CONCAT()`

La funzione `CONCAT()` concatena più stringhe in una singola stringa.

```sql
CREATE TABLE esempio_concat (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50),
    cognome VARCHAR(50),
    nome_completo VARCHAR(101) GENERATED ALWAYS AS (CONCAT(nome, ' ', cognome)) STORED
);
```

### Funzione `COALESCE()`

La funzione `COALESCE()` restituisce il primo valore non nullo tra gli argomenti forniti.

```sql
CREATE TABLE esempio_coalesce (
    id SERIAL PRIMARY KEY,
    valore1 INT,
    valore2 INT,
    valore_non_nullo INT GENERATED ALWAYS AS (COALESCE(valore1, valore2, 0)) STORED
);
```

Queste funzioni sono solo una parte delle numerose funzionalità offerte da PostgreSQL per la gestione avanzata dei dati. Utilizzarle correttamente può migliorare notevolmente l'efficienza e la funzionalità delle applicazioni che dipendono dal database.

---
## Relazioni in PostgreSQL

### Introduzione alle Relazioni

Le relazioni nei database rappresentano i collegamenti logici tra diverse tabelle. In PostgreSQL, come in altri sistemi di gestione di database relazionali, le relazioni permettono di organizzare i dati in modo efficiente e strutturato, riducendo la ridondanza e migliorando l'integrità dei dati.

### Tipi di Relazioni

1. **Uno-a-Uno (One-to-One)**
2. **Uno-a-Molti (One-to-Many)**
3. **Molti-a-Molti (Many-to-Many)**

---

### Relazione Uno-a-Uno (One-to-One)

In una relazione uno-a-uno, ogni record in una tabella è collegato a uno e solo uno record in un'altra tabella. Questo tipo di relazione è meno comune e viene utilizzato quando si desidera dividere una tabella in due per motivi di organizzazione o sicurezza.

#### Implementazione di una Relazione Uno-a-Uno

```sql
CREATE TABLE utenti (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50)
);

CREATE TABLE profili (
    id SERIAL PRIMARY KEY,
    utente_id INT UNIQUE,
    data_nascita DATE,
    FOREIGN KEY (utente_id) REFERENCES utenti(id)
);
```

In questo esempio, ogni utente ha un profilo unico, e ogni profilo appartiene a un solo utente.

---

### Relazione Uno-a-Molti (One-to-Many)

In una relazione uno-a-molti, un record in una tabella può essere collegato a più record in un'altra tabella. Questo è il tipo di relazione più comune nei database relazionali.

#### Implementazione di una Relazione Uno-a-Molti

```sql
CREATE TABLE categorie (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50)
);

CREATE TABLE prodotti (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50),
    categoria_id INT,
    FOREIGN KEY (categoria_id) REFERENCES categorie(id)
);
```

In questo esempio, ogni categoria può avere molti prodotti, ma ogni prodotto appartiene a una sola categoria.

---

### Relazione Molti-a-Molti (Many-to-Many)

In una relazione molti-a-molti, più record in una tabella possono essere collegati a più record in un'altra tabella. Per implementare questo tipo di relazione, si utilizza una tabella intermedia.

#### Implementazione di una Relazione Molti-a-Molti

```sql
CREATE TABLE studenti (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50)
);

CREATE TABLE corsi (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50)
);

CREATE TABLE iscrizioni (
    studente_id INT,
    corso_id INT,
    PRIMARY KEY (studente_id, corso_id),
    FOREIGN KEY (studente_id) REFERENCES studenti(id),
    FOREIGN KEY (corso_id) REFERENCES corsi(id)
);
```

In questo esempio, uno studente può iscriversi a molti corsi e un corso può avere molti studenti iscritti. La tabella `iscrizioni` gestisce la relazione molti-a-molti tra studenti e corsi.

---

### Best Practices per le Relazioni

1. **Utilizzare Chiavi Esterne**: Le chiavi esterne (foreign key) assicurano l'integrità referenziale tra le tabelle.
2. **Indice sulle Chiavi Esterne**: Creare indici sulle colonne che contengono chiavi esterne per migliorare le performance delle query.
3. **Nomi Significativi**: Dare nomi chiari e significativi alle chiavi esterne e alle tabelle intermedie.
4. **Documentazione**: Documentare le relazioni tra tabelle per rendere il database più facile da comprendere e mantenere.
5. **Normalizzazione**: Applicare i principi di normalizzazione per ridurre la ridondanza dei dati e migliorare la struttura del database.

---
## Creazione di Query e DML in PostgreSQL

### Introduzione alle Query e al DML

Le query in SQL permettono di recuperare, inserire, aggiornare e cancellare dati in un database. Il DML (Data Manipulation Language) comprende i comandi `SELECT`, `INSERT`, `UPDATE` e `DELETE`, che sono utilizzati per gestire i dati all'interno delle tabelle.

---

## SELECT

Il comando `SELECT` è utilizzato per recuperare i dati dalle tabelle. È il comando più utilizzato in SQL ed offre diverse opzioni per filtrare, ordinare e aggregare i dati.

### Sintassi Base di SELECT

```sql
SELECT colonne
FROM tabella;
```
Questa è la sintassi di base del comando `SELECT`. `colonne` rappresenta le colonne che desideri recuperare e `tabella` è la tabella da cui vuoi ottenere i dati.

### Selezionare Tutte le Colonne

```sql
SELECT *
FROM utenti;
```
Questo comando seleziona tutte le colonne dalla tabella `utenti`. L'asterisco (`*`) indica che devono essere recuperate tutte le colonne.

### Selezionare Colonne Specifiche

```sql
SELECT nome, email
FROM utenti;
```
Questo comando seleziona solo le colonne `nome` ed `email` dalla tabella `utenti`.

### Utilizzo di Alias per le Colonne

Gli alias sono utilizzati per rinominare le colonne nei risultati della query.

```sql
SELECT nome AS "Nome Utente", email AS "Indirizzo Email"
FROM utenti;
```
In questo esempio, la colonna `nome` sarà visualizzata come "Nome Utente" e la colonna `email` come "Indirizzo Email" nei risultati della query.

---

## WHERE

La clausola `WHERE` è utilizzata per filtrare i record che soddisfano una condizione specifica.

### Condizioni Base

```sql
SELECT nome, email
FROM utenti
WHERE età > 18;
```
Questo comando seleziona i nomi e le email degli utenti che hanno più di 18 anni. La condizione `età > 18` filtra i risultati per includere solo gli utenti con età maggiore di 18.

### Utilizzo di Operatori Logici

Gli operatori logici permettono di combinare più condizioni all'interno di una clausola `WHERE`.

- `AND`: entrambe le condizioni devono essere vere.
- `OR`: almeno una delle condizioni deve essere vera.
- `NOT`: la condizione deve essere falsa.

```sql
SELECT nome, email
FROM utenti
WHERE età > 18 AND città = 'Roma';
```
In questo esempio, vengono selezionati i nomi e le email degli utenti che hanno più di 18 anni e vivono a Roma. L'operatore `AND` è utilizzato per combinare due condizioni.

```sql
SELECT nome, email
FROM utenti
WHERE età < 18 OR città = 'Milano';
```
Questo comando seleziona i nomi e le email degli utenti che hanno meno di 18 anni o vivono a Milano. L'operatore `OR` permette di includere i record che soddisfano almeno una delle due condizioni.

```sql
SELECT nome, email
FROM utenti
WHERE NOT età > 18;
```
In questo esempio, vengono selezionati i nomi e le email degli utenti che non hanno più di 18 anni. L'operatore `NOT` inverte la condizione.

### Utilizzo di Operatori di Confronto

Gli operatori di confronto sono utilizzati per confrontare i valori nelle condizioni `WHERE`.

- `=`: uguale a.
- `<>` o `!=`: diverso da.
- `>`: maggiore di.
- `<`: minore di.
- `>=`: maggiore o uguale a.
- `<=`: minore o uguale a.

```sql
SELECT nome, email
FROM utenti
WHERE età = 18;
```
Questo comando seleziona i nomi e le email degli utenti che hanno esattamente 18 anni. L'operatore `=` è utilizzato per confrontare se `età` è uguale a 18.

```sql
SELECT nome, email
FROM utenti
WHERE età <> 18;
```
In questo esempio, vengono selezionati i nomi e le email degli utenti che non hanno 18 anni. L'operatore `<>` (o `!=`) è utilizzato per confrontare se `età` è diverso da 18.

### Filtrare con LIKE

`LIKE` è utilizzato per cercare un pattern specifico.

```sql
SELECT nome, email
FROM utenti
WHERE nome LIKE 'A%'; -- nomi che iniziano con 'A'
```
Questo comando seleziona i nomi e le email degli utenti i cui nomi iniziano con la lettera 'A'. Il simbolo `%` rappresenta una sequenza di caratteri qualsiasi.

### Filtrare con IN

`IN` è utilizzato per specificare più valori in una condizione `WHERE`.

```sql
SELECT nome, email
FROM utenti
WHERE città IN ('Roma', 'Milano', 'Napoli');
```
Questo comando seleziona i nomi e le email degli utenti che vivono a Roma, Milano o Napoli. La clausola `IN` permette di specificare una lista di valori.

### Filtrare con BETWEEN

`BETWEEN` è utilizzato per selezionare un range di valori.

```sql
SELECT nome, data_nascita
FROM utenti
WHERE data_nascita BETWEEN '2000-01-01' AND '2010-12-31';
```
Questo comando seleziona i nomi e le date di nascita degli utenti nati tra il 1 gennaio 2000 e il 31 dicembre 2010. La clausola `BETWEEN` definisce l'intervallo di date.

### Filtrare con IS NULL

`IS NULL` è utilizzato per trovare i valori nulli.

```sql
SELECT nome, email
FROM utenti
WHERE email IS NULL;
```
Questo comando seleziona i nomi degli utenti che non hanno un indirizzo email registrato. La condizione `IS NULL` filtra i risultati per includere solo i record con valori nulli.

---

## ORDER BY

`ORDER BY` è utilizzato per ordinare i risultati della query.

### Ordinare in Ordine Crescente

```sql
SELECT nome, email
FROM utenti
ORDER BY nome ASC;
```
Questo comando ordina i risultati della query in base ai nomi degli utenti in ordine crescente. L'operatore `ASC` specifica l'ordine crescente (default).

### Ordinare in Ordine Decrescente

```sql
SELECT nome, email
FROM utenti
ORDER BY nome DESC;
```
Questo comando ordina i risultati della query in base ai nomi degli utenti in ordine decrescente. L'operatore `DESC` specifica l'ordine decrescente.

---

## DISTINCT

`DISTINCT` è utilizzato per selezionare solo valori unici.

```sql
SELECT DISTINCT città
FROM utenti;
```
Questo comando seleziona le città uniche dalla tabella `utenti`. `DISTINCT` rimuove i duplicati dai risultati della query.

---

## LIMIT e OFFSET

`LIMIT` è utilizzato per limitare il numero di righe restituite. `OFFSET` è utilizzato per saltare un numero specifico di righe.

### Utilizzo di LIMIT

```sql
SELECT nome, email
FROM utenti
LIMIT 10;
```
Questo comando seleziona i primi 10 record dalla tabella `utenti`. La clausola `LIMIT` limita il numero di risultati a 10.

### Utilizzo di OFFSET

```sql
SELECT nome, email
FROM utenti
LIMIT 10 OFFSET 5; -- Salta i primi 5 risultati e mostra i successivi 10
```
Questo comando salta i primi 5 record e seleziona i successivi 10 dalla tabella `utenti`. La clausola `OFFSET` specifica il numero di righe da saltare.

---

## Funzioni Aggregate

Le funzioni aggregate eseguono un calcolo su un set di valori e restituiscono un singolo valore.

### COUNT

```sql
SELECT COUNT(*)
FROM utenti;
```
Questo comando conta il numero totale di record nella tabella `utenti`. La funzione `COUNT(*)` restituisce il numero totale di righe.

### SUM

```sql
SELECT SUM(saldo)
FROM conti_correnti;
```
Questo comando calcola la somma dei saldi di tutti i conti correnti. La funzione `SUM` restituisce la somma dei valori di una colonna numerica.

### AVG

```sql
SELECT AVG(età)
FROM utenti;
```
Questo comando calcola l'età media degli utenti. La funzione `AVG` restituisce il valore medio di una colonna numerica.

### MAX e MIN

```sql
SELECT MAX(età), MIN(età)
FROM utenti;
```
Questo comando restituisce l'età massima e minima degli utenti. Le funzioni `MAX` e `MIN` restituiscono rispettivamente il valore massimo e minimo di una colonna.

---

## GROUP BY

`GROUP BY` è utilizzato per raggruppare i risultati della query basati su uno o più colonne.

### Raggruppamento e Funzioni Aggregate

```sql
SELECT città, COUNT(*)
FROM utenti
GROUP BY città;
```
Questo comando raggruppa i record della tabella `utenti` per città e conta il numero di utenti in ciascuna città. La clausola `GROUP BY` è utilizzata per aggregare i dati.

---

## HAVING

`HAVING` è utilizzato per filtrare i gruppi di risultati creati con `GROUP BY`.

```sql
SELECT città, COUNT(*)
FROM utenti
GROUP BY città
HAVING COUNT(*) > 10;
```
Questo comando raggruppa i record della tabella `utenti` per città, conta il numero di utenti in ciascuna città e restituisce solo le città con più di 10 utenti. La clausola `HAVING` filtra i gruppi di dati aggregati.

---

## INSERT

Il comando `INSERT` è utilizzato per aggiungere nuovi record in una tabella.

### Sintassi Base di INSERT

```sql
INSERT INTO utenti (nome, email)
VALUES ('Mario Rossi', 'mario.rossi@example.com');
```
Questo comando inserisce un nuovo record nella tabella `utenti` con i valori specificati per le colonne `nome` ed `email`.

### Inserire Più Record

```sql
INSERT INTO utenti (nome, email)
VALUES ('Luca Bianchi', 'luca.bianchi@example.com'),
       ('Anna Verdi', 'anna.verdi@example.com');
```
Questo comando inserisce due nuovi record nella tabella `utenti`. Ogni set di valori è separato da una virgola.

---

## UPDATE

Il comando `UPDATE` è utilizzato per modificare i record esistenti in una tabella.

### Sintassi Base di UPDATE

```sql
UPDATE utenti
SET email = 'nuovo.email@example.com'
WHERE nome = 'Mario Rossi';
```
Questo comando aggiorna l'indirizzo email dell'utente con il nome 'Mario Rossi'. La clausola `SET` specifica le colonne da aggiornare e `WHERE` filtra i record da modificare.

### Aggiornare Più Colonne



```sql
UPDATE utenti
SET email = 'nuovo.email@example.com', città = 'Torino'
WHERE nome = 'Mario Rossi';
```
Questo comando aggiorna sia l'indirizzo email che la città dell'utente con il nome 'Mario Rossi'.

---

## DELETE

Il comando `DELETE` è utilizzato per rimuovere i record da una tabella.

### Sintassi Base di DELETE

```sql
DELETE FROM utenti
WHERE nome = 'Mario Rossi';
```
Questo comando rimuove il record dell'utente con il nome 'Mario Rossi' dalla tabella `utenti`.

### Cancellare Tutti i Record (Con Cautela)

```sql
DELETE FROM utenti;
```
Questo comando rimuove tutti i record dalla tabella `utenti`. Utilizzare con cautela poiché rimuove tutti i dati dalla tabella.

---
## Creazione di Query con Relazioni tra Tabelle

Le relazioni tra tabelle sono fondamentali per strutturare i dati in un database relazionale. Le relazioni permettono di collegare dati tra diverse tabelle utilizzando chiavi primarie e chiavi esterne. In PostgreSQL, possiamo usare i vari tipi di join per combinare i dati da tabelle diverse basandoci su queste relazioni.

### Tipi di Join

I join sono utilizzati per combinare righe da due o più tabelle in base a una condizione correlata tra di loro. I principali tipi di join sono:

- **INNER JOIN**
- **LEFT JOIN (o LEFT OUTER JOIN)**
- **RIGHT JOIN (o RIGHT OUTER JOIN)**
- **FULL JOIN (o FULL OUTER JOIN)**
- **CROSS JOIN**

---
### INNER JOIN

Un `INNER JOIN` restituisce solo le righe che hanno corrispondenze in entrambe le tabelle.

#### Sintassi

```sql
SELECT colonne
FROM tabella1
INNER JOIN tabella2 ON tabella1.colonna = tabella2.colonna;
```

#### Esempio

Supponiamo di avere due tabelle: `utenti` e `ordini`. La tabella `utenti` contiene informazioni sugli utenti, mentre la tabella `ordini` contiene informazioni sugli ordini effettuati dagli utenti.

#### Tabelle di Esempio

##### Tabella utenti

| id  | nome        | email                |
|-----|-------------|----------------------|
| 1   | Mario Rossi | mario@example.com    |
| 2   | Anna Bianchi| anna@example.com     |
| 3   | Luca Verdi  | luca@example.com     |

##### Tabella ordini

| numero_ordine | utente_id | data_ordine  |
|---------------|-----------|--------------|
| 101           | 1         | 2024-01-01   |
| 102           | 2         | 2024-01-02   |
| 103           | 4         | 2024-01-03   |

#### Query

```sql
SELECT utenti.nome, ordini.numero_ordine
FROM utenti
INNER JOIN ordini ON utenti.id = ordini.utente_id;
```

#### Risultato

| nome        | numero_ordine |
|-------------|---------------|
| Mario Rossi | 101           |
| Anna Bianchi| 102           |

Questo comando seleziona i nomi degli utenti e i numeri degli ordini per quegli utenti che hanno effettuato ordini. La condizione `ON utenti.id = ordini.utente_id` stabilisce la relazione tra le tabelle `utenti` e `ordini`, dove `id` è la chiave primaria della tabella `utenti` e `utente_id` è la chiave esterna nella tabella `ordini`.

---
### LEFT JOIN

Un `LEFT JOIN` restituisce tutte le righe dalla tabella di sinistra (tabella1) e le righe corrispondenti dalla tabella di destra (tabella2). Se non ci sono corrispondenze, i risultati conterranno `NULL` per le colonne della tabella di destra.

#### Sintassi

```sql
SELECT colonne
FROM tabella1
LEFT JOIN tabella2 ON tabella1.colonna = tabella2.colonna;
```

#### Query

```sql
SELECT utenti.nome, ordini.numero_ordine
FROM utenti
LEFT JOIN ordini ON utenti.id = ordini.utente_id;
```

#### Risultato

| nome        | numero_ordine |
|-------------|---------------|
| Mario Rossi | 101           |
| Anna Bianchi| 102           |
| Luca Verdi  | NULL          |

Questo comando seleziona tutti i nomi degli utenti e i numeri degli ordini. Per gli utenti che non hanno effettuato ordini, i risultati conterranno `NULL` per le colonne della tabella `ordini`. In questo modo, possiamo ottenere un elenco completo degli utenti, indipendentemente dal fatto che abbiano effettuato ordini o meno.

---
### RIGHT JOIN

Un `RIGHT JOIN` è simile al `LEFT JOIN`, ma restituisce tutte le righe dalla tabella di destra (tabella2) e le righe corrispondenti dalla tabella di sinistra (tabella1). Se non ci sono corrispondenze, i risultati conterranno `NULL` per le colonne della tabella di sinistra.

#### Sintassi

```sql
SELECT colonne
FROM tabella1
RIGHT JOIN tabella2 ON tabella1.colonna = tabella2.colonna;
```

#### Query

```sql
SELECT utenti.nome, ordini.numero_ordine
FROM utenti
RIGHT JOIN ordini ON utenti.id = ordini.utente_id;
```

#### Risultato

| nome        | numero_ordine |
|-------------|---------------|
| Mario Rossi | 101           |
| Anna Bianchi| 102           |
| NULL        | 103           |

Questo comando seleziona tutti i numeri degli ordini e i nomi degli utenti. Per gli ordini che non hanno un utente corrispondente, i risultati conterranno `NULL` per le colonne della tabella `utenti`. In questo modo, possiamo ottenere un elenco completo degli ordini, indipendentemente dal fatto che siano associati a un utente o meno.

---
### FULL JOIN

Un `FULL JOIN` restituisce tutte le righe quando c'è una corrispondenza in una delle due tabelle. Se non ci sono corrispondenze, i risultati conterranno `NULL` per le colonne della tabella che non ha la corrispondenza.

#### Sintassi

```sql
SELECT colonne
FROM tabella1
FULL JOIN tabella2 ON tabella1.colonna = tabella2.colonna;
```

#### Query

```sql
SELECT utenti.nome, ordini.numero_ordine
FROM utenti
FULL JOIN ordini ON utenti.id = ordini.utente_id;
```

#### Risultato

| nome         | numero_ordine |
| ------------ | ------------- |
| Mario Rossi  | 101           |
| Anna Bianchi | 102           |
| Luca Verdi   | NULL          |
| NULL         | 103           |

Questo comando seleziona tutti i nomi degli utenti e i numeri degli ordini. Se un utente non ha effettuato ordini, i risultati conterranno `NULL` per le colonne della tabella `ordini`. Allo stesso modo, se un ordine non ha un utente corrispondente, i risultati conterranno `NULL` per le colonne della tabella `utenti`. In questo modo, possiamo ottenere un elenco completo degli utenti e degli ordini, indipendentemente dal fatto che siano associati tra loro o meno.

---
### CROSS JOIN

Un `CROSS JOIN` restituisce il prodotto cartesiano delle due tabelle. Ogni riga della tabella di sinistra viene combinata con ogni riga della tabella di destra.

#### Sintassi

```sql
SELECT colonne
FROM tabella1
CROSS JOIN tabella2;
```

#### Query

```sql
SELECT utenti.nome, ordini.numero_ordine
FROM utenti
CROSS JOIN ordini;
```

#### Risultato

| nome        | numero_ordine |
|-------------|---------------|
| Mario Rossi | 101           |
| Mario Rossi | 102           |
| Mario Rossi | 103           |
| Anna Bianchi| 101           |
| Anna Bianchi| 102           |
| Anna Bianchi| 103           |
| Luca Verdi  | 101           |
| Luca Verdi  | 102           |
| Luca Verdi  | 103           |

Questo comando combina ogni utente con ogni ordine, restituendo tutte le possibili combinazioni di nomi degli utenti e numeri degli ordini. Il prodotto cartesiano può risultare in un gran numero di righe, quindi va utilizzato con cautela.

---
### Utilizzo di JOIN con Alias

Gli alias possono semplificare la scrittura delle query e migliorare la leggibilità.

```sql
SELECT u.nome, o.numero_ordine
FROM utenti AS u
INNER JOIN ordini AS o ON u.id = o.utente_id;
```

#### Spiegazione

In questo esempio, `utenti` è aliasato come `u` e `ordini` è aliasato come `o`. Gli alias rendono il codice più breve e leggibile, specialmente quando si lavora con molte tabelle.

### JOIN con Più Tabelle

È possibile eseguire join su più di due tabelle.

#### Tabelle di Esempio

##### Tabella prodotti

| id  | nome_prodotto |
|-----|---------------|
| 1   | Prodotto A    |
| 2   | Prodotto B    |

##### Tabella ordini

| numero_ordine | utente_id | prodotto_id | data_ordine  |
|---------------|-----------|-------------|--------------|
| 101           | 1         | 1           | 2024-01-01   |
| 102           | 2         | 2           | 2024-01-02   |
| 103           | 4         | 1           | 2024-01-03   |

#### Query

```sql
SELECT u.nome, o.numero_ordine, p.nome_prodotto
FROM utenti AS u
INNER JOIN ordini AS o ON u.id = o.utente_id
INNER JOIN

 prodotti AS p ON o.prodotto_id = p.id;
```

#### Risultato

| nome        | numero_ordine | nome_prodotto |
|-------------|---------------|---------------|
| Mario Rossi | 101           | Prodotto A    |
| Anna Bianchi| 102           | Prodotto B    |

Questo comando seleziona i nomi degli utenti, i numeri degli ordini e i nomi dei prodotti associati a ciascun ordine. La query utilizza due `INNER JOIN` per collegare tre tabelle: `utenti`, `ordini` e `prodotti`.
