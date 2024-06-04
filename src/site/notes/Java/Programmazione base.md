---
{"dg-publish":true,"permalink":"/java/programmazione-base/"}
---

## Le Basi di Java

### Struttura di un Programma Java
Un programma Java è composto da classi e metodi. Ogni applicazione Java deve avere un metodo `main` come punto di ingresso.

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### Spiegazione del Codice
- **public class HelloWorld**: Definisce una classe pubblica chiamata `HelloWorld`.
- **public static void main(String[] args)**: Metodo principale che viene eseguito quando si avvia il programma.
- **System.out.println("Hello, World!")**: Stampa il testo "Hello, World!" sulla console.

---

## Operazioni Matematiche in Java

---

### Introduzione

In Java, le operazioni matematiche possono essere eseguite utilizzando vari operatori aritmetici. Questi operatori consentono di effettuare calcoli di base come addizione, sottrazione, moltiplicazione, divisione e calcolo del resto. In questa sezione, esploreremo ciascuno di questi operatori con esempi pratici.

---

### Operatori Aritmetici

#### Addizione (`+`)

L'operatore di addizione somma due valori.

```java
System.out.println(5 + 3); // Output: 8
```

#### Sottrazione (`-`)

L'operatore di sottrazione sottrae il secondo valore dal primo.

```java
System.out.println(9 - 4); // Output: 5
```

#### Moltiplicazione (`*`)

L'operatore di moltiplicazione moltiplica due valori.

```java
System.out.println(7 * 3); // Output: 21
```

#### Divisione (`/`)

L'operatore di divisione divide il primo valore per il secondo. È importante notare che quando si dividono due numeri interi, il risultato sarà anch'esso un numero intero (la parte decimale viene troncata).

```java
System.out.println(10 / 2); // Output: 5
System.out.println(9 / 2); // Output: 4 (la parte decimale viene troncata)
```

Per ottenere un risultato decimale, è necessario utilizzare almeno un numero a virgola mobile (tipo `double` o `float`).

```java
System.out.println(9.0 / 2); // Output: 4.5
System.out.println(9 / 2.0); // Output: 4.5
```

#### Modulo (`%`)

L'operatore di modulo restituisce il resto della divisione tra due valori.

```java
System.out.println(10 % 3); // Output: 1 (10 diviso per 3 dà un resto di 1)
```

---

### Operazioni Matematiche Complesse

Per operazioni matematiche più complesse, Java fornisce la classe `Math` nella libreria standard. Alcuni metodi utili includono:

- `Math.pow(base, esponente)`: restituisce il risultato della base elevata all'esponente.
- `Math.sqrt(numero)`: restituisce la radice quadrata del numero.
- `Math.abs(valore)`: restituisce il valore assoluto.

Esempi:

```java
System.out.println(Math.pow(2, 3)); // Output: 8 (2 elevato alla potenza di 3)
System.out.println(Math.sqrt(16)); // Output: 4 (radice quadrata di 16)
System.out.println(Math.abs(-10)); // Output: 10 (valore assoluto di -10)
```

---

## Le Variabili in Java


### Introduzione alle Variabili

Le variabili sono elementi fondamentali nella programmazione, utilizzate per memorizzare dati che possono variare durante l'esecuzione di un programma. In Java, le variabili devono essere dichiarate prima di poter essere utilizzate. La dichiarazione di una variabile implica specificare il suo tipo e il suo nome.

---

### Dichiarazione e Inizializzazione delle Variabili

#### Dichiarazione di una Variabile

Per dichiarare una variabile in Java, si specifica il tipo della variabile seguito dal suo nome:

```java
int numero; // Dichiarazione di una variabile intera chiamata 'numero'
String nome; // Dichiarazione di una variabile stringa chiamata 'nome'
```

#### Inizializzazione di una Variabile

Una variabile deve essere inizializzata (assegnata a un valore) prima di poter essere utilizzata. La variabile può essere inizializzata al momento della dichiarazione:

```java
int numero = 10; // Dichiarazione e inizializzazione
String nome = "Alice"; // Dichiarazione e inizializzazione
```

Oppure può essere inizializzata successivamente:

```java
int numero;
numero = 10; // Inizializzazione successiva alla dichiarazione

String nome;
nome = "Alice"; // Inizializzazione successiva alla dichiarazione
```

---

### Tipi di Variabili in Java

In Java, esistono diversi tipi di variabili che si possono utilizzare a seconda del tipo di dati che si desidera memorizzare.

#### Tipi Primitivi

I tipi primitivi sono i tipi di dati più basilari in Java. I più comuni sono:

- `int`: interi (es. 1, 2, 3)

```java
int eta = 25; // Tipo intero
```

- `double`: numeri a virgola mobile a doppia precisione (es. 1.5, 2.75)

```java
double altezza = 1.75; // Tipo a virgola mobile
```

- `char`: singoli caratteri (es. 'a', 'B')

```java
char iniziale = 'A'; // Tipo carattere
```

- `boolean`: valori booleani (true, false)

```java
boolean isStudent = true; // Tipo booleano
```

#### Tipi di Riferimento

I tipi di riferimento fanno riferimento a oggetti e array. Il tipo più comune di riferimento è `String`, ma include anche array e classi definite dall'utente.

- `String`: una sequenza di caratteri

```java
String saluto = "Ciao"; // Tipo String
```

---

## Funzioni di Input e Output

### Input da Tastiera
Per leggere input da tastiera in Java, possiamo utilizzare la classe `Scanner`, che è una delle classi più comuni per questo scopo. La classe `Scanner` fornisce diversi metodi per leggere vari tipi di input, come stringhe, numeri interi, numeri decimali, e così via.

Ecco un esempio di base:

```java
import java.util.Scanner;

public class InputOutputExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Inserisci il tuo nome: ");
        String nome = scanner.nextLine();
        System.out.println("Ciao, " + nome + "!");
    }
}
```


---
### Utilizzo Avanzato di Scanner
La classe `Scanner` offre una varietà di metodi per leggere diversi tipi di dati:

- **nextLine()**: Legge una linea completa di input come stringa.
- **next()**: Legge il prossimo token di input come stringa.
- **nextInt()**: Legge il prossimo token di input come intero.
- **nextDouble()**: Legge il prossimo token di input come numero a virgola mobile (double).
- **nextBoolean()**: Legge il prossimo token di input come valore booleano (true o false).

