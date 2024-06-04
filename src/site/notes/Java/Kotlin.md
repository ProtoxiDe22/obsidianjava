---
{"dg-publish":true,"permalink":"/java/kotlin/"}
---

### Introduzione a Kotlin

#### Cos'è Kotlin

##### Storia e Sviluppo

Kotlin è un linguaggio di programmazione statically typed sviluppato da JetBrains, la stessa azienda che ha creato IntelliJ IDEA. È stato introdotto nel 2011 e ha raggiunto la versione stabile 1.0 nel 2016. Kotlin è stato progettato per interoperare completamente con Java e per migliorare le aree in cui Java potrebbe risultare meno efficiente.

##### Obiettivi e Caratteristiche Principali

Kotlin mira a essere un linguaggio di programmazione conciso, sicuro, interoperabile e con strumenti di supporto di alta qualità. Le caratteristiche principali di Kotlin includono:

- **Concisione**: Kotlin riduce il codice boilerplate, aumentando la leggibilità e la manutenibilità.
- **Sicurezza dei tipi**: Kotlin include la null safety, prevenendo molti errori null pointer exceptions.
- **Interoperabilità**: Kotlin è completamente interoperabile con Java, permettendo l'utilizzo di tutte le librerie Java.
- **Funzionalità moderne**: Kotlin supporta funzioni di ordine superiore, lambda, estensioni, coroutines e altro ancora.
---
##### Vantaggi di Kotlin rispetto a Java

###### Sintassi Concisa

Kotlin riduce significativamente la quantità di codice necessaria per compiti comuni. Ad esempio, la dichiarazione di variabili, la creazione di classi e l'implementazione di metodi richiedono meno codice rispetto a Java.

###### Sicurezza dei Tipi (Null Safety)

Una delle caratteristiche più importanti di Kotlin è la null safety, che elimina le null pointer exceptions a tempo di compilazione. Kotlin distingue tra tipi nullable e non-nullable, forzando il programmatore a gestire esplicitamente i valori null.

##### Estensioni e Funzionalità Moderne

Kotlin introduce diverse funzionalità moderne, come le estensioni che permettono di aggiungere metodi a classi esistenti senza modificarle, le funzioni lambda, le coroutines per la programmazione asincrona e le data classes per gestire dati immutabili in modo semplice.

##### Struttura del Progetto Kotlin

Un progetto Kotlin ha una struttura simile a quella di un progetto Java. I file Kotlin hanno estensione `.kt` e seguono la stessa convenzione dei pacchetti. Il punto di ingresso di un'applicazione Kotlin è la funzione `main`.

##### File Principali e Configurazione di Build

I file principali in un progetto Kotlin includono i file sorgente `.kt` e il file di build, solitamente `build.gradle` o `pom.xml`, a seconda del sistema di build utilizzato (Gradle o Maven). La configurazione di build include le dipendenze Kotlin e le configurazioni necessarie per compilare e eseguire il progetto.

---

### Sintassi di Base di Kotlin

#### Variabili e Tipi di Dato

Kotlin supporta la dichiarazione di variabili con parole chiave `var` e `val`. Le variabili dichiarate con `var` sono mutabili, mentre quelle dichiarate con `val` sono immutabili (simili a `final` in Java).

##### Dichiarazione di Variabili (var e val)

```kotlin
var nome: String = "Kotlin"
val eta: Int = 5
```

In questo esempio, `nome` è una variabile mutabile mentre `eta` è una variabile immutabile.

##### Tipi di Dato Comuni

I tipi di dato in Kotlin sono simili a quelli di Java, con alcune differenze:
- `Int`, `Double`, `Float`, `Boolean`, `Char`, `String`
- Array: `Array<Int>`, `Array<String>`
- Collezioni: `List`, `Set`, `Map`

---

### Controllo di Flusso

#### Condizioni (if, when)

Kotlin supporta le espressioni `if` e `when` per il controllo di flusso.

##### if

```kotlin
val numero = 10
val risultato = if (numero > 0) "Positivo" else "Negativo"
```

