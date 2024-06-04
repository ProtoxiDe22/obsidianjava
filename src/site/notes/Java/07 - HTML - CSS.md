---
{"dg-publish":true,"permalink":"/java/07-html-css/"}
---

## Cos'è HTML

HTML (HyperText Markup Language) è il linguaggio di markup utilizzato per creare pagine web. Esso utilizza tag per definire la struttura e il contenuto di un documento.

### Esempio di codice HTML di base:

```html
<!DOCTYPE html>
<html>
<head>
    <title>La mia prima pagina web</title>
</head>
<body>
    <h1>Benvenuti al corso di HTML e CSS</h1>
    <p>Questo è un paragrafo di esempio.</p>
</body>
</html>
```

### Spiegazione del codice:

- `<!DOCTYPE html>`: Dichiarazione del tipo di documento, indica che stiamo usando HTML5.
- `<html>`: Tag radice che contiene tutto il contenuto della pagina.
- `<head>`: Contiene metadati come il titolo della pagina.
- `<title>`: Definisce il titolo della pagina che appare nella barra del browser.
- `<body>`: Contiene il contenuto visibile della pagina.
- `<h1>`: Tag di intestazione, usato per titoli principali.
- `<p>`: Tag di paragrafo, usato per il testo del contenuto.

---

## Struttura di un Documento HTML

Un documento HTML è composto da una serie di elementi annidati, ciascuno con uno scopo specifico. Vediamo una struttura più dettagliata:

```html
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pagina Web di Esempio</title>
</head>
<body>
    <header>
        <h1>Benvenuti alla mia Pagina Web</h1>
    </header>
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
    <main>
        <section id="home">
            <h2>Home</h2>
            <p>Questa è la sezione Home.</p>
        </section>
        <section id="about">
            <h2>About</h2>
            <p>Questa è la sezione About.</p>
        </section>
        <section id="contact">
            <h2>Contact</h2>
            <p>Questa è la sezione Contact.</p>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 La mia Pagina Web</p>
    </footer>
</body>
</html>
```

### Spiegazione aggiuntiva:

- `<meta charset="UTF-8">`: Imposta la codifica dei caratteri del documento.
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Rende il sito responsive, adattandolo alle dimensioni del dispositivo.
- `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`: Tag semantici che migliorano la struttura e la leggibilità del codice.

---

## Cos'è CSS

CSS (Cascading Style Sheets) è il linguaggio usato per descrivere la presentazione di un documento scritto in HTML. Consente di separare il contenuto dalla presentazione, migliorando la manutenzione e la flessibilità.

### Esempio di codice CSS:

```css
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
}

h1, h2 {
    color: #333;
}

p {
    color: #666;
}

header, nav, main, footer {
    padding: 20px;
    background: #f4f4f4;
    margin-bottom: 10px;
}
```

### Spiegazione del codice:

- `body { ... }`: Stile applicato al corpo del documento.
- `font-family`: Definisce il tipo di carattere.
- `line-height`: Imposta l'altezza della linea per migliorare la leggibilità.
- `h1, h2 { ... }`: Stile applicato ai titoli di livello 1 e 2.
- `color`: Imposta il colore del testo.
- `header, nav, main, footer { ... }`: Stile applicato ai tag semantici per una presentazione coerente.

---

## Come Integrare CSS in HTML

Ci sono tre modi per integrare CSS in un documento HTML:

1. **Inline CSS**: Stile direttamente nell'elemento HTML.
2. **Internal CSS**: Stile all'interno dell'elemento `<style>` nel `<head>`.
3. **External CSS**: Stile in un file separato collegato tramite `<link>`.

### Esempi:

**Inline CSS:**

```html
<p style="color: blue;">Questo testo è blu.</p>
```

**Internal CSS:**

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        p {
            color: red;
        }
    </style>
</head>
<body>
    <p>Questo testo è rosso.</p>
</body>
</html>
```

**External CSS:**

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" type="text/css" href="stile.css">
</head>
<body>
    <p>Questo testo sarà stilizzato tramite un file CSS esterno.</p>
</body>
</html>
```