### Esempio di Utilizzo di Vari Metodi di Scanner
Vediamo un esempio che dimostra l'uso di vari metodi della classe `Scanner`:

```java
import java.util.Scanner;

public class AdvancedInputExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Lettura di una stringa
        System.out.print("Inserisci una stringa: ");
        String stringa = scanner.nextLine();
        System.out.println("Hai inserito la stringa: " + stringa);
        
        // Lettura di un intero
        System.out.print("Inserisci un numero intero: ");
        int numeroIntero = scanner.nextInt();
        System.out.println("Hai inserito il numero intero: " + numeroIntero);
        
        // Lettura di un numero a virgola mobile
        System.out.print("Inserisci un numero a virgola mobile: ");
        double numeroDouble = scanner.nextDouble();
        System.out.println("Hai inserito il numero a virgola mobile: " + numeroDouble);
        
        // Lettura di un valore booleano
        System.out.print("Inserisci un valore booleano (true/false): ");
        boolean valoreBooleano = scanner.nextBoolean();
        System.out.println("Hai inserito il valore booleano: " + valoreBooleano);
    }
}
```

---
### Output su Console
Per stampare output su console, utilizziamo `System.out.print` o `System.out.println`. La differenza tra i due metodi è che `System.out.print` stampa il testo senza andare a capo, mentre `System.out.println` aggiunge una nuova linea dopo aver stampato il testo.

```java
System.out.print("Questo è un output senza nuova linea.");
System.out.println(" Questo è un output con nuova linea.");
```

### Spiegazione del Codice
- **Scanner scanner = new Scanner(System.in)**: Crea un oggetto `Scanner` per leggere input da tastiera.
- **String nome = scanner.nextLine()**: Legge una linea di input dall'utente.
- **int numeroIntero = scanner.nextInt()**: Legge un numero intero dall'utente.
- **double numeroDouble = scanner.nextDouble()**: Legge un numero a virgola mobile dall'utente.
- **boolean valoreBooleano = scanner.nextBoolean()**: Legge un valore booleano dall'utente.
- **System.out.print** e **System.out.println**: Stampa testo sulla console, con e senza nuova linea.

In questo modo, possiamo leggere diversi tipi di input e gestire correttamente gli errori che possono verificarsi durante la lettura dei dati. La classe `Scanner` rende il processo di acquisizione degli input da tastiera semplice e flessibile, consentendo di gestire vari scenari di input in modo efficace.

---


## Le Stringhe

Le stringhe in Java sono oggetti immutabili che rappresentano sequenze di caratteri. Questo significa che una volta creata, una stringa non può essere modificata. Tuttavia, è possibile creare nuove stringhe basate su operazioni sulle stringhe esistenti.

### Dichiarazione e Inizializzazione delle Stringhe

Per dichiarare e inizializzare una stringa in Java, si utilizza il tipo `String` seguito dal nome della variabile.

```java
String saluto = "Ciao, Mondo!";
System.out.println(saluto);
```

---

### Concatenazione delle Stringhe

La concatenazione delle stringhe è il processo di unire due o più stringhe per formare una nuova stringa. In Java, è possibile concatenare stringhe utilizzando l'operatore `+` o il metodo `concat()`.

#### Utilizzo dell'Operatore `+`

L'operatore `+` può essere utilizzato per concatenare stringhe in modo semplice e diretto.

```java
String parte1 = "Ciao, ";
String parte2 = "Mondo!";
String saluto = parte1 + parte2;
System.out.println(saluto); // Stampa: "Ciao, Mondo!"
```
---

### Metodi Utili delle Stringhe

Java fornisce molti metodi utili per la manipolazione delle stringhe. Ecco alcuni dei più comuni:

- **length()**: Restituisce la lunghezza della stringa.
- **charAt(int index)**: Restituisce il carattere all'indice specificato.
- **substring(int beginIndex, int endIndex)**: Restituisce una sottostringa compresa tra `beginIndex` e `endIndex`.
- **toLowerCase()**: Converte tutti i caratteri della stringa in minuscolo.
- **toUpperCase()**: Converte tutti i caratteri della stringa in maiuscolo.
- **trim()**: Rimuove gli spazi bianchi iniziali e finali dalla stringa.
- **replace(char oldChar, char newChar)**: Sostituisce tutte le occorrenze di `oldChar` con `newChar`.
- **contains(string testo)**: Restituisce true se la stringa contiene al suo interno almeno un occorrenza di `testo`

Esempi:

```java
String esempio = " Programmazione Java ";

System.out.println("Lunghezza: " + esempio.length()); // Restituisce 20
System.out.println("Carattere all'indice 5: " + esempio.charAt(5)); // Restituisce 'a'
System.out.println("Sottostringa: " + esempio.substring(0, 11)); // Restituisce " Programma"
System.out.println("Minuscolo: " + esempio.toLowerCase()); // Restituisce " programmazione java "
System.out.println("Maiuscolo: " + esempio.toUpperCase()); // Restituisce " PROGRAMMAZIONE JAVA "
System.out.println("Senza spazi: " + esempio.trim()); // Restituisce "Programmazione Java"
System.out.println("Sostituzione: " + esempio.replace('a', 'o')); // Restituisce " Progrommozjone Jovo "
System.out.println("Contiene 'a'?:" + esempio.contains('a')); //restituisce true
System.out.println("Contiene 'k'?:" + esempio.contains('k')); //restituisce false

```

---

### Esempi di Utilizzo

#### Esempio 1: Concatenazione di Stringhe

```java
public class ConcatenazioneStringhe {
    public static void main(String[] args) {
        String parte1 = "Buongiorno, ";
        String parte2 = "come stai?";
        String messaggio = parte1 + parte2;
        System.out.println(messaggio); // Stampa: "Buongiorno, come stai?"
    }
}
```

#### Esempio 2: Manipolazione di Stringhe

