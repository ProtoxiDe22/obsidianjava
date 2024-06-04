---
{"dg-publish":true,"permalink":"/java/01-introduction/"}
---


## Introduzione al linguaggio Java
Java è un linguaggio di programmazione sviluppato da Sun Microsystems (ora parte di Oracle) negli anni '90. È stato progettato per essere **portabile**, sicuro e robusto, utilizzato ampiamente nello sviluppo di applicazioni web, mobili e enterprise.

---

## Paradigmi di programmazione
Un paradigma di programmazione è un approccio o uno stile di programmazione che guida il modo in cui i programmi vengono strutturati e scritti. Esistono diversi paradigmi di programmazione, ognuno con i propri principi e pratiche.

---
### Paradigma Procedurale
Il paradigma procedurale è uno dei più antichi e si basa sulla concettualizzazione dei programmi come una sequenza di istruzioni o procedure. Le caratteristiche principali includono:
- **Funzioni:** Blocchi di codice riutilizzabili che eseguono un compito specifico.
- **Chiamate di funzione:** Possibilità di chiamare e riutilizzare funzioni definite.
- **Struttura sequenziale:** Esecuzione del codice in un ordine predefinito.

---
### Paradigma Orientato agli Oggetti (OOP)
L'OOP si basa sul concetto di oggetti e classi per organizzare e strutturare il codice. Ogni oggetto rappresenta un'entità del mondo reale e le classi sono le blueprint degli oggetti. Le caratteristiche principali includono:
- **Incapsulamento:** Nasconde i dettagli interni di un oggetto e protegge lo stato interno dell'oggetto dall'accesso esterno non autorizzato.
- **Ereditarietà:** Permette alle nuove classi di derivare dalle classi esistenti, ereditando le loro proprietà e metodi.
- **Polimorfismo:** Permette agli oggetti di essere trattati come istanze della loro classe di base.
- **Astrazione:** Fornisce un'interfaccia semplice per complessi sistemi sottostanti, nascondendo i dettagli implementativi.

---
### Paradigma Funzionale
Il paradigma funzionale si basa su funzioni matematiche e evita lo stato e i cambiamenti di stato. Le caratteristiche principali includono:
- **Funzioni pure:** Funzioni che non hanno effetti collaterali e restituiscono sempre lo stesso output per gli stessi input.
- **Immutabilità:** Le variabili non possono essere modificate dopo essere state assegnate.
- **Composizione di funzioni:** Combinare semplici funzioni per costruire funzioni più complesse.

### Paradigma Logico
Il paradigma logico si basa sulla logica formale e sulla dichiarazione di fatti e regole. Il programma consiste in una serie di enunciati logici e il motore di inferenza esegue le query su questi enunciati. Esempio principale è Prolog.

---
## Linguaggi Interpretati e linguaggi Compilati
I linguaggi di programmazione possono essere interpretati o compilati:
- **Linguaggi Interpretati:** Il codice sorgente viene tradotto e eseguito riga per riga da un interprete.
- **Linguaggi Compilati:** Il codice sorgente viene tradotto in un file eseguibile dal compilatore prima dell'esecuzione.

## Interpretazione Vs Compilazione
- **Interpretazione:** Traduzione e esecuzione del codice sorgente riga per riga.
- **Compilazione:** Traduzione del codice sorgente in un file eseguibile una sola volta, che può poi essere eseguito ripetutamente.

## Compilazione, Interprete e Compilatore
- **Compilatore:** Traduttore che converte il codice sorgente in bytecode o codice macchina.
- **Interprete:** Esegue il codice sorgente direttamente, riga per riga.
- **Compilazione:** Processo di conversione del codice sorgente in bytecode o codice macchina.
---

### JRE (Java Runtime Environment)

 Il JRE è un insieme di strumenti software che consente di eseguire applicazioni Java.
- **Componenti principali:** Include la JVM, le librerie di classi e i file di configurazione.
- **Utilizzo:** Necessario per eseguire programmi Java.
- **Installazione:** Disponibile per vari sistemi operativi.
---
### JDK (Java Development Kit)

 Il JDK è un ambiente di sviluppo per Java, includendo il JRE e strumenti di sviluppo come il compilatore.
- **Componenti principali:** Compilatore (`javac`), debugger, JRE, e altri strumenti.
- **Utilizzo:** Essenziale per lo sviluppo di nuove applicazioni Java.
- **Versioni:** Disponibile in versioni standard (SE) e enterprise (EE)
---
### Build Automation: Maven

Maven è uno strumento di automazione del build e gestione delle dipendenze per progetti Java.
- **Componenti principali:** POM, repository, e plugins.
- **Utilizzo:** Automatizza il processo di build e gestione delle dipendenze.

