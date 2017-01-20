#HSLIDE
## CSS
### Cascading Style Sheets
(C) Pedro Miguel Moreira 2016-2017

#HSLIDE
### Syntax
fundamental syntax

```css
selector {
	property1: value1;
	property2: value2;
	/* comment */
}
```

#HSLIDE
### selectors : element or type
element selector
 * selects nodes by element name

```css
element { /* style */ }
```
examples

```css
p {
	color: black;
	text-decoration: underline;
	}
```

```html
<p> * some text</p>
<p class="news"> * another text</p>
```

#HSLIDE
### selectors:  class
class selector
 * selects node by class name

```css
.class { /* style */ }
```
examples

```css
.news {
	font-size: larger;
	}
```
```html
<p class="news highlight"> * some text</p>
<div class="news"> * another content</p>
```


#HSLIDE
### selectors : id
id selector
 * selects node by id

```css
#id { /* style */ }
```
examples

```css
#copyright {
	font-size: larger;
	}
```

```html
<p id=#copyright> * some text</p>
```

#HSLIDE
### selectors : descendants

Nodes Selected by B which area descendants of A

```css
A   B { /* style */ }
```
examples

```css
div .news {
	color: blue;
	}
```

```html
<div>
 <p class="news"> * one</p>
 <form>
 	<h1 clas="news"> * letter </h1>
 	<p> two </p>
 </form>
</div>
```

#HSLIDE
### selectors : child

Nodes Selected by B which are children of A

```css
A > B { /* style */ }
```
examples

```css
div>.news {
	color: blue;
	}
```

```html
<div>
 <p class="news"> * one</p>
 <form>
 	<h1 clas="news"> letter </h1>
 	<p> two </p>
 </form>
</div>
```

#HSLIDE
### selectors : adjacent

Nodes B which immediately follow Nodes A (sharing a common parent)
(

```css
A + B { /* style */ }
```
examples

```css
div + .news { color: blue; }
```

```html
<div>
 <p class="news"> one</p>
 <form>
 	<h1 class="news"> letter </h1>
 	<p> two </p>
 </form>
</div>
<p class="news"> * three </p>
<p class="news"> four </p>
```

#HSLIDE
### selectors : siblings

Nodes B which are preceded by nodes A (sharing a common parent)

```css
A ~ B { /* style */ }
```
examples

```css
div ~ .news { color: blue; }
```

```html
<div>
 <p class="news"> one </p>
 <form>
 	<h1 class="news"> letter </h1>
 	<p> two </p>
 </form>
</div>
<p class="news"> * three </p>
<p class="news"> * four </p>
```

#HSLIDE
### selectors : pseudo-classes

pseudo-class is a keyword added to selectors to specify a special state of the selected element.

```css
selector:pseudo-class { /* style */ }
```
examples

`:first-child` selects elements that are first-children of their parents.

```css
p:first-child {font-size : 5em}
```

```html
<div>
 <p class="news"> * one </p>
 <form>
 	<h1 class="news"> letter </h1>
 	<p> two </p>
 </form>
</div>
<p class="news"> three </p>
<p class="news"> four </p>
```

#HSLIDE
### selectors : pseudo-classes
### some more pseudo-classes


|   |      |  |
|:---------|:----------|:-------|
| :active   | :link      | :not()  |
| :checked  | :disabled  | :focus  |
| :any | :checked | :default 
| :disabled | :empty | :enabled
| :first | :first-child | :first-of-type
| :focus | :hover | :last-of-type
| :not() | :nth-child() | :nth-last-child()
| :nth-last-of-type() | :nth-of-type() | :only-child
| :required | :right | :root |

#HSLIDE
### selectors : pseudo-elements

A pseudo-element is added to selectors, allowing to style parts of it

```css
selector::pseudo-element { /* style */ }
```
examples

`:first-letter` selects the first chars of selected elements.

```css
p::first-letter {color : magenta}
```

```html
<div>
 <p class="news"> *o*ne </p>
 <form>+
 	<h1 class="news"> *l*etter </h1>
 	<p> *t*wo </p>
 </form>
</div>
<p class="news"> *t*hree </p>
```

#HSLIDE
### selectors : pseudo-elements
### some more pseudo-elements

||||
|:---|:---|:---|
|::after|::before|::first-letter|
|::first-line|::selection|::backdrop|
|::placeholder |::marker |::spelling-error |
|::grammar-error||| 

#HSLIDE
### selectors : attribute selectors
Attribute selectors select an element using the existence of a given attribute or attribute value.

* [attr]
 * Represents an element with an attribute name of attr (any value)
* [attr=value]
 * value is exactly "value".
* [attr~=value]
 * value is a space-separated list of words, one of them is "value".
 
#HSLIDE
### selectors : attribute selectors

* [attr|=value]
 * value is exactly "value" or begin with “value” immediately followed by “-”
* [attr^=value]
 * value is prefixed by "value".
* [attr$=value]
 * value is suffixed by "value".
* [attr*=value]
 * value has "value" as substring.
* [attr operator value i]
 * Add an i (or I) before the closing bracket for case-insensitivity

 
#HSLIDE
### selectors : attribute selectors

```css
    [lang] {text-decoration : underline;}
    p[lang="pt"] {color: red;}
    p[lang*="BR"] {color: lime;}
    a[href$=pdf]::after {content: " (PDF)";}
```

```html
    <p lang="pt-PT">Olá</p>
    <p lang="pt-BR">Oi</p>
    <a href="manual.pdf">Manual de PT </a>    
```
#HSLIDE
#&nbsp;
#media queries

Media Queries is a module of CSS enabling to define expressions allowing to condional styles to fit a specific range of output devices.

example:  styles 
```css
@media (min-width : 50em) { 
	html {background-color: blue}
	/* ... */
}
```

#HSLIDE
###media queries
```css
@media print {
  body { font-size: 8pt }
}
@media screen {
  body { font-size: 20px }
}
@media screen, print {
  body { line-height: 1.2 }
}

@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px)
  and (-webkit-min-device-pixel-ratio: 2) {
    body { line-height: 1.4 }
}

```
#HSLIDE
#### disclaimer
with parts from:
* MDN by Mozilla Contributors