```java
public class ManipolazioneStringhe {
    public static void main(String[] args) {
        String frase = " Programmazione Java ";

        System.out.println("Lunghezza: " + frase.length()); // Stampa: 20
        System.out.println("Carattere all'indice 5: " + frase.charAt(5)); // Stampa: 'a'
        System.out.println("Sottostringa: " + frase.substring(0, 12)); // Stampa: " Programmaz"
        System.out.println("Minuscolo: " + frase.toLowerCase()); // Stampa: " programmazione java "
        System.out.println("Maiuscolo: " + frase.toUpperCase()); // Stampa: " PROGRAMMAZIONE JAVA "
        System.out.println("Senza spazi: " + frase.trim()); // Stampa: "Programmazione Java"
        System.out.println("Sostituzione: " + frase.replace('a', 'o')); // Stampa: " Progrommozjone Jovo "
    }
}
```


### Spiegazione del Codice

- **esempio.length()**: Restituisce la lunghezza della stringa, inclusi gli spazi.
- **esempio.charAt(5)**: Restituisce il carattere all'indice 5 della stringa.
- **esempio.substring(0, 11)**: Restituisce una sottostringa che va dal carattere all'indice 0 al carattere all'indice 10.
- **esempio.toLowerCase()**: Converte tutti i caratteri della stringa in minuscolo.
- **esempio.toUpperCase()**: Converte tutti i caratteri della stringa in maiuscolo.
- **esempio.trim()**: Rimuove gli spazi bianchi iniziali e finali dalla stringa.
- **esempio.replace('a', 'o')**: Sostituisce tutte le occorrenze del carattere 'a' con il carattere 'o'.

---


## Le Istruzioni Condizionali in Java

### Introduzione alle Istruzioni Condizionali

Le istruzioni condizionali permettono al programma di prendere decisioni in base a condizioni specifiche. In Java, le principali istruzioni condizionali sono `if`, `else if`, `else` e `switch`. Queste istruzioni controllano il flusso di esecuzione del programma in base al risultato di espressioni booleane.

---

### Operatori di Confronto

Prima di approfondire le istruzioni condizionali, è importante conoscere gli operatori di confronto utilizzati per creare espressioni booleane:

- `==`: uguale a
- `!=`: diverso da
- `<`: minore di
- `<=`: minore o uguale a
- `>`: maggiore di
- `>=`: maggiore o uguale a

Esempio:

```java
boolean uguale  = (5 == 10) // false
boolean uguale2 = (10 == 10) // true 

boolean diverso  = (5 != 10) // true
boolean diverso2 = (10 != 10) // false 

boolean minore = (5 < 10); // true
boolean maggiore = (5 > 10); // false
```

Gli operatori `>=`  e `<=` funzionano come gli operatori `>` e `<`, ma al contrario di questi ultimi, il loro valore booleano è vero anche se i due valori confrontati sono uguali

```java

boolean minore  = (9 < 10) //true
boolean minore2 = (10 < 10) // false

boolean minuguale  = (9 <= 10) // true
boolean minuguale2 = (10 <= 10) // true
```

---
### Comparazione delle Stringhe

Quando si tratta di confrontare stringhe in Java, non possiamo usare gli operatori di confronto (`==`, `!=`, ecc.) per verificare l'uguaglianza o la disuguaglianza dei valori. Questo perché questi operatori confrontano i riferimenti delle stringhe, non i loro contenuti. Per confrontare i valori delle stringhe, dobbiamo usare metodi specifici.

#### Metodo `equals`

Il metodo `equals` è utilizzato per verificare se due stringhe hanno lo stesso contenuto.

Esempio:

```java
String str1 = "ciao";
String str2 = "ciao";
String str3 = "Ciao";

boolean uguali = str1.equals(str2); // true
boolean diversi = str1.equals(str3); // false
```

#### Metodo `equalsIgnoreCase`

Il metodo `equalsIgnoreCase` confronta le stringhe ignorando le differenze tra maiuscole e minuscole.

Esempio:

```java
String str1 = "ciao";
String str2 = "Ciao";

boolean ugualiIgnoraCase = str1.equalsIgnoreCase(str2); // true
```

#### Metodo `compareTo`

Il metodo `compareTo` confronta due stringhe lessicograficamente. Restituisce un valore negativo se la stringa chiamante precede l'argomento, zero se le stringhe sono uguali, e un valore positivo se la stringa chiamante segue l'argomento.

Esempio:

```java
String str1 = "apple";
String str2 = "banana";
String str3 = "apple";

int confronto1 = str1.compareTo(str2); // negativo
int confronto2 = str1.compareTo(str3); // 0
int confronto3 = str2.compareTo(str1); // positivo
```

---

### Istruzione `if`

L'istruzione `if` esegue un blocco di codice solo se una condizione specificata è vera.

```java
int numero = 10;

if (numero > 0) {
    System.out.println("Il numero è positivo");
}
```

In questo esempio, il messaggio "Il numero è positivo" verrà stampato solo se `numero` è maggiore di 0.

---

### Istruzione `if-else`

L'istruzione `if-else` permette di eseguire un blocco di codice se la condizione è vera e un altro blocco di codice se la condizione è falsa.

```java
int numero = -5;

if (numero > 0) {
    System.out.println("Il numero è positivo");
} else {
    System.out.println("Il numero è negativo o zero");
}
```

---

### Istruzione `else if`

L'istruzione `else if` permette di testare più condizioni. Viene utilizzata in combinazione con `if` e `else` per creare una catena di condizioni.

```java
int numero = 0;

if (numero > 0) {
    System.out.println("Il numero è positivo");
} else if (numero < 0) {
    System.out.println("Il numero è negativo");
} else {
    System.out.println("Il numero è zero");
}
```

---

### Istruzione `switch`

L'istruzione `switch` seleziona una tra molteplici sezioni di codice da eseguire, in base al valore di una variabile. È particolarmente utile quando si ha a che fare con un gran numero di condizioni.

```java
int giorno = 3;

switch (giorno) {
    case 1:
        System.out.println("Lunedì");
        break;
    case 2:
        System.out.println("Martedì");
        break;
    case 3:
        System.out.println("Mercoledì");
        break;
    case 4:
        System.out.println("Giovedì");
        break;
    case 5:
        System.out.println("Venerdì");
        break;
    case 6:
        System.out.println("Sabato");
        break;
    case 7:
        System.out.println("Domenica");
        break;
    default:
        System.out.println("Giorno non valido");
        break;
}
```

