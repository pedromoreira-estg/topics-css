#HSLIDE
## CSS
### Cascading Style Sheets
(C) Pedro Miguel Moreira 2016

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
## sample HTML document
<pre>color: <b>hsla</b>(
  <span class="hsl-value" id="hsl-h-value">277,</span> <input id="hsl-h" type="range" min="0" max="360" value="128" onchange="changeHSL()">
  <span class="hsl-value" id="hsl-s-value">37%,</span> <input id="hsl-s" type="range" min="0" max="100" value="75" onchange="changeHSL()">
  <span class="hsl-value" id="hsl-l-value">33%,</span> <input id="hsl-l" type="range" min="0" max="100" value="33" onchange="changeHSL()">
  <span class="hsl-value" id="hsl-a-value">1.00);</span> <input id="hsl-a" type="range" min="0" max="100" value="100" onchange="changeHSL()">
        </pre>

#HSLIDE
## sample HTML document
#### tree
<img src="html-tree.svg.png" alt="Drawing" style="width: 400px;"/>

#HSLIDE
## sample HTML document
#### dom navigation
<img src="html-links.svg.png" alt="Drawing" style="width: 400px;"/>

#HSLIDE
#### dom navigation, children

Node.children returns a live HTMLCollection of child elements.

Node.childNodes returns a live NodeList of child nodes (inluding text nodes and comments)

```javascript
var elements = element.children; 
var nodes = element.childNodes; 
```

#HSLIDE
#### dom navigation, children

Node.firstChild and Node.lastChild return the first/last child of a given node (or null, if none)

```javascript
var childNode = node.firstChild;
var childNode = node.lastChild;
```

#HSLIDE
#### dom navigation, parents

Node.parentNode returns the parent node of a given Node (it can be a Node, a Document or a DocumentFragment). Returns null if no parent is set.

Node.parentElement returns the parent Element of a given Node (always a DOM Element or null).

```javascript
parentNode = node.parentNode;
parentElement = node.parentElement;
```

#HSLIDE
#### dom navigation, brothers

// nodes can be Text

```javascript
nextNode = node.nextSibling;
prevNode = node.previousSibling;

var nextElement = element.nextElementSibling; 
var prevElement = element.previousElementSibling; 
```

#HSLIDE
#### locating elements

**Locating by id**

returns an `Element`

```
// returns an element
var e = document.getElementById(id);
```
#HSLIDE
#### locating elements

**Locating by Tag Name**

returns a **live** `HTMLCollection`

```
var nl = document.getElementsByTagName(tagName);
var nl = <element>.getElementsByTagName(tagName);
```

#HSLIDE
#### locating elements

**Locating by Class Name**

returns a **live** ```HTMLCollection```

```
var nl = document.getElementsByClassName(classNames);
var nl = <element>.getElementsByClassName(classNames);
```

#HSLIDE
#### selecting nodes

**selecting by query selector**

retuns the first Element that matches

```
var e = document.querySelector(cssQuery);
// also available at the Element interface
var e = <element>.querySelector(cssQuery);
```

retuns a **non-live** NodeList that matches

```
// returns a nl NodeList that matches
var nl = document.querySelectorAll(cssQuery);
// also available at the Element interface
var nl = <element>.querySelector(cssQuery);

```

#HSLIDE
#### creating nodes

In an HTML document, the Document.createElement() method creates the HTML element specified by tagName.
Document.createTextNode() creates a new Text node.

```
var e = document.createElement(tagName[, options]);
var new = document.createTextNode(text); 
```

#HSLIDE
#### set/get HTML content

The Element.innerHTML property sets or gets the HTML syntax describing the element's descendants.

```
// get
var content = element.innerHTML;
// set
element.innerHTML = content;
```

#HSLIDE
#### insert HTML content

Element.insertAdjacentHTML() parses the specified text as HTML and inserts the resulting nodes into a specified position.

```
element.insertAdjacentHTML(position, text);
```
position can take the following values:
 
 * `'beforebegin'` : just before the element 
 * `'afterbegin'` : before first child
 * `'beforeend'` : after last child
 * `'afterend'` : after the element

#HSLIDE
#### replacing nodes

The Node.replaceChild() method replaces one child node of the specified node with another.

```
var old = parentNode.replaceChild(new, old);
```

#HSLIDE
#### inserting nodes

The Node.appendChild() method adds a node to the end of the list of children of a specified parent node. If the node is already parented then it is reparented.

The Node.insertBefore() method inserts the specified node before the reference node as a child of the current node.

```
var n = element.appendChild(n); 
var iNode = parentNode.insertBefore(new, reference);
```
#HSLIDE
#### cloning nodes

The Node.cloneNode() method returns a duplicate of the node on which this method was called.

