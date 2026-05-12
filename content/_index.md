
+++

title = "Web Intro - HTML, CSS, JS"
description = "A Hugo theme for creating Reveal.js presentations"
outputs = ["Reveal"]
aliases = [
    "/guide/"
]

+++

{{% accentify "top-right" %}}
# Introduzione al **Web**
{{% /accentify %}}

## HTML, CSS, JavaScript

<small>
A cura di Nicholas Magi
</small>

<br>

{{% pdf %}}

---
{{% section %}}

# Il Web

{{% callout type="cite" src="[Enciclopedia Treccani]" srcLink="https://www.treccani.it/enciclopedia/web_%28Enciclopedia-Italiana%29/" %}}
Il **web** (abbreviazione di *world wide web*, 'ragnatela mondiale', spesso indicato brevemente anche come www) è un sistema di **interconnessione tra documenti** basato sull'infrastruttura di Internet che permette l'accesso a tutta l'informazione disponibile su computer collegati in rete.
{{% /callout %}}

---

### Sul **web** possono essere disponibili **qualsiasi tipo di documenti**.

Immagini, video, audio, documenti Word, PDF...

---

### Architettura **Client-Server** 

<img class="w-50" src="imgs/web-arch.png"/>

---

### Cosa succede quando si fa una richiesta sul web?

```mermaid
sequenceDiagram
    actor Client (Browser)
    Client (Browser)->>+DNS: IP of www.google.com?
    DNS->>+Client (Browser): 8.8.8.8
    Client (Browser)->>+Server: HTTP-REQ Can I get https://8.8.8.8/home.html?
    Server->>+Client (Browser): HTTP-RES Sure! `200 OK`
    Server-->>+Client (Browser): HTTP-RES Cannot find what you were looking for! `404 NOT FOUND`
```

{{% /section %}}

---

## Web standards

- Tecnologie utilizzate per costruire **siti web**.

### Princìpi chiave

1. Libera contribuzione e utilizzo
2. Accessibilità
3. Retrocompatibilità

---

## Dispense di un "vecchio" seminario

"**[React for Dummies / Web Basics](
https://github.com/Nickolausen/react-for-dummies/tree/master/web-basics)**", corso pomeridiano PNRR **@** I.T.T. "Blaise Pascal"

---

{{% section %}}

<img style="max-width: 128px" class="exclude" src="https://cdn-icons-png.flaticon.com/512/174/174854.png" />

<br>

<small>
<a href="https://www.flaticon.com/free-icons/html" title="html icons">Html icons created by Freepik - Flaticon</a>
</small>


## **HTML**
### **H**yperText **M**arkup **L**anguage