---

### Esempi di Utilizzo

#### Esempio 1: Controllare se un numero è pari o dispari

```java
int numero = 8;

if (numero % 2 == 0) {
    System.out.println("Il numero è pari");
} else {
    System.out.println("Il numero è dispari");
}
```

#### Esempio 2: Utilizzare `switch` per determinare il mese

```java
int mese = 7;

switch (mese) {
    case 1:
        System.out.println("Gennaio");
        break;
    case 2:
        System.out.println("Febbraio");
        break;
    case 3:
        System.out.println("Marzo");
        break;
    case 4:
        System.out.println("Aprile");
        break;
    case 5:
        System.out.println("Maggio");
        break;
    case 6:
        System.out.println("Giugno");
        break;
    case 7:
        System.out.println("Luglio");
        break;
    case 8:
        System.out.println("Agosto");
        break;
    case 9:
        System.out.println("Settembre");
        break;
    case 10:
        System.out.println("Ottobre");
        break;
    case 11:
        System.out.println("Novembre");
        break;
    case 12:
        System.out.println("Dicembre");
        break;
    default:
        System.out.println("Mese non valido");
        break;
}
```

---


## Scope delle Variabili in Java

### Introduzione allo Scope delle Variabili

Lo "scope" di una variabile in Java si riferisce alla parte del codice in cui una variabile è accessibile. Comprendere lo scope delle variabili è fondamentale per evitare errori e garantire che le variabili siano utilizzate correttamente. In Java, le variabili possono essere dichiarate in diversi contesti, ognuno dei quali determina il loro scope.

### Tipi di Scope delle Variabili

In Java, le variabili possono avere tre principali tipi di scope:

1. **Scope di Classe (Variabili di Classe)**
2. **Scope di Metodo (Variabili Locali)**
3. **Scope di Blocco (Variabili di Blocco)**

---

### Scope di Classe

Le variabili di classe, anche chiamate variabili di istanza o campi, sono dichiarate all'interno di una classe ma al di fuori di qualsiasi metodo, costruttore o blocco. Queste variabili sono accessibili da tutti i metodi della classe.

```java
public class EsempioScope {
    // Variabile di classe
    int variabileClasse = 10;

    public void metodoUno() {
        System.out.println("Metodo Uno: " + variabileClasse);
    }

    public void metodoDue() {
        System.out.println("Metodo Due: " + variabileClasse);
    }
}
```

In questo esempio, `variabileClasse` è accessibile sia da `metodoUno` che da `metodoDue`.

---

### Scope di Metodo

Le variabili locali sono dichiarate all'interno di un metodo. Queste variabili sono accessibili solo all'interno del metodo in cui sono dichiarate e non possono essere utilizzate al di fuori di esso.

```java
public class EsempioScope {
    public void metodo() {
        // Variabile locale
        int variabileLocale = 20;
        System.out.println("Variabile Locale: " + variabileLocale);
    }

    public void altroMetodo() {
        // System.out.println("Variabile Locale: " + variabileLocale); // Errore di compilazione
    }
}
```

In questo esempio, `variabileLocale` è accessibile solo all'interno di `metodo` e non può essere utilizzata in `altroMetodo`.

---

### Scope di Blocco

Le variabili di blocco sono dichiarate all'interno di blocchi di codice delimitati da parentesi graffe `{}` come nei cicli `for`, `while` o nei blocchi condizionali `if`. Queste variabili sono accessibili solo all'interno del blocco in cui sono dichiarate.

```java
public class EsempioScope {
    public void metodo() {
        for (int i = 0; i < 5; i++) {
            // Variabile di blocco
            int variabileBlocco = i * 2;
            System.out.println("Variabile di Blocco: " + variabileBlocco);
        }
        // System.out.println("Variabile di Blocco: " + variabileBlocco); // Errore di compilazione
    }
}
```

In questo esempio, `variabileBlocco` è accessibile solo all'interno del ciclo `for` e non può essere utilizzata al di fuori di esso.

---

### Esempio Completo

Vediamo un esempio completo che illustra tutti e tre i tipi di scope delle variabili:

```java
public class EsempioCompletoScope {
    // Variabile di classe
    int variabileClasse = 100;

    public void metodoEsempio() {
        // Variabile locale
        int variabileLocale = 200;

        if (variabileClasse > 50) {
            // Variabile di blocco
            int variabileBlocco = 300;
            System.out.println("Variabile di Blocco: " + variabileBlocco);
        }

        System.out.println("Variabile Locale: " + variabileLocale);
        System.out.println("Variabile di Classe: " + variabileClasse);
        // System.out.println("Variabile di Blocco: " + variabileBlocco); // Errore di compilazione
    }

    public static void main(String[] args) {
        EsempioCompletoScope esempio = new EsempioCompletoScope();
        esempio.metodoEsempio();
    }
}
```

In questo esempio:
- `variabileClasse` è una variabile di classe accessibile ovunque all'interno della classe `EsempioCompletoScope`.
- `variabileLocale` è una variabile locale accessibile solo all'interno di `metodoEsempio`.
- `variabileBlocco` è una variabile di blocco accessibile solo all'interno del blocco `if`.

---

### Considerazioni Finali

Capire lo scope delle variabili è cruciale per scrivere codice chiaro e senza errori. Ecco alcune buone pratiche:
- **Dichiarare le variabili nel contesto più ristretto possibile:** Questo riduce il rischio di errori e rende il codice più leggibile.
- **Evitare di usare lo stesso nome per variabili in scope diversi:** Questo può creare confusione e portare a errori difficili da individuare.
- **Utilizzare commenti per chiarire lo scope delle variabili:** Specialmente in metodi complessi o lunghi.
---
## Logica Booleana in Java

### Introduzione alla Logica Booleana

La logica booleana è la base dell'informatica moderna e si occupa di variabili che possono assumere solo due valori: `true` (vero) e `false` (falso). Questa logica è utilizzata per prendere decisioni nei programmi e per controllare il flusso di esecuzione. In Java, le espressioni booleane sono fondamentali per le istruzioni condizionali.

---

### Operatori Logici

