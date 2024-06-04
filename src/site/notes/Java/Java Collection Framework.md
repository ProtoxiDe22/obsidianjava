---
{"dg-publish":true,"permalink":"/java/java-collection-framework/"}
---


## Enhanced For Loop

### Introduzione

Il ciclo `for` migliorato, noto anche come enhanced for loop o for-each loop, è una funzionalità introdotta in Java 5 che semplifica l'iterazione su array e collezioni. Fornisce un modo più leggibile e conciso per iterare su ogni elemento di un array o di una collezione senza dover gestire esplicitamente l'indice o l'iteratore.

### Sintassi e Significato

La sintassi del ciclo for migliorato è la seguente:

```java
for (TipoElemento elemento : collezione) {
    // Corpo del ciclo
}
```

- `TipoElemento`: Il tipo degli elementi nell'array o nella collezione.
- `elemento`: Una variabile che rappresenta l'elemento corrente nell'iterazione.
- `collezione`: L'array o la collezione da iterare.

### Come Viene Effettuata l'Iterazione

L'iterazione viene effettuata in modo sequenziale su ogni elemento dell'array o della collezione. Ad ogni iterazione, il valore dell'elemento corrente viene assegnato alla variabile `elemento`, che può essere utilizzata all'interno del corpo del ciclo.

### Confronto con l'Iterazione con Indice

#### Iterazione con Indice

```java
public class TraditionalForLoopExample {
    public static void main(String[] args) {
        String[] fruits = {"Apple", "Banana", "Cherry"};

        for (int i = 0; i < fruits.length; i++) {
            System.out.println(fruits[i]);
        }
    }
}
```

In questo esempio, utilizziamo un indice (`i`) per accedere a ciascun elemento dell'array `fruits`. Questo richiede la gestione esplicita dell'indice e la verifica dei limiti dell'array.

#### Enhanced For Loop

```java
public class EnhancedForLoopExample {
    public static void main(String[] args) {
        String[] fruits = {"Apple", "Banana", "Cherry"};

        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

In questo esempio, il ciclo for migliorato itera attraverso ogni elemento dell'array `fruits` e stampa il suo valore. Non è necessario gestire esplicitamente gli indici o controllare i limiti dell'array.

### Vantaggi dell'Enhanced For Loop

1. **Semplicità e Leggibilità**: Il ciclo for migliorato è più leggibile e conciso rispetto al ciclo for tradizionale. Non è necessario gestire esplicitamente gli indici o gli iteratori.
2. **Riduzione degli Errori**: Poiché non ci sono indici da gestire, si riducono le possibilità di errori comuni come `ArrayIndexOutOfBoundsException`.
3. **Mantenimento del Codice**: Il codice è più facile da mantenere e comprendere, specialmente per chi legge il codice successivamente.

### Esempi Pratici

#### Somma degli Elementi di un Array

```java
public class SumArrayExample {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        int sum = 0;

        for (int number : numbers) {
            sum += number;
        }

        System.out.println("Sum: " + sum);
    }
}
```

In questo esempio, il ciclo for migliorato è utilizzato per calcolare la somma degli elementi di un array di interi.

#### Iterazione con Oggetti

```java
public class ObjectArrayExample {
    public static void main(String[] args) {
        String[] fruits = {"Apple", "Banana", "Cherry"};

        for (String fruit : fruits) {
            System.out.println("I like " + fruit);
        }
    }
}
```

In questo esempio, il ciclo for migliorato itera attraverso ogni elemento dell'array `fruits` e stampa un messaggio personalizzato per ciascun frutto.

---
### Enhanced for e modifica dell'array

Il ciclo for migliorato è un potente strumento per iterare su array e collezioni in Java. Fornisce una sintassi più chiara e riduce la possibilità di errori comuni associati alla gestione degli indici. Tuttavia, è importante ricordare che il ciclo for migliorato è ideale per situazioni in cui non è necessario modificare direttamente gli elementi dell'array o della collezione durante l'iterazione. In caso contrario, è necessario utilizzare il ciclo for tradizionale.

### Esempi Pratici

#### Somma degli Elementi di un Array

```java
public class SumArrayExample {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        int sum = 0;

