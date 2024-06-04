---
{"dg-publish":true,"permalink":"/java/08-esercizi/esercizi-oop/"}
---



### Esercizi di Programmazione Orientata agli Oggetti in Java

#### Esercizio 1: Definizione di Classi e Oggetti
1. Crea una classe `Persona` con le proprietà `nome` (String) e `età` (int). 
2. Aggiungi un costruttore che inizializza entrambe le proprietà.
3. Aggiungi metodi getter e setter per entrambe le proprietà.
4. Crea una classe `TestPersona` con un metodo `main` che crea un oggetto `Persona` e stampa i suoi dettagli.

#### Esercizio 2: Ereditarietà
1. Crea una classe `Veicolo` con le proprietà `marca` (String) e `modello` (String) e un metodo `mostraDettagli`.
2. Crea una sottoclasse `Auto` che estende `Veicolo` e aggiungi la proprietà `numeroPorte` (int).
3. Sovrascrivi il metodo `mostraDettagli` in `Auto` per includere `numeroPorte`.
4. Crea una classe `TestVeicolo` con un metodo `main` che crea un oggetto `Auto` e chiama `mostraDettagli`.

#### Esercizio 3: Incapsulamento
1. Crea una classe `ContoBancario` con le proprietà `saldo` (double) e `numeroConto` (String).
2. Rendi `saldo` privato e aggiungi metodi getter e setter per esso.
3. Aggiungi metodi `deposita` e `preleva` per modificare il `saldo`.
4. Crea una classe `TestContoBancario` con un metodo `main` che crea un oggetto `ContoBancario`, deposita e preleva denaro, e stampa il saldo.

#### Esercizio 4: Polimorfismo
1. Crea una classe astratta `Animale` con un metodo astratto `verso`.
2. Crea due classi `Cane` e `Gatto` che estendono `Animale` e implementano il metodo `verso`.
3. Crea una classe `TestAnimale` con un metodo `main` che crea oggetti `Cane` e `Gatto` e chiama il metodo `verso`.

#### Esercizio 5: Interazione tra Oggetti
1. Crea una classe `Libro` con le proprietà `titolo` (String) e `autore` (String).
2. Crea una classe `Biblioteca` con una lista di libri.
3. Aggiungi metodi per aggiungere e rimuovere libri dalla biblioteca.
4. Crea una classe `TestBiblioteca` con un metodo `main` che aggiunge e rimuove libri e stampa i dettagli dei libri nella biblioteca.

#### Esercizio 6: Modularità
1. Crea un'interfaccia `Volante` con il metodo `vola`.
2. Crea un'interfaccia `Nuotante` con il metodo `nuota`.
3. Crea una classe `Anatra` che implementa entrambe le interfacce e fornisce l'implementazione dei metodi `vola` e `nuota`.
4. Crea una classe `TestAnatra` con un metodo `main` che crea un oggetto `Anatra` e chiama i metodi `vola` e `nuota`.


### Esercizi Complessi di Programmazione Orientata agli Oggetti in Java

#### Esercizio 1: Sistema di Gestione di Biblioteca
In questo esercizio, si richiede di creare un sistema di gestione di una biblioteca utilizzando i concetti di interfaccia, overload e override dei metodi, e l'uso di metodi getter e setter.

1. Crea un'interfaccia `ElementoBiblioteca` con i metodi `getTitolo` e `mostraDettagli`.
2. Crea una classe astratta `Pubblicazione` che implementa `ElementoBiblioteca` e contiene le proprietà `titolo` e `autore`, con relativi getter e setter.
3. Crea una classe `Libro` che estende `Pubblicazione` e aggiunge la proprietà `numeroPagine`. Implementa il metodo `mostraDettagli` per visualizzare titolo, autore e numero di pagine.
4. Crea una classe `Rivista` che estende `Pubblicazione` e aggiunge la proprietà `numeroRivista`. Implementa il metodo `mostraDettagli` per visualizzare titolo, autore e numero della rivista.
5. Crea una classe `Biblioteca` con una lista di `ElementoBiblioteca`. Aggiungi metodi per aggiungere un `ElementoBiblioteca`, rimuovere un `ElementoBiblioteca` e visualizzare i dettagli di tutti gli elementi.
6. Crea una classe `TestBiblioteca` con un metodo `main` che crea una biblioteca, aggiunge libri e riviste, e visualizza i dettagli degli elementi nella biblioteca.

#### Esercizio 2: Gestione di un Negozio di Animali
In questo esercizio, si richiede di creare un sistema di gestione di un negozio di animali utilizzando i concetti di interfaccia, overload e override dei metodi, e l'uso di metodi getter e setter.

1. Crea un'interfaccia `Animale` con i metodi `getNome` e `mostraDettagli`.
2. Crea una classe astratta `AnimaleDomestico` che implementa `Animale` e contiene le proprietà `nome` e `età`, con relativi getter e setter.
3. Crea una classe `Cane` che estende `AnimaleDomestico` e aggiunge la proprietà `razza`. Implementa il metodo `mostraDettagli` per visualizzare nome, età e razza. La proprietà `razza` deve accettare solo razze valide
5. Crea una classe `Gatto` che estende `AnimaleDomestico` e aggiunge la proprietà `colore`. Implementa il metodo `mostraDettagli` per visualizzare nome, età e colore. 
6. Crea una classe `NegozioAnimali` con una lista di `Animale`. Aggiungi metodi per aggiungere un `Animale`, rimuovere un `Animale` e visualizzare i dettagli di tutti gli animali.
7. Crea una classe `TestNegozioAnimali` con un metodo `main` che crea un negozio di animali, aggiunge cani e gatti, e visualizza i dettagli degli animali nel negozio.

#### Esercizio 3: Gestione di un Negozio di Libri

In questo esercizio, si richiede di creare una classe `NegozioLibri` che gestisca la vendita di libri con diverse modalità. Implementeremo l'overloading dei metodi per aggiungere libri al catalogo e per calcolare il totale del prezzo dei libri nel carrello.

1. Crea una classe `Libro` che rappresenti un libro con proprietà `titolo`, `autore` e `prezzo`.
2. Crea una classe `NegozioLibri` con metodi per aggiungere libri al catalogo e al carrello.
3. Implementa il metodo `aggiungiLibro` per aggiungere un libro al catalogo usando l'oggetto `Libro`.
4. Implementa il metodo `aggiungiLibro` per aggiungere un libro al catalogo usando il titolo, l'autore e il prezzo.
5. Implementa il metodo `aggiugiAlCarrello` per aggiungere un libro al carrello usando il nome del libro (che deve essere presente nel catalogo)
6. Implementa il metodo `calcolaTotale` per calcolare il totale del prezzo dei libri nel carrello.
7. Implementa il metodo `calcolaTotale` per calcolare il totale del prezzo dei libri nel carrello applicando uno sconto in percentuale.
8. Crea una classe `TestNegozioLibri` con un metodo `main` che crea un'istanza di `NegozioLibri` e testa i metodi `aggiungiLibro` e `calcolaTotale` con diversi set di parametri.