Java fornisce diversi operatori logici per costruire espressioni booleane complesse:

- `&&` (AND logico): restituisce `true` se entrambe le espressioni sono vere.
- `||` (OR logico): restituisce `true` se almeno una delle espressioni è vera.
- `!` (NOT logico): inverte il valore di una espressione booleana.

#### AND Logico (`&&`)

L'operatore AND logico (`&&`) restituisce `true` solo se entrambe le condizioni sono vere.

| A     | B     | A && B |
|-------|-------|--------|
| true  | true  | true   |
| true  | false | false  |
| false | true  | false  |
| false | false | false  |

Esempio in Java:

```java
System.out.println(true && true); // Output: true
System.out.println(true && false); // Output: false
```

#### OR Logico (`||`)

L'operatore OR logico (`||`) restituisce `true` se almeno una delle condizioni è vera.

| A     | B     | A \|\| B |
|-------|-------|--------|
| true  | true  | true   |
| true  | false | true   |
| false | true  | true   |
| false | false | false  |

Esempio in Java:

```java
System.out.println(true || false); // Output: true
System.out.println(false || false); // Output: false
```

#### NOT Logico (`!`)

L'operatore NOT logico (`!`) inverte il valore di una espressione booleana.

| A     | !A    |
|-------|-------|
| true  | false |
| false | true  |

Esempio in Java:

```java
System.out.println(!true); // Output: false
System.out.println(!false); // Output: true
```

---

### Utilizzo della Logica Booleana in Java

Le espressioni booleane sono utilizzate principalmente nelle istruzioni condizionali per controllare il flusso del programma.

#### Istruzioni Condizionali

Esempio di utilizzo degli operatori logici in una istruzione `if`:

```java
int a = 10;
int b = 20;

if (a < b && b < 30) {
    System.out.println("Entrambe le condizioni sono vere");
}

if (a > 5 || b < 15) {
    System.out.println("Almeno una delle condizioni è vera");
}

if (!(a == b)) {
    System.out.println("a e b sono diversi");
}
```

---

### Combinare Molteplici Operatori Logici

In Java, è possibile combinare più operatori logici per costruire espressioni booleane complesse. L'ordine delle operazioni è importante e può essere controllato usando le parentesi.

Esempio:

```java
int a = 5;
int b = 10;
int c = 15;

// Controlla se a è minore di b e b è minore di c, oppure se c è uguale a 15
if ((a < b && b < c) || c == 15) {
    System.out.println("La condizione è vera");
}
```

Ordine delle operazioni:
1. Le espressioni nelle parentesi vengono valutate per prime.
2. Gli operatori `&&` vengono valutati successivamente.
3. Gli operatori `||` vengono valutati per ultimi.

Altro esempio:

```java
int x = 3;
int y = 4;
int z = 5;

// Utilizzo di operatori multipli
if ((x < y || y > z) && !(z == 5)) {
    System.out.println("Condizione complessa vera");
} else {
    System.out.println("Condizione complessa falsa");
}
```

In questo esempio:
1. `x < y` è `true` e `y > z` è `false`. L'operatore `||` combina queste due espressioni come `true || false`, che è `true`.
2. La condizione `!(z == 5)` viene valutata come `!(true)`, che è `false`.
3. La condizione complessiva è `true && false`, che è `false`.

---

### Tabelle di Verità

Le tabelle di verità sono strumenti utili per comprendere il comportamento degli operatori logici. Vediamo le tabelle di verità per gli operatori AND, OR e NOT.

#### Tabella di Verità per AND (`&&`)

| A     | B     | A && B |
|-------|-------|--------|
| true  | true  | true   |
| true  | false | false  |
| false | true  | false  |
| false | false | false  |

#### Tabella di Verità per OR (`||`)

| A     | B     | A \|\| B |
|-------|-------|--------|
| true  | true  | true   |
| true  | false | true   |
| false | true  | true   |
| false | false | false  |

#### Tabella di Verità per NOT (`!`)

| A     | !A    |
|-------|-------|
| true  | false |
| false | true  |

---

### Esempi Pratici

Esempio 1: Controllare se un numero è compreso tra due valori

```java
int numero = 15;

if (numero > 10 && numero < 20) {
    System.out.println("Il numero è compreso tra 10 e 20");
}
```

Esempio 2: Verificare se un numero è fuori da un intervallo

```java
int numero = 25;

if (numero < 10 || numero > 20) {
    System.out.println("Il numero è fuori dall'intervallo 10-20");
}
```

Esempio 3: Invertire una condizione

```java
boolean condizione = false;

if (!condizione) {
    System.out.println("La condizione è falsa");
}
```
---
## Cicli ed Iterazioni

### Ciclo for
Il ciclo `for` è utilizzato per iterare una serie di istruzioni un numero specifico di volte.

```java
for (int i = 0; i < 5; i++) {
    System.out.println("Valore di i: " + i);
}
```

### Ciclo while
Il ciclo `while` esegue un blocco di codice finché una condizione specificata è vera.

```java
int i = 0;
while (i < 5) {
    System.out.println("Valore di i: " + i);
    i++;
}
```

### Spiegazione del Codice
- **for (int i = 0; i < 5; i)**: Inizializza `i` a 0, esegue il ciclo finché `i` è minore di 5, incrementa `i` di 1 ad ogni iterazione.
- **while (i < 5)**: Esegue il ciclo finché `i` è minore di 5.

---

## Statement Break & Continue

### break
Il `break` esce dal ciclo corrente.

```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break;
    }
    System.out.println("Valore di i: " + i);
}
```

### continue
Il `continue` salta l'iterazione corrente del ciclo e passa alla successiva.

```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        continue;
    }
    System.out.println("Valore di i: " + i);
}
```

### Spiegazione del Codice
- **if (i == 5) break**: Esce dal ciclo quando `i` è 5.
- **if (i == 5) continue**: Salta l'iterazione quando `i` è 5.

---

## Conversione dei Tipi di Dati

### Conversione Implicita
La conversione implicita avviene automaticamente quando si assegna un valore di un tipo di dati inferiore a un tipo di dati superiore.

```java
int numeroIntero = 100;
double numeroDouble = numeroIntero; // Conversione implicita da int a double
System.out.println("Numero Double: " + numeroDouble);
```