        for (int number : numbers) {
            sum += number;
        }

        System.out.println("Sum: " + sum);
    }
}
```

In questo esempio, il ciclo for migliorato è utilizzato per calcolare la somma degli elementi di un array di interi.

#### Modifica degli Elementi di un Array

```java
public class ModifyArrayExample {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        for (int i = 0; i < numbers.length; i++) {
            numbers[i] *= 2;
        }

        for (int number : numbers) {
            System.out.println(number);
        }
    }
}
```

In questo esempio, utilizziamo il ciclo for tradizionale per modificare gli elementi dell'array, in quanto il ciclo for migliorato non permette di modificare direttamente gli elementi dell'array durante l'iterazione.

---
## Introduzione al Java Collection Framework

Le collezioni in Java sono una parte fondamentale della programmazione, che ci permettono di gestire gruppi di oggetti in modo efficiente e flessibile. Differiscono dagli array semplici in quanto offrono metodi e funzionalità avanzate, come l'aggiunta dinamica di elementi, la ricerca e l'ordinamento, l'eliminazione di duplicati e molto altro.


![Collection framework hierarchy.png](/img/user/Java/assets/Collection%20framework%20hierarchy.png)
---

## Interfaccia Collection

L'interfaccia `Collection` è la radice della gerarchia delle collezioni Java. Essa definisce i metodi fondamentali che tutte le collezioni devono implementare.

### Metodi Principali di Collection

- `add(E e)`: Aggiunge l'elemento specificato a questa collezione.
- `remove(Object o)`: Rimuove una singola istanza dell'elemento specificato da questa collezione.
- `contains(Object o)`: Restituisce true se questa collezione contiene l'elemento specificato.
- `size()`: Restituisce il numero di elementi in questa collezione.
- `isEmpty()`: Restituisce true se questa collezione non contiene elementi.
- `iterator()`: Restituisce un iteratore su gli elementi in questa collezione.

---

## Interfaccia List

`List` è un'interfaccia che estende `Collection` e rappresenta una sequenza ordinata di elementi. Gli elementi possono essere accessibili tramite il loro indice (posizione).

### Metodi Principali di List (oltre a quelli ereditati da Collection)

- `get(int index)`: Restituisce l'elemento alla posizione specificata in questa lista.
- `set(int index, E element)`: Sostituisce l'elemento alla posizione specificata in questa lista con l'elemento specificato.
- `add(int index, E element)`: Inserisce l'elemento specificato alla posizione specificata in questa lista.
- `remove(int index)`: Rimuove l'elemento alla posizione specificata in questa lista.
- `indexOf(Object o)`: Restituisce l'indice della prima occorrenza dell'elemento specificato in questa lista, o -1 se questa lista non contiene l'elemento.

---
### ArrayList

`ArrayList` è un'implementazione di `List` basata su un array ridimensionabile. Fornisce un accesso rapido agli elementi grazie agli indici, ma le operazioni di inserimento e rimozione possono essere costose.

#### Esempio di Utilizzo

```java
import java.util.ArrayList;

public class ArrayListExample {
    public static void main(String[] args) {
        ArrayList<String> cities = new ArrayList<>();
        cities.add("New York");
        cities.add("Los Angeles");
        cities.add("Chicago");
        
        System.out.println(cities.get(1)); // Los Angeles
    }
}
```

#### Metodi Aggiuntivi di ArrayList

- `ensureCapacity(int minCapacity)`: Aumenta la capacità di questa istanza di `ArrayList`, se necessario, per garantire che possa contenere almeno il numero di elementi specificato.

---
### LinkedList

`LinkedList` è un'implementazione di `List` che utilizza una lista collegata (linked list). Offre un'ottima performance per operazioni di inserimento e rimozione.

#### Esempio di Utilizzo

```java
import java.util.LinkedList;

