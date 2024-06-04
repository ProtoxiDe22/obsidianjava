---
{"dg-publish":true,"permalink":"/java/04-programmazione-a-oggetti/"}
---

# Corso di Base di Java

Benvenuti al corso di base di Java! Questo corso è rivolto ai principianti assoluti e vi guiderà attraverso i concetti fondamentali della programmazione orientata agli oggetti (OOP) utilizzando Java.

---

## I meccanismi della programmazione ad oggetti

### Concetti filosofici ed operativi della OOP

La programmazione orientata agli oggetti (OOP) è un paradigma di programmazione che utilizza "oggetti" per rappresentare dati e metodi. Gli oggetti sono istanze di classi, che possono essere considerate come un modello o una descrizione di un tipo di oggetto.

- **Filosofia**: L'OOP si basa sul concetto di modellare il mondo reale in termini di oggetti. Ogni oggetto ha uno stato (rappresentato da proprietà o attributi) e un comportamento (rappresentato da metodi).
- **Operatività**: In OOP, programmi complessi vengono suddivisi in oggetti più piccoli e gestibili che interagiscono tra loro. Questo rende il codice più organizzato, riutilizzabile e facile da mantenere.

Esempio di oggetto nel mondo reale: Un "Automobile" può essere un oggetto con proprietà come "colore", "modello" e "velocità", e comportamenti come "accelerare" e "frenare".

---

### Le Classi

Le classi sono il fondamento dell'OOP. Una classe è una struttura che definisce lo stato e il comportamento degli oggetti.

```java
// Definizione di una classe Automobile
public class Automobile {
    // Proprietà (variabili di istanza)
    String colore;
    String modello;
    int velocità;

    // Metodo (comportamento)
    void accelera() {
        velocità += 10;
    }
    
    void frena() {
        velocità -= 10;
    }
}
```

---

### I Metodi

I metodi sono funzioni definite all'interno di una classe che descrivono i comportamenti degli oggetti. Possono manipolare le proprietà della classe e/o eseguire azioni.

```java
// Esempio di metodi in una classe Automobile
public class Automobile {
    // Proprietà
    String colore;
    String modello;
    int velocità;

    // Metodi
    void accelera() {
        velocità += 10;
    }
    
    void frena() {
        velocità -= 10;
    }

    // Metodo principale per eseguire il programma
    public static void main(String[] args) {
        // Creazione di un'istanza di Automobile
        Automobile miaAuto = new Automobile();
        miaAuto.colore = "Rosso";
        miaAuto.modello = "Ferrari";
        miaAuto.velocità = 0;

        // Utilizzo dei metodi
        miaAuto.accelera();
        System.out.println("Velocità: " + miaAuto.velocità); // Output: Velocità: 10
    }
}
```

---

### Le proprietà

Le proprietà, o variabili di istanza, rappresentano lo stato di un oggetto. Ogni oggetto avrà valori propri per queste variabili.

```java
public class Automobile {
    // Proprietà
    String colore;
    String modello;
    int velocità;
}
```

---

### Metodi Getter e Setter

I metodi getter e setter sono utilizzati per accedere e modificare le proprietà private di una classe. Questo approccio segue il principio dell'incapsulamento.

```java
public class Automobile {
    // Proprietà private
    private String colore;
    private String modello;
    private int velocità;

    // Getter per la proprietà 'colore'
    public String getColore() {
        return colore;
    }

    // Setter per la proprietà 'colore'
    public void setColore(String colore) {
        this.colore = colore;
    }
}
```

---

### Ereditarietà

L'ereditarietà è un meccanismo che permette a una classe di ereditare proprietà e metodi da un'altra classe. La classe che eredita è chiamata sottoclasse, mentre la classe da cui eredita è chiamata superclasse.

```java
// Classe Superclasse
public class Veicolo {
    String tipo;
    int velocità;

    void accelera() {
        velocità += 10;
    }
}

// Classe Sottoclasse
public class Automobile extends Veicolo {
    String modello;

    public static void main(String[] args) {
        Automobile miaAuto = new Automobile();
        miaAuto.tipo = "Auto";
        miaAuto.modello = "Ferrari";
        miaAuto.velocità = 0;
        miaAuto.accelera();
        System.out.println("Velocità: " + miaAuto.velocità); // Output: Velocità: 10
    }
}
```