**stile.css:**

```css
p {
    color: green;
}
```

---

## Selettori e Proprietà CSS

CSS utilizza selettori per applicare stili a elementi HTML specifici. I selettori più comuni sono:

1. **Selettore di tipo**: Seleziona tutti gli elementi di un certo tipo.
2. **Selettore di classe**: Seleziona elementi con una specifica classe.
3. **Selettore ID**: Seleziona un elemento con un ID specifico.

### Esempi:

**Selettore di tipo:**

```css
p {
    color: purple;
}
```

**Selettore di classe:**

```css
.intestazione {
    color: orange;
}
```

HTML:

```html
<p class="intestazione">Questo è un paragrafo con una classe.</p>
```

**Selettore ID:**

```css
#intro {
    color: brown;
}
```

HTML:

```html
<p id="intro">Questo è un paragrafo con un ID.</p>
```

---

## Creare una Pagina Web Semplice

Costruiamo una semplice pagina web passo dopo passo.

### Passo 1: Creare una struttura di base

```html
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pagina Semplice</title>
</head>
<body>
    <header>
        <h1>La Mia Prima Pagina Web</h1>
    </header>
    <main>
        <p>Benvenuto nel mio sito web.</p>
    </main>
    <footer>
        <p>&copy; 2024 La Mia Pagina Web</p>
    </footer>
</body>
</html>
```

### Passo 2: Aggiungere contenuti

```html
<main>
    <section>
        <h2>Chi Siamo</h2>
        <p>Questa è una breve descrizione di chi siamo.</p>
    </section>
    <section>
        <h2>I Nostri Servizi</h2>
        <p>Descrizione dei servizi offerti.</p>
    </section>
</main>
```

---

## Styling di Base con CSS

### Cambiare Colori e Font

```css
body {
    font-family: 'Helvetica', sans-serif;
    background-color: #f0f0f0;
    color: #333;
}

h1, h2 {
    color: #0066cc;
}

p {
    font-size: 16px;
}
```

### Layout e Posizionamento

Usiamo Flexbox per creare un layout di base:

```css
header, main, footer {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
    background: #e0e0e0;
    margin-bottom: 10px;
}
```

Aggiorniamo l'HTML per migliorare il layout:

```html
<header>
    <h1>La Mia Prima Pagina Web</h1>
</header>
<main>
    <section>
        <h2>Chi Siamo</h2>
        <p>Questa è una breve descrizione di chi siamo.</p>
    </section>
    <section>
        <h2>I Nostri Servizi</h2>
        <p>Descrizione dei servizi offerti.</p>
    </section>
</main>
<footer>
    <p>&copy; 2024 La Mia Pagina Web</p>
</footer>
```

# Uso Avanzato dei Selettori CSS e Flexbox

---

## Selettori CSS

I selettori CSS sono strumenti potenti per applicare stili specifici agli elementi HTML. Vediamo più in dettaglio come usare e combinare diversi tipi di selettori.

### Selettori di Tipo

I selettori di tipo si applicano a tutti gli elementi di un certo tipo.

```css
p {
    color: blue;
}
```

### Selettori di Classe

I selettori di classe si applicano agli elementi che hanno un attributo `class` specifico. Per assegnare una classe a un elemento, si usa il punto (`.`) seguito dal nome della classe.

```css
.intestazione {
    color: green;
}
```

HTML:

```html
<p class="intestazione">Questo è un paragrafo con una classe.</p>
```

### Selettori ID

I selettori ID si applicano agli elementi che hanno un attributo `id` specifico. Per assegnare un ID a un elemento, si usa il cancelletto (`#`) seguito dal nome dell'ID. Gli ID devono essere unici all'interno di una pagina.

```css
#intro {
    color: red;
}
```

HTML:

```html
<p id="intro">Questo è un paragrafo con un ID.</p>
```

### Combinare i Selettori

È possibile combinare più selettori per creare stili più specifici.

**Discendenti:**

Applica lo stile agli elementi che sono discendenti di un altro elemento.

```css
div p {
    color: purple;
}
```