public class LinkedListExample {
    public static void main(String[] args) {
        LinkedList<String> students = new LinkedList<>();
        students.add("Alice");
        students.add("Bob");
        students.add("Charlie");
        
        students.addFirst("Zara"); // Aggiunge all'inizio della lista
        students.addLast("Eve");   // Aggiunge alla fine della lista
        
        System.out.println(students.get(0)); // Zara
    }
}
```

#### Metodi Aggiuntivi di LinkedList

- `addFirst(E e)`: Inserisce l'elemento specificato all'inizio di questa lista.
- `addLast(E e)`: Inserisce l'elemento specificato alla fine di questa lista.
- `removeFirst()`: Rimuove e restituisce il primo elemento di questa lista.
- `removeLast()`: Rimuove e restituisce l'ultimo elemento di questa lista.

---
### Vector

`Vector` è un'implementazione di `List` che utilizza un array ridimensionabile ed è sincronizzata, rendendola thread-safe.

#### Esempio di Utilizzo

```java
import java.util.Vector;

public class VectorExample {
    public static void main(String[] args) {
        Vector<String> tools = new Vector<>();
        tools.add("Hammer");
        tools.add("Screwdriver");
        tools.add("Wrench");
        
        System.out.println(tools.get(2)); // Wrench
    }
}
```

#### Metodi Aggiuntivi di Vector

- `capacity()`: Restituisce la capacità corrente di questo vettore.
- `ensureCapacity(int minCapacity)`: Aumenta la capacità di questo vettore, se necessario, per garantire che possa contenere almeno il numero di elementi specificato.
- `trimToSize()`: Regola la capacità di questo vettore alla dimensione corrente della lista di elementi.

---

## Interfaccia Set

`Set` è un'interfaccia che estende `Collection` e rappresenta una raccolta che non permette duplicati.

### Metodi Principali di Set (oltre a quelli ereditati da Collection)

- `add(E e)`: Aggiunge l'elemento specificato a questo set se non è già presente.
- `remove(Object o)`: Rimuove l'elemento specificato da questo set, se presente.
- `contains(Object o)`: Restituisce true se questo set contiene l'elemento specificato.

### HashSet

`HashSet` è un'implementazione di `Set` basata su una tabella hash. Non garantisce l'ordine degli elementi.

#### Esempio di Utilizzo

```java
import java.util.HashSet;

public class HashSetExample {
    public static void main(String[] args) {
        HashSet<String> emails = new HashSet<>();
        emails.add("john.doe@example.com");
        emails.add("jane.doe@example.com");
        emails.add("john.doe@example.com"); // Non verrà aggiunto

        for (String email : emails) {
            System.out.println(email);
        }
    }
}
```

#### Metodi Aggiuntivi di HashSet

Non ha metodi aggiuntivi specifici rispetto a quelli definiti nell'interfaccia `Set`.

---

## Interfaccia Queue

`Queue` è un'interfaccia che estende `Collection` e rappresenta una raccolta progettata per contenere elementi prima del loro processamento.

### Metodi Principali di Queue (oltre a quelli ereditati da Collection)

- `offer(E e)`: Inserisce l'elemento specificato in questa coda.
- `poll()`: Recupera e rimuove la testa di questa coda.
- `peek()`: Recupera, ma non rimuove, la testa di questa coda.

### LinkedList (come Queue)

`LinkedList` implementa anche l'interfaccia `Queue`, permettendo l'utilizzo dei metodi di `Queue` su una lista collegata.

#### Esempio di Utilizzo

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        Queue<String> printQueue = new LinkedList<>();
        printQueue.offer("Document1.pdf");
        printQueue.offer("Photo.png");
        printQueue.offer("Report.docx");

        System.out.println("Next in queue: " + printQueue.peek()); // Visualizza l'elemento in testa senza rimuoverlo
        System.out.println("Processing: " + printQueue.poll()); // Rimuove e visualizza l'elemento in testa
        
        for (String document : printQueue) {
            System.out.println(document);
        }
    }
}
```