deep is a boolean flag. `deee=true` if the node should be deep cloned , i.e., with its children, or `deep=false` if only the node is cloned.

```
var clonedNode = node.cloneNode([deep]);
```

#HSLIDE
#### removing nodes

The Node.removeChild() method removes a child node from the DOM. Returns the removed node.

```
// to keep a reference (to later reuse)
var removed = node.removeChild(child);
// to free it from memory ASAP
element.removeChild(child);
```

#HSLIDE
#### get / set classes and ids

className gets and sets the value of the class attribute of the specified element (a space-separeted list of classes).

id gets and sets the value of the id attribute of the specified element.

```javascript
var cName = element.className; // Get the classes
element.className = cName; // Set the classes

var idName = elt.id; // Get the id
element.id = idName; // Set the id

```

#HSLIDE
#### get / set arbitrary attributes

getAttribute() returns the value of a specified attribute on the element.

setAttribute() sets the value of a specified attribute on the element

```javascript
element.setAttribute(attName, attValue);
var attValue = element.getAttribute(attNamne);
```

**hint :** use 'data-' prefix for custom attributes to avoid conflicts.


#HSLIDE
#### styles, set
```
// Multiple style properties via style
element.style.cssText = "color: blue"; 

//Multiple style properties via attribute
element.setAttribute("style", "color: blue");

// Direct property assignment
elt.style.color = "blue";
```

#HSLIDE
#### styles, get
```
var style = window.getComputedStyle(element);
```

#HSLIDE
#### Event
The Event represents any event which takes place in the DOM

* user-generated
 * mouse or keyboard events
* generated by APIs
 * animation has finished running
 * a video has been paused

#HSLIDE
#### target
The target represents the object where the event originated
#### currentTarget
The currentTarget represents the object where the event handler was attached (may be not the same as the target, as events bubble through the DOM).

#HSLIDE
#### Event, adding listeners
```
target.addEventListener(type, listener, [, options]);
target.addEventListener(type, listener, [, useCapture]);
```

type : event type
 
 * 'click', 'mouseover', 'load', ...
 
#HSLIDE
#### Event, adding listeners

listener : a callback function or a EventListener object


```
div = document.getElementById('div001');
p.addEventListener('click', function (e) {
  console.log(e); // function logic
  }
p.addEventListener('click', sayHi);
function sayHi(event) {
  // function logic
  console.log(e);
}
 
```

#HSLIDE
#### Event, adding listeners

**Benefits usin addEventListener**

* more than a single handler
* finer-grained control of the phase when the listener gets activated (capturing vs. bubbling)
* It works on any DOM element, not just HTML elements.

#HSLIDE
#### Event, adding listeners

**the 'old' way **

// 1. Pass a function reference (just the name without, ()'s)
el.onclick = modifyText;

// 2. Using a function expression
element.onclick = function() {
  // ... function logic ...
};


#HSLIDE
#### Event, mouse Events

 * click
 * dblclick
 * mouseover
 * mouseenter
 * mouseleave
 * mouseout
 * mousemove
 * mouseup
 * mousedown
 * wheel
 * select

#HSLIDE
#### Event, Drag & Drop

 * dragstart
 * drag
 * dragend
 * dragenter
 * dragover
 * dragleave
 * drop

#HSLIDE
#### Event, key

 * keydown
 * keyup
 * keypress



#HSLIDE
#### Event, key events

```
<p>This page turns violet when you hold the V key.</p>
<script>
  addEventListener("keydown", function(event) {
    if (event.keyCode == 86)
      document.body.style.background = "violet";
  });
  addEventListener("keyup", function(event) {
    if (event.keyCode == 86)
      document.body.style.background = "";
  });
</script>

```

#HSLIDE
#### Event, mouse Events

```
<style>
  body {
    height: 200px;
    background: beige;
  }
  .dot {
    height: 8px; width: 8px;
    border-radius: 4px; /* rounds corners */
    background: blue;
    position: absolute;
  }
</style>
<script>
  addEventListener("click", function(event) {
    var dot = document.createElement("div");
    dot.className = "dot";
    dot.style.left = (event.pageX - 4) + "px";
    dot.style.top = (event.pageY - 4) + "px";
    document.body.appendChild(dot);
  });
</script>

```

#HSLIDE
#### Event, cancelling default behaviour

```
<a href="https://developer.mozilla.org/">MDN</a>
<script>
  var link = document.querySelector("a");
  link.addEventListener("click", function(event) {
    console.log("Nope.");
    event.preventDefault();
  });
</script>
```

#HSLIDE
#### disclaimer
with parts from:
* Eloquent JavaScript by Marijn Haverbeke
* MDN by Mozilla Contributors