##### when

```kotlin
val giorno = 3
val nomeGiorno = when (giorno) {
    1 -> "Lunedì"
    2 -> "Martedì"
    3 -> "Mercoledì"
    else -> "Altro"
}
```

---
#### Cicli (for, while)

Kotlin supporta cicli `for` e `while`.

##### for

```kotlin
for (i in 1..5) {
    println(i)
}
```

##### while

```kotlin
var i = 1
while (i <= 5) {
    println(i)
    i++
}
```

---

### Funzioni

#### Definizione e Chiamata di Funzioni

In Kotlin, le funzioni sono definite utilizzando la parola chiave `fun`.

```kotlin
fun somma(a: Int, b: Int): Int {
    return a + b
}

val risultato = somma(3, 4)
```

#### Funzioni di Estensione

Le funzioni di estensione permettono di aggiungere metodi a classi esistenti.

```kotlin
fun String.saluta() {
    println("Ciao, $this!")
}

"World".saluta()
```

---

### Interoperabilità tra Kotlin e Java

#### Chiamare Codice Java da Kotlin

Kotlin può chiamare codice Java senza problemi.

```kotlin
import java.util.Date

fun main() {
    val data = Date()
    println(data)
}
```

#### Chiamare Codice Kotlin da Java

Il codice Kotlin può essere chiamato da Java. Le funzioni Kotlin diventano metodi statici nella classe di supporto Kotlin.

```java
// In Java
import FunzioniKt;

public class Main {
    public static void main(String[] args) {
        int risultato = FunzioniKt.somma(3, 4);
        System.out.println(risultato);
    }
}
```

---
### Null Safety

#### Operatore Elvis

L'operatore Elvis (`?:`) fornisce un valore di default quando l'operando sinistro è null.

```kotlin
val nome: String? = null
val lunghezza = nome?.length ?: -1
```

#### Safe Calls e Not-null Assertion

Le safe calls (`?.`) eseguono un'operazione solo se l'oggetto non è null. La not-null assertion (`!!`) lancia un'eccezione se l'oggetto è null.

```kotlin
val lunghezza = nome?.length // Safe call
val lunghezzaNonNulla = nome!!.length // Not-null assertion
```

---

### Programmazione Orientata agli Oggetti

#### Classi e Oggetti

Le classi in Kotlin sono definite con la parola chiave `class`.

```kotlin
class Persona(val nome: String, var eta: Int)

val persona = Persona("Alice", 30)
```

#### Interfacce e Ereditarietà

Le interfacce sono definite con la parola chiave `interface`.

```kotlin
interface Lavoratore {
    fun lavora()
}

class Dipendente : Lavoratore {
    override fun lavora() {
        println("Sto lavorando")
    }
}
```

---

### Programmazione Funzionale

#### Lambda e Funzioni di Ordine Superiore

Le lambda sono funzioni anonime che possono essere passate come argomenti.

```kotlin
val somma = { a: Int, b: Int -> a + b }
println(somma(3, 4))
```

Le funzioni di ordine superiore accettano altre funzioni come parametri.

```kotlin
fun operazione(a: Int, b: Int, operazione: (Int, Int) -> Int): Int {
    return operazione(a, b)
}

val risultato = operazione(3, 4, somma)
println(risultato)
```

#### Collezioni e Operazioni su Collezioni

Kotlin fornisce una vasta gamma di operazioni su collezioni.

```kotlin
val numeri = listOf(1, 2, 3, 4, 5)
val numeriPari = numeri.filter { it % 2 == 0 }
println(numeriPari)
```

---

### Confronto tra Kotlin e Java

#### Similitudini

##### Strutture Comuni

Kotlin e Java condividono molte strutture comuni, come classi, interfacce e metodi.

##### Paradigmi di Programmazione

Entrambi i linguaggi supportano la programmazione orientata agli oggetti e la programmazione funzionale.

#### Differenze

##### Sintassi

La sintassi di Kotlin è più concisa e moderna rispetto a quella di Java.