---

## Struttura di un programma Java
Un programma Java è composto da una o più classi. Ogni classe può contenere variabili di istanza (campi), metodi (funzioni) e costruttori (per creare oggetti). La struttura base di un programma Java è:

1. **Dichiarazione del package (opzionale):** Organizza le classi in namespace.
2. **Import delle classi di libreria (opzionale):** Permette l'uso di classi di altri package.
3. **Definizione della classe:** La classe contiene variabili, metodi e costruttori.
4. **Metodo main:** Punto di ingresso del programma.

Esempio di un semplice programma Java:
```java
package esempio;

import java.util.Scanner;

public class HelloWorld {
    private String messaggio;
    
    public HelloWorld(String messaggio) {
        this.messaggio = messaggio;
    }
    
    public void stampaMessaggio() {
        System.out.println(messaggio);
    }
    
    public static void main(String[] args) {
        HelloWorld hw = new HelloWorld("Hello, World!");
        hw.stampaMessaggio();
    }
}
```

---
## Utilizzo delle classi di libreria
Le classi di libreria forniscono funzionalità predefinite che possono essere utilizzate nei programmi Java. Esempi includono `java.util.ArrayList`, `java.io.File`, e `java.net.URL`. L'uso delle librerie permette di risparmiare tempo e sforzo, evitando di riscrivere codice comune.

Esempio di utilizzo di una classe di libreria:
```java
import java.util.ArrayList;

public class EsempioArrayList {
    public static void main(String[] args) {
        ArrayList<String> lista = new ArrayList<>();
        lista.add("Java");
        lista.add("Python");
        lista.add("C++");
        
        for (String linguaggio : lista) {
            System.out.println(linguaggio);
        }
    }
}
```

## Import e concetto di Package
I package in Java organizzano le classi in namespace distinti per evitare conflitti di nome e migliorare la modularità del codice. Un package è simile a una cartella in un file system. Il comando `import` permette di utilizzare le classi di altri package senza dover specificare il percorso completo del package ogni volta.

Esempio di dichiarazione di un package e importazione di classi:
```java
// Dichiarazione del package
package com.esempio;

// Importazione di classi di altri package
import java.util.ArrayList;
import java.util.HashMap;

public class EsempioPackage {
    public static void main(String[] args) {
        ArrayList<String> lista = new ArrayList<>();
        HashMap<String, Integer> mappa = new HashMap<>();
        
        lista.add("Java");
        mappa.put("Java", 1);
        
        System.out.println(lista);
        System.out.println(mappa);
    }
}
```
Utilizzare i package e gli import consente di organizzare meglio il codice, promuovendo la riusabilità e la manutenzione efficace del software.

---
##   IDE (Integrated Development Environment)

### Cosa sono gli IDE

Un Integrated Development Environment (IDE) è un software che fornisce strumenti completi per lo sviluppo di applicazioni. Gli IDE sono progettati per semplificare il processo di scrittura, debugging e testing del codice sorgente, offrendo una gamma di funzionalità che migliorano la produttività degli sviluppatori.

### Perché è necessario usare un IDE

Utilizzare un IDE offre diversi vantaggi, tra cui:

- **Efficienza:** Gli IDE integrano strumenti e funzionalità che accelerano il processo di sviluppo.
- **Debugging:** Offrono potenti strumenti di debugging che aiutano a identificare e correggere errori nel codice.
- **Autocompletamento del codice:** Suggeriscono e completano automaticamente il codice, riducendo errori di sintassi e aumentando la velocità di scrittura.
- **Gestione dei progetti:** Forniscono strumenti per organizzare e gestire progetti complessi con facilità.
- **Integrazione con VCS:** Si integrano con i sistemi di controllo di versione (VCS) come Git, facilitando la gestione delle versioni del codice.
- **Plugin e estensioni:** Supportano plugin che estendono le funzionalità dell'IDE, adattandolo alle esigenze specifiche degli sviluppatori.

### Funzionalità principali di un IDE

Le funzionalità principali di un IDE includono:

- **Editor di codice:** Un editor avanzato con funzioni di autocompletamento, evidenziazione della sintassi e refactoring.
- **Debugging:** Strumenti per eseguire il codice passo-passo, impostare breakpoints e visualizzare variabili.
- **Compilazione e build:** Strumenti integrati per compilare il codice e gestire il processo di build.
- **Integrazione con VCS:** Supporto per sistemi di controllo versione come Git.
- **Gestione delle dipendenze:** Strumenti per gestire librerie e dipendenze del progetto.
- **Interfaccia grafica:** Un'interfaccia utente che facilita la navigazione tra i file del progetto, le configurazioni e gli strumenti.