---

### Incapsulamento

L'incapsulamento è il principio di nascondere i dettagli interni di un oggetto e fornire un'interfaccia pubblica per l'interazione. Questo si ottiene dichiarando le variabili di istanza come private e fornendo metodi pubblici (getter e setter) per accedervi.

```java
public class Automobile {
    // Proprietà private
    private String colore;
    private String modello;
    private int velocità;

    // Getter e Setter
    public String getColore() {
        return colore;
    }

    public void setColore(String colore) {
        this.colore = colore;
    }

    public int getVelocità() {
        return velocità;
    }

    public void setVelocità(int velocità) {
        this.velocità = velocità;
    }
}
```

---
### Modificatori di visibilità delle classi

I modificatori di visibilità controllano l'accesso alle classi, ai metodi e alle variabili in Java. I principali modificatori di visibilità sono:

- **public**: Il membro è accessibile da qualsiasi altra classe.
- **private**: Il membro è accessibile solo all'interno della stessa classe.
- **protected**: Il membro è accessibile all'interno dello stesso pacchetto e dalle sottoclassi.
- **default** (nessun modificatore): Il membro è accessibile solo all'interno dello stesso pacchetto.

Esempio:

La classe `EsempioVisibilita` viene definita nel package `org.example`
```java
package org.example;  
public class EsempioVisibilita {  
    public int pubblico;  
    private int privato;  
    protected int protetto;  
    int predefinito; // default  
  
    public static void main(String[] args) {  
        EsempioVisibilita esempio = new EsempioVisibilita();  
        esempio.pubblico = 1;    // Accessibile  
        esempio.privato = 2;     // Accessibile  
        esempio.protetto = 3;    // Accessibile  
        esempio.predefinito = 4; // Accessibile  
    }  
}
```
All'interno della stessa classe, tutte le proprietà, anche quelle private, sono sempre accessibili

La classe `StessoPackage` viene definita anch'essa nel package `org.example`

```java
package org.example
class StessoPackage{  
  
    public static void main(String[] args) {  
        EsempioVisibilita esempioEsterno = new EsempioVisibilita();  
        esempioEsterno.pubblico = 1; // Accessibile  
        esempioEsterno.privato = 2; // Non Accessibile  
        esempioEsterno.protetto = 3; // Accessibile  
        esempioEsterno.predefinito = 4; // Accessibile  
  
    }  
}
```
In questo caso le variabili private diventano inaccessibili, tutte le altre sono accessibili


La classe `AltroPackage`  viene definita in un package differente

```java
package org.example.sottopacchetto;  
import org.example.EsempioVisibilita;  
  
public class AltroPackage {  
    public static void main(String[] args) {  
        System.out.println("Hello world!");  
        EsempioVisibilita esempioFuoriDalPacchetto = new EsempioVisibilita();  
        esempioFuoriDalPacchetto.pubblico = 1; // Accessibile  
        esempioFuoriDalPacchetto.privato = 2; // Non Accessibile  
        esempioFuoriDalPacchetto.protetto = 3; // Non Accessibile  
        esempioFuoriDalPacchetto.predefinito = 4; // Non Accessibile  
    }  
}
```
In questa situazione bisogna innanzitutto importare la classe `EsempioVisibilita` per poterla usare, e inoltre tutte le variabili non pubbliche vengono rese inaccessibili

---

### Polimorfismo

Il polimorfismo è la capacità di un oggetto di prendere molte forme. In Java, il polimorfismo si ottiene tramite l'overloading (sovraccarico) dei metodi e l'override (sovrascrittura) dei metodi.

- **Overloading**: Consente a più metodi di avere lo stesso nome ma parametri diversi.
- **Override**: Consente a una sottoclasse di fornire una specifica implementazione di un metodo già definito nella superclasse.