### Conversione Esplicita
La conversione esplicita deve essere specificata dall'utente utilizzando il casting.

```java
double numeroDouble = 9.78;
int numeroIntero = (int) numeroDouble; // Conversione esplicita da double a int
System.out.println("Numero Intero: " + numeroIntero);
```

### Metodi di Conversione delle Stringhe
Utilizziamo metodi come `Integer.parseInt()` e `Double.parseDouble()` per convertire stringhe in numeri.

```java
String numeroStringa = "123";
int numeroIntero = Integer.parseInt(numeroStringa);
double numeroDouble = Double.parseDouble(numeroStringa);
System.out.println("Numero Intero: " + numeroIntero);
System.out.println("Numero Double: " + numeroDouble);
```

### Spiegazione del Codice
- **(int) numeroDouble**: Converte esplicitamente un `double` in `int`.
- **Integer.parseInt(numeroStringa)**: Converte una stringa in un intero.
- **Double.parseDouble(numeroStringa)**: Converte una stringa in un double.

---

## Formattazione di Stringhe

### Introduzione alla Formattazione delle Stringhe
La formattazione delle stringhe in Java consente di costruire stringhe dinamiche con valori variabili. Questo è particolarmente utile quando si desidera creare messaggi personalizzati o visualizzare dati in un formato specifico.

### Utilizzo di `String.format()`
Il metodo `String.format()` consente di creare stringhe formattate utilizzando specificatori di formato.

```java
int età = 25;
String nome = "Mario";
String messaggio = String.format("Ciao, mi chiamo %s e ho %d anni.", nome, età);
System.out.println(messaggio);
```

I selettori `%s` e `%d` indicano il punto della stringa e il formato in cui andranno inserite le variabili di seguito
### Utilizzo di `System.out.printf()`
Il metodo `System.out.printf()` è simile a `String.format()`, ma stampa direttamente sulla console.

```java
int età = 25;
String nome = "Mario";
System.out.printf("Ciao, mi chiamo %s e ho %d anni.%n", nome, età);
```

---
### Selettore `%n` nella funzione `printf()`
Il selettore `%n` è utilizzato per inserire una nuova linea nel testo formattato. È preferibile utilizzare `%n` rispetto al classico `\n` poiché `%n` garantisce la corretta nuova linea in modo indipendente dalla piattaforma. Questo è particolarmente importante quando il codice potrebbe essere eseguito su sistemi operativi diversi (Windows, macOS, Linux), che potrebbero interpretare `\n` in modo differente.

```java
System.out.printf("Questa è la prima linea.%nQuesta è la seconda linea.%n");
```

---

### Selettori di Formato
Ecco una lista dei selettori di formato più comuni utilizzati in `String.format()` e `System.out.printf()`:

- **%s**: Stringa
- **%d**: Intero decimale
- **%f**: Numero in virgola mobile
- **%.2f**: Numero in virgola mobile con due cifre decimali
- **%c**: Carattere
- **%b**: Booleano
- **%n**: Nuova linea
- **%t**: Data e ora (richiede specificatori aggiuntivi)

### Esempi di Utilizzo dei Selettori di Formato

#### Formattazione di Stringhe
```java
String nome = "Alice";
System.out.printf("Nome: %s%n", nome);
```

#### Formattazione di Interi
```java
int età = 30;
System.out.printf("Età: %d anni%n", età);
```

#### Formattazione di Numeri a Virgola Mobile
```java
double prezzo = 19.99;
System.out.printf("Prezzo: %.2f EUR%n", prezzo);
```

#### Formattazione di Caratteri
```java
char iniziale = 'A';
System.out.printf("Iniziale: %c%n", iniziale);
```

#### Formattazione di Booleani
```java
boolean isStudente = true;
System.out.printf("È studente: %b%n", isStudente);
```

#### Formattazione di Date e Ore
```java
import java.util.Date;

Date data = new Date();
System.out.printf("Data e Ora: %tF %<tT%n", data);
```
In questo esempio:
- **%tF**: Formatta la data come "YYYY-MM-DD".
- **%<tT**: Formatta l'ora come "HH:MM:SS".

### Spiegazione del Codice
- **%s**: Inserisce una stringa.
- **%d**: Inserisce un intero.
- **%.2f**: Inserisce un numero in virgola mobile con due cifre decimali.
- **%c**: Inserisce un carattere.
- **%b**: Inserisce un valore booleano.
- **%tF**: Inserisce una data in formato "YYYY-MM-DD".
- **%<tT**: Inserisce un'ora in formato "HH:MM:SS".

### Utilizzo Avanzato dei Selettori di Formato
È possibile combinare e utilizzare specificatori di formato avanzati per ottenere risultati più complessi. Ecco alcuni esempi:

#### Allineamento e Larghezza Fissa
```java
String nome = "Alice";
int età = 30;
System.out.printf("Nome: %-10s Età: %5d%n", nome, età);
```
In questo esempio:
- **%-10s**: Allinea la stringa a sinistra e occupa almeno 10 caratteri.
- **%5d**: Allinea l'intero a destra e occupa almeno 5 caratteri.

---
### Selettore `%n`
Il selettore `%n` è utilizzato per inserire una nuova linea nel testo formattato. È preferibile utilizzare `%n` rispetto al classico `\n` poiché `%n` garantisce la corretta nuova linea in modo indipendente dalla piattaforma. Questo è particolarmente importante quando il codice potrebbe essere eseguito su sistemi operativi diversi (Windows, macOS, Linux), che potrebbero interpretare `\n` in modo differente.

```java
System.out.printf("Questa è la prima linea.%nQuesta è la seconda linea.%n");
```

---
## Gli Array in Java

### Introduzione agli Array

Gli array sono strutture dati che permettono di memorizzare una collezione di elementi dello stesso tipo. Gli array in Java hanno una lunghezza fissa, determinata al momento della loro creazione, e possono memorizzare sia tipi primitivi che oggetti.

---

### Dichiarazione degli Array

Per dichiarare un array in Java, è necessario specificare il tipo degli elementi che conterrà e utilizzare le parentesi quadre `[]`. Ci sono diversi modi per dichiarare un array:

