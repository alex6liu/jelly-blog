---
layout: post
title:  "Week-01 day-01 HTML & CSS Intro"
date:   2018-08-19 16:38:20 +0800
categories: JSA
---

### Use [mdn](https://developer.mozilla.org) as the reference website rather than w3cschool 

### [HTML basics](https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/HTML_basics)

HTML (Hypertext Markup Language) is the code that is used to structure a web page and its content.

![](https://mdn.mozillademos.org/files/9347/grumpy-cat-small.png)

![](https://mdn.mozillademos.org/files/9345/grumpy-cat-attribute-small.png)

- HTML tags
   - `<html>`
   - `<head>`
   - `<link>`
   - `<script>`
   - `<body>`
   - `<meta>`
   - `<title>`
   - `<h1>` - `<h6>`
   - `<p>`
   - `<a>`
   - `<img>`
   - `<article>`
   - `<aside>`
   - `<strong>`
   - `<em>`
   - `<span>`
   - `<div>`
   - `<header>`
   - `<main>`
   - `<footer>`
   - `<section>`
   - `<ul>`
   - `<ol>`
   - `<li>`
   - `<dl>`
   - `<dd>`
   - `<dt>`
   - `<pre>`

**Try to use class rather than id(cause id should be unique and it's hard to make sure that)**

### [CSS basics](https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/CSS_basics)

### Selector

#### Type selector
Selects all elements that match the given node name.

Syntax: eltname

Example: input will match any ```<input>``` element.

#### Class selector
Selects all elements that have the given class attribute.

Syntax: .classname

Example: .index will match any element that has a class of "index".

#### ID selector
Selects an element based on the value of its id attribute. There should be only one element with a given ID in a document.

Syntax: #idname

Example: #toc will match the element that has the ID "toc".

#### Universal selector
Selects all elements. Optionally, it may be restricted to a specific namespace or to all namespaces.

Syntax: ```* ns|* *|*```

Example: * will match all the elements of the document.

#### Attribute selector
Selects elements based on the value of the given attribute.

Syntax: [attr] [attr=value] [attr~=value] 
[attr|=value] [attr^=value] [attr$=value] [attr*=value]

Example: [autoplay] will match all elements that have the autoplay attribute set (to any value).


### Combinators

#### Adjacent sibling combinator
The + combinator selects adjacent siblings. This means that the second element directly follows the first, and both share the same parent.

Syntax: A + B

Example: h2 + p will match all ```<p>``` elements that 
directly follow an ```<h2>```.

#### General sibling combinator
The ~ combinator selects siblings. This means that the second element follows the first (though not necessarily immediately), and both share the same parent.

Syntax: A ~ B

Example: p ~ span will match all <span> elements that follow a ```<p>```.

#### Child combinator
The > combinator selects nodes that are direct children of the first element.

Syntax: A > B

Example: ul > li will match all ```<li>``` elements that are nested directly inside a ```<ul>``` element.

#### Descendant combinator
The   (space) combinator selects nodes that are descendants of the first element.

Syntax: A B

Example: div span will match all <span> elements that are inside a ```<div>``` element.

### [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

Hypertext Transfer Protocol (HTTP) is an application-layer protocol for transmitting hypermedia documents, such as HTML. It was designed for communication between web browsers and web servers.