---

## Interfaccia Map

`Map` è un'interfaccia che rappresenta una struttura di dati che mappa chiavi a valori. Non permette chiavi duplicate.

### Metodi Principali di Map

- `put(K key, V value)`: Associa il valore specificato con la chiave specificata in questa mappa.
- `remove(Object key)`: Rimuove il mapping per una chiave da questa mappa se è presente.
- `get(Object key)`: Restituisce il valore al quale è mappata la chiave specificata, o null se questa mappa non contiene un mapping per la chiave.
- `containsKey(Object key)`: Restituisce true se questa mappa contiene un mapping per la chiave specificata.
- `containsValue(Object value)`: Restituisce true se questa mappa associa uno o più valori alla chiave specificata.

### HashMap

`HashMap` è un'implementazione di `Map` basata su una tabella hash. Non garantisce l'ordine delle chiavi.

#### Esempio di Utilizzo

```java
import java.util.HashMap;

public class HashMapExample {
    public static void main(String[] args) {
        HashMap<String, String> countryCapitalMap = new HashMap<>();
        countryCapitalMap.put("USA", "Washington, D.C.");
        countryCapitalMap.put("France", "Paris");
        countryCapitalMap.put("Japan", "Tokyo");
        
        for (String country : country

CapitalMap.keySet()) {
            System.out.println(country + ": " + countryCapitalMap.get(country));
        }
    }
}
```

#### Metodi Aggiuntivi di HashMap

Non ha metodi aggiuntivi specifici rispetto a quelli definiti nell'interfaccia `Map`.

---

## java.util.Collections

La classe `Collections` contiene numerosi metodi statici che operano su collezioni, inclusi ordinamento, ricerca e modifica.

### Metodi Principali di Collections

- `sort(List<T> list)`: Ordina la lista specificata in ordine naturale.
- `binarySearch(List<? extends Comparable<? super T>> list, T key)`: Cerca l'elemento specificato nella lista ordinata utilizzando la ricerca binaria.
- `reverse(List<?> list)`: Inverte l'ordine degli elementi nella lista specificata.
- `shuffle(List<?> list)`: Permuta casualmente la lista specificata.

#### Esempio di Utilizzo

```java
import java.util.ArrayList;
import java.util.Collections;

public class CollectionsExample {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(3);
        numbers.add(1);
        numbers.add(2);
        
        Collections.sort(numbers); // Ordina la lista
        System.out.println("Sorted: " + numbers);
        
        Collections.reverse(numbers); // Inverte l'ordine della lista
        System.out.println("Reversed: " + numbers);
        
        Collections.shuffle(numbers); // Permuta casualmente la lista
        System.out.println("Shuffled: " + numbers);
    }
}
```

---

## java.util.Arrays

La classe `Arrays` contiene numerosi metodi statici che operano su array.

### Metodi Principali di Arrays

- `sort(T[] a)`: Ordina l'array specificato in ordine naturale.
- `binarySearch(T[] a, T key)`: Cerca l'elemento specificato nell'array ordinato utilizzando la ricerca binaria.
- `asList(T... a)`: Restituisce una vista dell'array specificato come una lista.
- `copyOf(T[] original, int newLength)`: Copia l'array specificato, troncandolo o riempiendolo con valori null secondo necessità.

#### Esempio di Utilizzo