```java
int[] numeri;  // Dichiarazione di un array di interi
String[] nomi; // Dichiarazione di un array di stringhe
```

È anche possibile dichiarare un array mettendo le parentesi quadre dopo il nome della variabile, anche se questa sintassi è meno comune:

```java
int numeri[];  // Alternativa per dichiarare un array di interi
String nomi[]; // Alternativa per dichiarare un array di stringhe
```

---

### Inizializzazione degli Array

#### Inizializzazione al Momento della Dichiarazione

Un array può essere inizializzato al momento della dichiarazione specificando la sua lunghezza:

```java
int[] numeri = new int[5];  // Array di 5 interi, inizializzati a 0
String[] nomi = new String[3]; // Array di 3 stringhe, inizializzate a null
```

#### Inizializzazione con Valori Predefiniti

È possibile inizializzare un array con valori predefiniti usando una lista di valori tra parentesi graffe `{}`:

```java
int[] valori = {1, 2, 3, 4, 5}; // Array di interi inizializzati con 1, 2, 3, 4, 5
String[] colori = {"Rosso", "Verde", "Blu"}; // Array di stringhe inizializzati con "Rosso", "Verde", "Blu"
```

#### Inizializzazione Dinamica di un Array

In Java, la lunghezza di un array è fissa dopo la sua creazione, ma è possibile creare un array con una lunghezza determinata dinamicamente al momento dell'esecuzione del programma. Ad esempio, è possibile chiedere all'utente di specificare la lunghezza dell'array:

```java
import java.util.Scanner;

public class ArrayDinamico {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Inserisci la lunghezza dell'array: ");
        int lunghezza = scanner.nextInt();
        
        int[] numeri = new int[lunghezza];
        System.out.println("Array di lunghezza " + lunghezza + " creato.");
    }
}
```

In questo esempio, la lunghezza dell'array `numeri` è determinata dall'input dell'utente.

---

### Accesso e Modifica degli Elementi di un Array

Gli elementi di un array sono indicizzati a partire da 0. È possibile accedere a un elemento specifico utilizzando l'indice corrispondente e modificarne il valore:

```java
int[] numeri = {10, 20, 30, 40, 50};

// Accesso agli elementi dell'array
System.out.println("Il primo elemento è: " + numeri[0]); // Stampa: 10
System.out.println("Il terzo elemento è: " + numeri[2]); // Stampa: 30

// Modifica degli elementi dell'array
numeri[1] = 25; // Modifica il secondo elemento
System.out.println("Il nuovo secondo elemento è: " + numeri[1]); // Stampa: 25
```

---

### La Proprietà `length`

La proprietà `length` degli array in Java restituisce la lunghezza (il numero di elementi) dell'array. Questa proprietà è utile per iterare su tutti gli elementi dell'array senza causare errori di indice fuori dai limiti.

```java
int[] numeri = {10, 20, 30, 40, 50};
System.out.println("La lunghezza dell'array è: " + numeri.length); // Stampa: 5
```

---

### Iterazione su un Array

#### Utilizzo di un Ciclo `for`

È possibile iterare su tutti gli elementi di un array utilizzando un ciclo `for` tradizionale:

```java
int[] numeri = {10, 20, 30, 40, 50};
for (int i = 0; i < numeri.length; i++) {
    System.out.println("Elemento all'indice " + i + ": " + numeri[i]);
}
```

#### Utilizzo di un Ciclo `for-each`

Il ciclo `for-each` è una sintassi più semplice per iterare su tutti gli elementi di un array:

```java
int[] numeri = {10, 20, 30, 40, 50};
for (int numero : numeri) {
    System.out.println("Elemento: " + numero);
}
```

---

### Array Multidimensionali

Gli array multidimensionali sono array di array. Il tipo più comune è l'array bidimensionale, che può essere pensato come una matrice.

#### Dichiarazione e Inizializzazione di un Array Bidimensionale

```java
// Dichiarazione di un array bidimensionale
int[][] matrice = new int[3][3];

// Inizializzazione con valori predefiniti
int[][] tabella = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

#### Accesso agli Elementi di un Array Bidimensionale

```java
int[][] matrice = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
System.out.println("Elemento alla posizione (0,0): " + matrice[0][0]); // Stampa: 1
System.out.println("Elemento alla posizione (2,1): " + matrice[2][1]); // Stampa: 8
```

#### Iterazione su un Array Bidimensionale

```java
int[][] matrice = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
for (int i = 0; i < matrice.length; i++) {
    for (int j = 0; j < matrice[i].length; j++) {
        System.out.println("Elemento alla posizione (" + i + "," + j + "): " + matrice[i][j]);
    }
}
```

---

### Metodi Utili per gli Array

#### Metodi della Classe `Arrays`

La classe `java.util.Arrays` fornisce diversi metodi utili per lavorare con gli array.

- **`Arrays.toString(array)`**: Restituisce una rappresentazione stringa dell'array.

```java
import java.util.Arrays;

int[] numeri = {10, 20, 30, 40, 50};
System.out.println(Arrays.toString(numeri)); // Stampa: [10, 20, 30, 40, 50]
```

- **`Arrays.sort(array)`**: Ordina gli elementi dell'array in ordine crescente.

```java
import java.util.Arrays;

int[] numeri = {30, 10, 50, 20, 40};
Arrays.sort(numeri);
System.out.println(Arrays.toString(numeri)); // Stampa: [10, 20, 30, 40, 50]
```

- **`Arrays.binarySearch(array, key)`**: Cerca un elemento nell'array ordinato e restituisce l'indice dell'elemento, o un valore negativo se l'elemento non è presente.

```java
import java.util.Arrays;

