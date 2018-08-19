---
layout: post
title:  "Week-03 day-02 Callback and Events"
date:   2018-08-19 17:33:20 +0800
categories: JSA
---

## Callback

### Material Review

 -  callback
 -  timers
    -  `setTimeout`
    -  `setInterval`
    -  `clearTimeout`
    -  `clearInterval`

**Try to avoid [callback hell](http://callbackhell.com/)**

## Events

## Material Review

- event
  (
    A real life action what you want to handle in your program.
    - an automatic door, action: you walked into the observed area
    - the elevator, action: you pushed the button
    - rendering website, action: content loaded
    - communicating with the server, action: response received
  )
- javascript events
  - `click`, `mouseenter`, `mouseleave`
  - `focus`, `blur`, `input`, `change`, `submit`
  - `keyup`, `keypress`, `keydown`,
  - `scroll`,
  - `readystatechange`,
    (
      Why is it fired 4 times?
    )
  - `load`
    (
      The load event can be used to detect a fully-loaded page. (each stylesheet, image, subframes, etc...)
      It is fired on the window element, window.addEvenetListener('load', ...); then the js file can operate the dom after it loaded.
    )
  - `DOMContentLoaded` - optional
    (
      The DOMContentLoaded event is fired when the document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading
      It is fired on the document object, document.addEventListener('DOMContentLoaded, ...);
    )
- event target
  (
    EventTarget is an interface implemented by objects that can receive events and may have listeners for them.
    Element, document, and window are the most common event targets, but other objects can be event targets too, for example XMLHttpRequest, AudioNode, AudioContext, and others.
  )
  - `addEventListener`, `HTMLElement.on...`
  - `removeEventListener`
  - `dispatchEvent` - optional. if you don't want to listen a certain element, you can dispatch the event to the parent and listen the whole. 
    (
      Fires the event on the EventTarget
    )
- event bubbling
  (
    The browser checks to see if the element that was actually clicked on has an onclick event handler registered on it in the bubbling phase, and runs it if so.
    Then it moves on to the next immediate ancestor element and does the same thing, then the next one, and so on until it reaches the <html> element.
  )
  - `event.target`, `event.currentTarget`
    (
      event.target: the originator HTMLElement which dispatched the event
      event.currentTarget: the HTMLElement on we handle the event
    )
- `preventDefault()` // when use a ```<Form>```tag and submit something, you may need to prevent the default action
  (prevents the default behaviour, like anchor navigation and form submission)


### Candy shop

Find the HTML skeleton of the game in the [candy game](workshop/candy-game) folder.

- Gather 10.000 candies!
- Clicking the ‘Create candies’ button gives you 1 candy.
- You can buy a lollipop for 100 candies by clicking the ‘Buy lollipop’ button.
- 10 lollipops generate 1 candy per second.
  - Use the 🍭 emoji to display the lollipops you have
- Display the candy producton rate in the `Candies / Second` row
- If you press the "make candy rain" button, the candy generation should speed up 10x

### Advanced exercises

- [Infinite scroll 💪](workshop/infinite-scroll/README.md)
- [Dispatch click](workshop/dispatch-click/index.html)
- [Custom events 💪💪](workshop/custom-events/index.html)