HTML:

```html
<div>
    <p>Questo paragrafo sarà viola.</p>
</div>
```

**Combinatori:**

I combinatori sono simboli che permettono di selezionare elementi basandosi sulla loro relazione con altri elementi.

- **Selettore figlio (`>`):**

```css
div > p {
    color: orange;
}
```

HTML:

```html
<div>
    <p>Questo paragrafo sarà arancione.</p>
    <div>
        <p>Questo paragrafo non sarà arancione.</p>
    </div>
</div>
```

- **Selettore adiacente (`+`):**

```css
h1 + p {
    color: brown;
}
```

HTML:

```html
<h1>Intestazione</h1>
<p>Questo paragrafo sarà marrone.</p>
<p>Questo paragrafo non sarà marrone.</p>
```

### Selettori di Attributo

I selettori di attributo permettono di selezionare elementi basati sugli attributi e sui valori degli attributi.

```css
a[href] {
    color: pink;
}
```

HTML:

```html
<a href="https://www.example.com">Link con attributo href</a>
<a>Link senza attributo href</a>
```

Più specificamente, possiamo selezionare in base al valore dell'attributo.

```css
a[href="https://www.example.com"] {
    color: yellow;
}
```

### Selettori Pseudo-classe

Le pseudo-classi selezionano elementi in uno stato particolare.

```css
a:hover {
    color: red;
}
```

HTML:

```html
<a href="#">Passa il mouse su questo link</a>
```

---

## Flexbox

Flexbox è un sistema di layout potente che rende facile l'allineamento e la distribuzione degli elementi all'interno di un contenitore.

### Contenitore Flex

Per creare un contenitore flex, si usa la proprietà `display: flex;`.

```css
.container {
    display: flex;
}
```

HTML:

```html
<div class="container">
    <div>Elemento 1</div>
    <div>Elemento 2</div>
    <div>Elemento 3</div>
</div>
```

### Direzione del Flex

La proprietà `flex-direction` specifica la direzione degli elementi.

```css
.container {
    display: flex;
    flex-direction: row; /* or column */
}
```

### Allineamento degli Elementi

Flexbox offre diverse proprietà per l'allineamento degli elementi.

- **justify-content**: Allinea gli elementi lungo l'asse principale.

```css
.container {
    display: flex;
    justify-content: center; /* or flex-start, flex-end, space-between, space-around */
}
```

- **align-items**: Allinea gli elementi lungo l'asse trasversale.

```css
.container {
    display: flex;
    align-items: center; /* or flex-start, flex-end, stretch, baseline */
}
```

### Esempio Completo

```css
.container {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    height: 100vh;
}

.container div {
    background: lightblue;
    padding: 20px;
    margin: 10px;
}
```

HTML:

```html
<div class="container">
    <div>Elemento 1</div>
    <div>Elemento 2</div>
    <div>Elemento 3</div>
</div>
```

---

## Padding e Margin

### Padding

Il padding è lo spazio interno tra il contenuto di un elemento e il suo bordo. Si può specificare singolarmente per ogni lato (top, right, bottom, left) oppure in un unico shorthand.

```css
.elemento {
    padding-top: 10px;
    padding-right: 15px;
    padding-bottom: 20px;
    padding-left: 25px;
}
```

**Shorthand:**

```css
.elemento {
    padding: 10px 15px 20px 25px;
}
```

### Margin

Il margin è lo spazio esterno tra il bordo di un elemento e gli elementi circostanti. Anche il margin può essere specificato singolarmente o in shorthand.

```css
.elemento {
    margin-top: 10px;
    margin-right: 15px;
    margin-bottom: 20px;
    margin-left: 25px;
}
```

**Shorthand:**

```css
.elemento {
    margin: 10px 15px 20px 25px;
}
```

### Esempio Completo con Padding e Margin

```css
.elemento {
    padding: 20px; /* Padding su tutti i lati */
    margin: 15px; /* Margin su tutti i lati */
    background-color: lightgray;
}
```

HTML:

```html
<div class="elemento">
    Questo è un elemento con padding e margin.
</div>
```