[Guida di riferimento: MDN Docs](https://developer.mozilla.org/en-US/docs/Web/HTML)

---

### Linguaggio di markup
- come $\LaTeX{}$, markdown, XML...
- definisce la *struttura* e il *contenuto* di una pagina

<br>
<br>

{{% callout type="warning"%}} 
**Non è un linguaggio di programmazione**!
{{% /callout %}}

---

![](imgs/HTML.png)

---

## HTML: **Tag**

- Una pagina si compone di un insieme di **tag**:
  - ogni tag è composto da un **nome** (*case insensitive*) circondato da `<` e `>`;
  - per ogni tag possono essere specificati alcuni attributi coppia `nome="valore"` che specifica alcune proprietà dell’elemento

---

{{% multicol %}}
{{% col %}}

### Codice sorgente

```html { linenos=inline hl_lines=["4", "15"] }
<!DOCTYPE html> 
<!-- Dichiaro il tipo di documento -->

<html>
  <!-- Parte di metadati della pagina -->
    <head>
      <title>Il mio bellissimo sito</title>
    </head>

    <!-- Contenuto della pagina -->
    <body>
      <p>Lorem Ipsum Ipse Dixit</p>
        <a href="www.google.com">Mi sento fortunato</a>
    </body>
</html>
```
{{% callout %}}
In evidenza il tag `<html>`, **radice** della pagina.
{{% /col %}}

{{% /callout %}}
{{% col %}}

### Render

<iframe height="500"
  sandbox
  srcdoc="<!DOCTYPE html> 
<!-- Dichiaro il tipo di documento -->

<html>
  <!-- Parte di metadati della pagina -->
    <head>
      <title>Il mio bellissimo sito</title>
    </head>

    <!-- Contenuto della pagina -->
    <body>
      <p>Lorem Ipsum Ipse Dixit</p>
        <a href="www.google.com">Mi sento fortunato</a>
    </body>
</html>">
</iframe>
{{% /col %}}

{{% /multicol %}}

---

## Semantica dei tag

![Semantica](imgs/semantica.png)

Ogni tag deve essere usato in accordo con il **contenuto che deve rappresentare**.

---

## Tag di sectioning 

{{% multicol %}}
{{% col %}}
```html { linenos=inline }
<!DOCTYPE html>

<html>
  ...
  <body>
      <header>
          <nav>
              ...
          </nav>
      </header>

      <main>
          <aside>
              ...
          </aside>
          <div>
              <section>
                  ...
              </section>
              <article>
                  ...
              </article>
          </div>
          <aside>
              ...
          </aside>
      </main>
      
      <footer>
          ...
      </footer>
  </body>
</html>
```
{{% /col %}}
{{% col %}}
![Sectioning](imgs/sectioning.png)

{{% callout %}}
Scheletro del codice sorgente e render corrispondente (*decorato con CSS!*)
{{% /callout %}}

{{% /col %}}
{{% /multicol %}}

---

#### Alcuni tag fondamentali
### `<img/>`

- `<img src="link-to-img" alt="what-img-represents">`
  - `src`: percorso dell’immagine (salvata nel filesystem o sul web)
  - `alt`: testo alternativo (mostrato quando l’immagine non viene caricata correttamente)

---

#### Alcuni tag fondamentali
### `<a></a>`

`<a href="www.google.com" target="_blank">Clicca qui</a>`
  - `href`: URL del tag.
  - `target`: specifica dove deve essere aperto quel link — `_blank` indica “in una nuova tab”.

---

## Attributi

- Ce ne sono tanti, alcuni visti poco fa (`href`, `target`, `src`, `alt`...)
- Alcuni sono **universali** — comuni a tutti i tag esistenti:
    - <mark><code>class</code></mark>
    - <mark><code>id</code></mark>
    - `style`
    - `data-`
    - ...

---

## Attributi
<mark><code>class</code> vs <code>id</code></mark>
- **`class`**: identifica un **gruppo di elementi** a cui voglio attribuire caratteristiche comuni.
- **`id`**: identifica un **singolo elemento** della mia pagina.

Entrambi permettono di interagire con il documento HTML tramite **fogli di stile** o **script esterni**.

---

## Attività **#01**

<img class="w-75" src="imgs/gravatar.png">

https://it.gravatar.com/

{{% /section %}}

---

{{% section %}}

<img class="exclude" style="max-width: 128px;" src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ab/Official_CSS_Logo.svg/960px-Official_CSS_Logo.svg.png" />

## **CSS**
### **C**ascading **S**tyle **S**heet

---

### Cascading Style Sheet
- Tecnologia particolarmente odiata, ma comunque **fondamentale** — è *ovunque*;
- Ha l'importante compito di separare il **contenuto** dalla sua **presentazione**
  - definisce infatti <mark><b>come</b></mark> un contenuto HTML deve essere presentato

<br>
<br>

{{% callout type="warning" %}} 
**Non è un linguaggio di programmazione**!
{{% /callout %}}

---

![CSS](imgs/CSS.png)

---

### Importare un foglio di stile
1. foglio di <mark>stile <b>inline</b></mark> 
    - attributo `style` del tag che voglio stilare
2. foglio di <mark>stile <b>interno</b></mark>  
    - importato in `<head>` dal tag `<style>`
3. foglio di <mark>stile <b>esterno</b></mark>  
    1. importato in `<head>` dal tag `<style>`
    2. importato in `<head>` dal tag `<link>`

---

#### 1. CSS inline

```html { linenos=inline hl_lines=["2"] }
...
    <header style="color:blue;">
        <h1>Monsters and Co.</h1>
    </header>
...
```

<br/>
{{% callout type="danger" %}}
**Pessimo**, mischia il contenuto e la presentazione. 
{{% /callout %}}

---

#### 2. CSS in `<head>`
```html { linenos=inline hl_lines=["2-8"] }
...
    <head>
        <style type="text/css">
            header {
                color: blue;
            }
        </style>
    </head>
    <body>
        <header>
            <h1>Monsters and Co.</h1>
        </header>
    </body>
...
```

{{% callout type="warning"%}}
Iniziamo ad isolare contenuto e presentazione, ma ancora siamo dentro ad HTML.
{{% /callout %}}

---

#### 3.1 Foglio esterno

{{% multicol %}}
{{% col %}}
```html { linenos=inline hl_lines=["5-7"]}
<!DOCTYPE html>

<html>
  <head>
      <style type="text/css">
        @import url("styles.css");
      </style>
  </head>
  <body>
    <header>
      <h1>Monsters and Co.</h1>
    </header>
  </body>
</html>
```
`index.html`
{{% /col %}}
{{% col %}}
```css
header {
  color: blue;
}
```
`styles.css`
{{% /col %}}
{{% /multicol %}}

{{% callout %}}
Inusuale, ma ci siamo! Esiste tuttavia un'alternativa — più diffusa.
{{% /callout %}}

---

#### 3.2 Foglio esterno

{{% multicol %}}
{{% col %}}
```html { linenos=inline hl_lines=["5"]}
<!DOCTYPE html>

<html>
  <head>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <header>
      <h1>Monsters and Co.</h1>
    </header>
  </body>
</html>
```
`index.html`
{{% /col %}}
{{% col %}}
```css
header {
  color: blue;
}
```
`styles.css`
{{% /col %}}
{{% /multicol %}}

{{% callout type="success" %}}
Noi facciamo così!
{{% /callout %}}

---

## Funzionamento
- Un foglio di stile si compone di una serie di regole, scritte una dopo l'altra;
  - queste vengono applicate a **cascata** (non a caso il linguaggio si chiama *Cascade Style Sheet*), 
    - partendo dall'alto e scendendo in maniera sequenziale fino alla fine del foglio;
  - logica da tenere a mente per evitare eventuali <mark><b>conflitti</b></mark> tra <mark>diverse regole</mark> applicate ad uno <mark>stesso elemento</mark>;

---

## Sintassi

{{% multicol %}}
{{% col %}}

### In generale
```css
selettore {
  proprietà: valore;
}
```
{{% /col %}}
{{% col %}}

### Esempio
```css
a[href="https://www.google.com"] {
  text-decoration: none;
  color: red;
  font-weight: bold;
}
```
{{% /col %}}
{{% /multicol %}}

<table>
  <thead>
    <tr>
      <td>#</td>
      <td>specifica</td>
      <td>esempio</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>selettore</code></td>
      <td>a chi applicare le regole di stile</td>
      <td><code>div</code>, <code>.nav-link</code>...</td>
    </tr>
    <tr>
      <td><code>proprietà</code></td>
      <td>caratteristica di stile assegnabile ad un elemento</td>
      <td><code>margin</code>, <code>padding</code>...</td>
    </tr>
  </tbody>
</table>

---

## Selettori, pt. 01
Più utilizzati
| **Tipologia**     | **Selettore**        |
|---------------|------------------:|
| universale    | `*`                |
| di tipo       | `E`                |
| di prossimità | `E{ ,>,+,~}F`      |
| di classe     | `E{.,#}main-title` |

---

## Selettori, pt. 02

| **Tipologia**                    | **Selettore**                     |
|------------------------------|-------------------------------:|
| di pseudo-classi             | `E:link`, `E:hover`               |
| di pseudo-classi strutturali | `E:first-child`, `E:nth-child(n)` |
| di pseudo-elementi           | `E:before`, `E:after`             |
| di attributi                 | `E[attr]`                       |

---

## Selettori
{{% multicol %}}
{{% col %}}

### Elemento HTML

```html
<div id="provaID"></div>
```
{{% /col %}}

{{% col %}}

### Foglio CSS

```css
div#provaID { 
  background-color: red; 
}

div.provaClasse { 
  background-color: blue; 
}

div { 
  background-color: green; 
}
```
{{% /col %}}
{{% /multicol %}}

> Di quale colore sarà lo sfondo del `div`?

---

## Priorità delle regole
{{% multicol %}}
{{% col %}}
In ordine **decrescente** di importanza
1. Media
2. Importanza di una dichiarazione
3. Origine della dichiarazione
4. Specificità del selettore
5. Ordine delle dichiarazioni
{{% /col %}}

{{% col %}}
{{% callout type="tip" %}}
`!important` fornisce **max. priorità**:
```css
p { 
  font-size: 3px !important 
}
```
{{% /col %}}
{{% /callout %}}
{{% /multicol %}}

{{% /section %}}