```java
// Overloading dei metodi
public class Formattatore {

    private String formattaNumero(int value) {
        return String.format("%d", value);
    }

    private String formattaNumero(double value) {
        return String.format("%.3f", value);
    }

    private String formattaNumero(String value) {
        return String.format("%.2f", Double.parseDouble(value));
    }

    public static void main(String[] args) {
        Formattatore f = new Formattatore();
        System.out.println(f.formattaNumero(500)); //output: 500
        System.out.println(f.formattaNumero(89.9934)); //output: 89.993
        System.out.println(f.formattaNumero("550")); //output: 550.00
    }
}

// Override dei metodi
public class Veicolo {
    void avvia() {
        System.out.println("Il veicolo si avvia");
    }
}

public class Automobile extends Veicolo {
    @Override
    void avvia() {
        System.out.println("L'automobile si avvia");
    }

    public static void main(String[] args) {
        Veicolo mioVeicolo = new Automobile();
        mioVeicolo.avvia(); // Output: L'automobile si avvia
    }
}
```

---


### Costruttori

I costruttori sono metodi speciali utilizzati per inizializzare gli oggetti. Un costruttore ha lo stesso nome della classe e non ha un tipo di ritorno. I costruttori possono essere sovraccaricati.

```java
public class Automobile {
    // Proprietà
    String colore;
    String modello;
    int velocità;

    // Costruttore senza parametri
    public Automobile() {
        this.colore = "Bianco";
        this.modello = "Standard";
        this.velocità = 0;
    }

    // Costruttore con parametri
    public Automobile(String colore, String modello, int velocità) {
        this.colore = colore;
        this.modello = modello;
        this.velocità = velocità;
    }

    public static void main(String[] args) {
        // Creazione di un oggetto utilizzando il costruttore senza parametri
        Automobile auto1 = new Automobile();
        System.out.println("Auto1 Modello: " + auto1.modello); // Output: Auto1 Modello: Standard

        // Creazione di un oggetto utilizzando il costruttore con parametri
        Automobile auto2 = new Automobile("Rosso", "Ferrari", 0);


        System.out.println("Auto2 Modello: " + auto2.modello); // Output: Auto2 Modello: Ferrari
    }
}
```

---
## Classi Astratte e Interfacce

### Classi Astratte

#### Cos'è una Classe Astratta?

Una classe astratta è una classe che non può essere istanziata direttamente. Può contenere sia metodi astratti (metodi dichiarati ma non implementati) sia metodi concreti (metodi con implementazione). Serve come base per altre classi che estenderanno questa classe astratta e forniranno implementazioni concrete per i metodi astratti.

#### Come si Usa?

Una classe astratta viene dichiarata usando la parola chiave `abstract`. Le classi che ereditano da una classe astratta devono implementare tutti i suoi metodi astratti. Tuttavia, le classi astratte possono avere campi e metodi concreti che possono essere utilizzati dalle sottoclassi.

```java
// Dichiarazione di una classe astratta
public abstract class Animale {
    private String nome;

    public Animale(String nome) {
        this.nome = nome;
    }

    // Metodo astratto
    public abstract void verso();

    // Metodo concreto
    public void dormi() {
        System.out.println(nome + " sta dormendo.");
    }

    // Getter e Setter
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }
}
```

---
#### Quando Vanno Usate?

Le classi astratte vanno usate quando si vuole creare una classe base che non dovrebbe essere istanziata direttamente, ma che condivide un comportamento comune tra le sottoclassi. Sono utili quando si vuole definire un comportamento comune e obbligare le sottoclassi a fornire una specifica implementazione di alcuni metodi.

#### Esempio di utilizzo della Classe Astratta

```java
// Classe Cane che estende la classe astratta Animale
public class Cane extends Animale {
    public Cane(String nome) {
        super(nome);
    }

    @Override
    public void verso() {
        System.out.println(getNome() + " abbaia.");
    }
}

// Classe Gatto che estende la classe astratta Animale
public class Gatto extends Animale {
    public Gatto(String nome) {
        super(nome);
    }

    @Override
    public void verso() {
        System.out.println(getNome() + " miagola.");
    }
}

// Classe di Test
public class TestAnimale {
    public static void main(String[] args) {
        Animale cane = new Cane("Fido");
        Animale gatto = new Gatto("Whiskers");

        cane.verso();  // Output: Fido abbaia.
        gatto.verso(); // Output: Whiskers miagola.

        cane.dormi();  // Output: Fido sta dormendo.
        gatto.dormi(); // Output: Whiskers sta dormendo.
    }
}
```

---

### Interfacce

