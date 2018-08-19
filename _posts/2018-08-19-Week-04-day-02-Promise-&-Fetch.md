---
layout: post
title:  "Week-04 day-02 Promise & Fetch"
date:   2018-08-19 18:28:20 +0800
categories: JSA
---

Material 

- [Fetch API vs XMLHttpRequest](https://stackoverflow.com/questions/35549547/what-is-the-difference-between-the-fetch-api-and-xmlhttprequest) 
- [How to escape promise hell](https://medium.com/@pyrolistical/how-to-get-out-of-promise-hell-8c20e0ab0513) 
- [Promise in MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) 
- [Fetch API in MDN](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) 
- [`fetch()` in MDN](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch) 

## Material Review

 -  promise
     -  `.resolve()`
     -  `.reject()`
     -  `.then()`
     -  `.catch()`
     -  `.finally()`
     -  chaining
 -  Fetch API
     -  `fetch()`
 -  `await`

 
 ### Promise

#### Then

```javascript
const URL = 'http://whatthecommit.com/index.txt';

const myAsyncAjax = (url) => {
  return new Promise((resolve, reject) => {
    const xhr = new XMLHttpRequest();
    xhr.open('GET', url);
    xhr.onload = () => resolve(xhr.responseText);
    xhr.onerror = () => reject(xhr.statusText);
    xhr.send();
  });
};

myAsyncAjax(URL).then((response) => {
  console.log(response);
});
```

#### Catch

```javascript
const erroredFunction = () =>{
  return new Promise(() => {
    throw new Error('Uh-oh!');
  });
};

const promise = erroredFunction();
promise.catch((error) => {
  console.log(error.message);
});
```

### Fetch

```javascript
const URL = 'http://api.icndb.com/jokes/random';

fetch(URL)
  .then(response => response.json())
  .then(myJson => console.log(myJson));
```

### Exercises
 
 -  [Promise, it won't hurt](promise-it-wont-hurt/README.md)