```java
import java.util.Arrays;

public class ArraysExample {
    public static void main(String[] args) {
        String[] fruits = {"Apple", "Banana", "Cherry"};
        
        Arrays.sort(fruits); // Ordina l'array
        System.out.println("Sorted: " + Arrays.toString(fruits));
        
        int index = Arrays.binarySearch(fruits, "Banana"); // Cerca "Banana"
        System.out.println("Index of Banana: " + index);
        
        String[] moreFruits = Arrays.copyOf(fruits, 5); // Copia l'array
        System.out.println("Copied: " + Arrays.toString(moreFruits));
    }
}
```

---

## Controllo dell’Esecuzione del Thread e ThreadSafety

La sicurezza dei thread (`ThreadSafety`) è un concetto fondamentale in applicazioni multithreaded. Alcune implementazioni delle raccolte, come `Vector` e `Hashtable`, sono thread-safe, il che significa che sono sicure per l'uso da parte di più thread contemporaneamente.

### Quando Usare ThreadSafe Collections

- **Accesso concorrente**: Utilizzare raccolte thread-safe quando più thread possono accedere e modificare la raccolta contemporaneamente.
- **Prestazioni**: Considerare l'overhead della sincronizzazione e scegliere raccolte non sincronizzate quando le prestazioni sono critiche e l'accesso concorrente non è un problema.

#### Esempio di Utilizzo

```java
import java.util.Collections;
import java.util.HashMap;
import java.util.Map;

public class ThreadSafeExample {
    public static void main(String[] args) {
        Map<String, String> synchronizedMap = Collections.synchronizedMap(new HashMap<>());
        synchronizedMap.put("username", "admin");
        synchronizedMap.put("password", "password123");
        
        synchronized (synchronizedMap) {
            for (String key : synchronizedMap.keySet()) {
                System.out.println(key + ": " + synchronizedMap.get(key));
            }
        }
    }
}
```


## Serializzazione dei Dati

### Introduzione

La serializzazione è il processo di conversione di un oggetto in un formato che può essere facilmente salvato su un supporto di memorizzazione (come un file) o trasmesso attraverso una rete. In Java, la serializzazione viene utilizzata per salvare lo stato di un oggetto per un uso successivo o per inviare oggetti tra diverse parti di un'applicazione.

### Come Funziona

In Java, per serializzare un oggetto, la classe dell'oggetto deve implementare l'interfaccia `Serializable`. Questa interfaccia non ha metodi; serve semplicemente come indicatore che la classe può essere serializzata.

#### Esempio di Base

```java
import java.io.Serializable;

public class Person implements Serializable {
    private static final long serialVersionUID = 1L;
    
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getters e setters
}
```

### Serializzazione di Oggetti

Per serializzare un oggetto, utilizziamo le classi `ObjectOutputStream` e `FileOutputStream`.

#### Esempio di Serializzazione

```java
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;

public class SerializationExample {
    public static void main(String[] args) {
        Person person = new Person("Alice", 30);

        try (FileOutputStream fileOut = new FileOutputStream("person.ser");
             ObjectOutputStream out = new ObjectOutputStream(fileOut)) {
            out.writeObject(person);
            System.out.println("Oggetto serializzato salvato in person.ser");
        } catch (IOException i) {
            i.printStackTrace();
        }
    }
}
```

### Deserializzazione di Oggetti

Per deserializzare un oggetto, utilizziamo le classi `ObjectInputStream` e `FileInputStream`.

#### Esempio di Deserializzazione

```java
import java.io.FileInputStream;
import java.io.IOException;
import java.io.ObjectInputStream;

public class DeserializationExample {
    public static void main(String[] args) {
        Person person = null;

        try (FileInputStream fileIn = new FileInputStream("person.ser");
             ObjectInputStream in = new ObjectInputStream(fileIn)) {
            person = (Person) in.readObject();
            System.out.println("Oggetto deserializzato: " + person.getName() + ", " + person.getAge());
        } catch (IOException | ClassNotFoundException i) {
            i.printStackTrace();
        }
    }
}
```

---

## Serializzazione delle Collezioni