#### Cos'è un'Interfaccia?

Un'interfaccia è un contratto che una classe può implementare. Contiene dichiarazioni di metodi ma non fornisce alcuna implementazione. Le interfacce possono essere utilizzate per definire un comportamento che può essere implementato da diverse classi non correlate. A partire da Java 8, le interfacce possono includere metodi predefiniti e metodi statici con implementazione.

#### Come si Usa?

Un'interfaccia viene dichiarata usando la parola chiave `interface`. Le classi implementano un'interfaccia utilizzando la parola chiave `implements`. Una classe può implementare più interfacce.

```java
// Dichiarazione di un'interfaccia
public interface Volante {
    void vola();
}

// Implementazione di un'interfaccia
public class Uccello implements Volante {
    @Override
    public void vola() {
        System.out.println("L'uccello vola.");
    }
}

// Classe di Test
public class TestVolante {
    public static void main(String[] args) {
        Volante uccello = new Uccello();
        uccello.vola();  // Output: L'uccello vola.
    }
}
```

#### Quando Vanno Usate?

Le interfacce vanno usate quando si vuole definire un set di metodi che possono essere implementati da diverse classi, permettendo la flessibilità di diverse implementazioni. Sono utili per definire comportamenti comuni tra classi non correlate.

#### Esempio di Interfaccia

```java
// Interfaccia Volante
public interface Volante {
    void vola();
}

// Interfaccia Nuotante
public interface Nuotante {
    void nuota();
}

// Classe Anatra che implementa Volante e Nuotante
public class Anatra implements Volante, Nuotante {
    @Override
    public void vola() {
        System.out.println("L'anatra vola.");
    }

    @Override
    public void nuota() {
        System.out.println("L'anatra nuota.");
    }
}

// Classe di Test
public class TestAnatra {
    public static void main(String[] args) {
        Anatra anatra = new Anatra();
        anatra.vola();  // Output: L'anatra vola.
        anatra.nuota(); // Output: L'anatra nuota.
    }
}
```

---

### Differenze tra Classi Astratte e Interfacce

| Caratteristica           | Classe Astratta                  | Interfaccia                              |
|--------------------------|----------------------------------|------------------------------------------|
| Istanziabile             | No                               | No                                       |
| Metodi                   | Può avere sia metodi astratti che concreti | Solo metodi astratti (fino a Java 7), può avere metodi di default e statici (da Java 8) |
| Ereditarietà             | Può estendere una sola classe    | Può estendere multiple interfacce        |
| Parola Chiave            | `abstract`                       | `interface`                              |
| Quando Usarla            | Quando si vuole una classe base con metodi comuni e alcune parti lasciate per l'implementazione | Quando si vuole definire un contratto che varie classi possono implementare |


### Quando Usare Classi Astratte o Interfacce

- **Usa Classi Astratte** quando hai una situazione in cui vuoi condividere del codice comune tra più classi strettamente correlate.
- **Usa Interfacce** quando vuoi specificare che un gruppo di classi non correlate deve implementare un determinato comportamento.

---

### Esempio Combinato: Classe Astratta e Interfacce

```java
// Interfaccia Volante
public interface Volante {
    void vola();
}

// Classe Astratta Animale
public abstract class Animale {
    private String nome;

    public Animale(String nome) {
        this.nome = nome;
    }

    public abstract void verso();

    public void dormi() {
        System.out.println(nome + " sta dormendo.");
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }
}

// Classe Anatra che estende Animale e implementa Volante
public class Anatra extends Animale implements Volante {
    public Anatra(String nome) {
        super(nome);
    }

    @Override
    public void verso() {
        System.out.println(getNome() + " fa qua qua.");
    }

    @Override
    public void vola() {
        System.out.println(getNome() + " vola.");
    }
}

// Classe di Test
public class TestAnatra {
    public static void main(String[] args) {
        Anatra anatra = new Anatra("Daisy");

        anatra.verso();  // Output: Daisy fa qua qua.
        anatra.vola();   // Output: Daisy vola.
        anatra.dormi();  // Output: Daisy sta dormendo.
    }
}
```

Questi capitoli completano la presentazione sui concetti avanzati di classi astratte e interfacce, spiegandone l'uso e fornendo esempi pratici per una comprensione approfondita.