int[] numeri = {10, 20, 30, 40, 50};
int indice = Arrays.binarySearch(numeri, 30);
System.out.println("L'elemento 30 si trova all'indice: " + indice); // Stampa: 2
```
---
## Funzioni in Java

### Introduzione alle Funzioni

Le funzioni (o metodi) sono blocchi di codice riutilizzabili che eseguono una specifica operazione. Le funzioni aiutano a rendere il codice più organizzato, leggibile e mantenibile. In Java, le funzioni sono definite all'interno delle classi.

---

### Definizione di una Funzione

Una funzione in Java è definita con la seguente sintassi:

```java
modificatore_di_accesso tipo_di_ritorno nome_della_funzione(parametri) {
    // Corpo della funzione
}
```

- **Modificatore di accesso**: Specifica la visibilità della funzione (`public`, `private`, `protected`).
- **Tipo di ritorno**: Il tipo di dato che la funzione restituisce (`int`, `double`, `void`, ecc.).
- **Nome della funzione**: Un identificatore che rappresenta il nome della funzione.
- **Parametri**: Una lista di parametri (opzionale) che la funzione prende in ingresso.

#### Esempio di una Funzione Senza Parametri e Senza Valore di Ritorno

```java
public static void saluta() {
    System.out.println("Ciao, Mondo!");
}
```

Questa funzione `saluta` stampa semplicemente "Ciao, Mondo!" sulla console. Non prende parametri e non restituisce alcun valore (`void`).

#### Esempio di una Funzione con Parametri e Senza Valore di Ritorno

```java
public static void salutaConNome(String nome) {
    System.out.println("Ciao, " + nome + "!");
}
```

Questa funzione `salutaConNome` prende un parametro di tipo `String` chiamato `nome` e stampa un messaggio di saluto personalizzato.

#### Esempio di una Funzione con Parametri e con Valore di Ritorno

```java
public static int somma(int a, int b) {
    return a + b;
}
```

Questa funzione `somma` prende due parametri di tipo `int` e restituisce la loro somma.

---

### Utilizzo delle Funzioni

Per utilizzare una funzione, basta chiamarla dal metodo `main` o da altre funzioni all'interno della stessa classe.

#### Esempio di Chiamata di una Funzione Senza Parametri e Senza Valore di Ritorno

```java
public class EsempioFunzioni {
    public static void main(String[] args) {
        saluta();
    }

    public static void saluta() {
        System.out.println("Ciao, Mondo!");
    }
}
```

#### Esempio di Chiamata di una Funzione con Parametri e Senza Valore di Ritorno

```java
public class EsempioFunzioni {
    public static void main(String[] args) {
        salutaConNome("Alice");
    }

    public static void salutaConNome(String nome) {
        System.out.println("Ciao, " + nome + "!");
    }
}
```

#### Esempio di Chiamata di una Funzione con Parametri e con Valore di Ritorno

```java
public class EsempioFunzioni {
    public static void main(String[] args) {
        int risultato = somma(5, 3);
        System.out.println("La somma è: " + risultato);
    }

    public static int somma(int a, int b) {
        return a + b;
    }
}
```

---

### Funzioni con Più Parametri

Le funzioni possono prendere qualsiasi numero di parametri. Ecco un esempio di una funzione che calcola la media di tre numeri:

```java
public class EsempioFunzioni {
    public static void main(String[] args) {
        double media = calcolaMedia(10, 20, 30);
        System.out.println("La media è: " + media);
    }

    public static double calcolaMedia(int a, int b, int c) {
        return (a + b + c) / 3.0;
    }
}
```

---

### Funzioni con Nessun Parametro e con Valore di Ritorno

A volte, una funzione potrebbe non richiedere parametri ma restituire un valore. Ecco un esempio:

```java
public class EsempioFunzioni {
    public static void main(String[] args) {
        int numero = ottieniNumero();
        System.out.println("Il numero è: " + numero);
    }

    public static int ottieniNumero() {
        return 42;
    }
}
```

---

### Esempi Pratici

#### Esempio 1: Funzione che Controlla se un Numero è Pari

```java
public class EsempioFunzioni {
    public static void main(String[] args) {
        boolean risultato = isPari(4);
        System.out.println("Il numero è pari: " + risultato);
    }

    public static boolean isPari(int numero) {
        return numero % 2 == 0;
    }
}
```

#### Esempio 2: Funzione che Calcola il Fattoriale di un Numero

```java
public class EsempioFunzioni {
    public static void main(String[] args) {
        int risultato = fattoriale(5);
        System.out.println("Il fattoriale è: " + risultato);
    }

    public static int fattoriale(int n) {
        int risultato = 1;
        for (int i = 1; i <= n; i++) {
            risultato *= i;
        }
        return risultato;
    }
}
```

---

## Le Eccezioni

### Gestione delle Eccezioni
Le eccezioni sono eventi anomali che possono verificarsi durante l'esecuzione di un programma. Possono essere gestite utilizzando blocchi `try-catch`.

```java
try {
    int divisione = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Errore: Divisione per zero.");
}
```

### Spiegazione del Codice
- **try**: Blocco di codice che può generare un'eccezione.
- **catch (ArithmeticException e)**: Gestisce l'eccezione specifica `ArithmeticException`.

---

## Sollevare le Eccezioni

### throw
Il `throw` viene utilizzato per sollevare un'eccezione.

```java
public class TestThrow {
    public static void main(String[] args) {
        try {
            verificaEtà(15);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }

    static void verificaEtà(int età) throws Exception {
        if (età < 18) {
            throw new Exception("Età non valida per la registrazione.");
        }
    }
}
```

### Spiegazione del Codice
- **throw new Exception("Età non valida per la registrazione.")**: Solleva un'eccezione con il messaggio specificato.
- **catch (Exception e)**: Cattura e gestisce l'eccezione sollevata.

---

## Differenza tra Eccezioni Checked ed Unchecked

### Eccezioni Checked
Le eccezioni `checked` sono verificate a tempo di compilazione. Devono essere gestite esplicitamente.

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class TestCheckedException {
    public static void main(String[] args) {
        try {
            File file = new File("test.txt");
            Scanner scanner = new Scanner(file);
        } catch (FileNotFoundException e) {
            System.out.println("File non trovato.");
        }
    }
}
```

### Eccezioni Unchecked
Le eccezioni `unchecked` sono verificate a runtime. Non è obbligatorio gestirle.

```java
public class TestUncheckedException {
    public static void main(String[] args) {
        int[] array = {1, 2, 3};
        System.out.println(array[5]); // Questo causerà una ArrayIndexOutOfBoundsException
    }
}
```

### Spiegazione del Codice
- **FileNotFoundException**: Esempio di eccezione `checked`.
- **ArrayIndexOutOfBoundsException**: Esempio di eccezione `unchecked`.