Le collezioni Java come `ArrayList`, `HashMap`, e `HashSet` implementano l'interfaccia `Serializable`, quindi possono essere serializzate facilmente. Tuttavia, è importante assicurarsi che tutti gli oggetti contenuti nella collezione siano serializzabili.

### Serializzazione di una Lista

#### Esempio di Serializzazione di ArrayList

```java
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;
import java.util.ArrayList;

public class SerializeArrayList {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");

        try (FileOutputStream fileOut = new FileOutputStream("fruits.ser");
             ObjectOutputStream out = new ObjectOutputStream(fileOut)) {
            out.writeObject(fruits);
            System.out.println("ArrayList serializzato salvato in fruits.ser");
        } catch (IOException i) {
            i.printStackTrace();
        }
    }
}
```

#### Esempio di Deserializzazione di ArrayList

```java
import java.io.FileInputStream;
import java.io.IOException;
import java.io.ObjectInputStream;
import java.util.ArrayList;

public class DeserializeArrayList {
    public static void main(String[] args) {
        ArrayList<String> fruits = null;

        try (FileInputStream fileIn = new FileInputStream("fruits.ser");
             ObjectInputStream in = new ObjectInputStream(fileIn)) {
            fruits = (ArrayList<String>) in.readObject();
            System.out.println("ArrayList deserializzato: " + fruits);
        } catch (IOException | ClassNotFoundException i) {
            i.printStackTrace();
        }
    }
}
```

### Serializzazione di una Mappa

#### Esempio di Serializzazione di HashMap

```java
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;
import java.util.HashMap;

public class SerializeHashMap {
    public static void main(String[] args) {
        HashMap<String, String> countryCapitalMap = new HashMap<>();
        countryCapitalMap.put("USA", "Washington D.C.");
        countryCapitalMap.put("France", "Paris");
        countryCapitalMap.put("Germany", "Berlin");

        try (FileOutputStream fileOut = new FileOutputStream("countryCapitalMap.ser");
             ObjectOutputStream out = new ObjectOutputStream(fileOut)) {
            out.writeObject(countryCapitalMap);
            System.out.println("HashMap serializzato salvato in countryCapitalMap.ser");
        } catch (IOException i) {
            i.printStackTrace();
        }
    }
}
```

#### Esempio di Deserializzazione di HashMap

```java
import java.io.FileInputStream;
import java.io.IOException;
import java.io.ObjectInputStream;
import java.util.HashMap;

public class DeserializeHashMap {
    public static void main(String[] args) {
        HashMap<String, String> countryCapitalMap = null;

        try (FileInputStream fileIn = new FileInputStream("countryCapitalMap.ser");
             ObjectInputStream in = new ObjectInputStream(fileIn)) {
            countryCapitalMap = (HashMap<String, String>) in.readObject();
            System.out.println("HashMap deserializzato: " + countryCapitalMap);
        } catch (IOException | ClassNotFoundException i) {
            i.printStackTrace();
        }
    }
}
```

### Considerazioni sulla Serializzazione delle Collezioni

1. **Consistenza dei Dati**: Assicurarsi che tutti gli oggetti all'interno delle collezioni siano serializzabili.
2. **Versione della Classe**: Utilizzare `serialVersionUID` per mantenere la compatibilità tra diverse versioni di una classe serializzata.
3. **Prestazioni**: La serializzazione può avere un impatto sulle prestazioni, specialmente per collezioni molto grandi.

---

### Riepilogo

- La serializzazione converte un oggetto in un formato che può essere salvato o trasmesso.
- Per serializzare un oggetto in Java, la classe deve implementare `Serializable`.
- Le collezioni Java come `ArrayList` e `HashMap` sono serializzabili.
- Assicurarsi che tutti gli oggetti contenuti nelle collezioni siano serializzabili per evitare errori.

Con questa comprensione della serializzazione, sei pronto a salvare e trasmettere i tuoi dati in modo efficiente in Java!