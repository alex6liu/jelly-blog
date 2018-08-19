---
layout: post
title:  "Week-03 day-04 HTTP basics and XHR"
date:   2018-08-19 17:51:20 +0800
categories: JSA
---

## Material Review

 -  XMLHttpRequest
 -  request methods  
 -  `.open`
 -  `.send`
 -  `.setRequestHeader`
 -  `.onreadystatechange`
 -  `.onload`
 -  [status codes](http://www.restapitutorial.com/httpstatuscodes.html) | [status cats](https://http.cat/)
 -  `.readyState`
 -  `.response`
 -  Blocking / non-blocking
 -  Callbacks
 -  XML
 -  JSON
 -  API-s
 -  API keys
 -  Fetch API
 -  [Cross origin](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)


```
// if method='GET'
const ajax = (method, url, callback, payload = null) => {
  const httpRequest = new XMLHttpRequest(); // eslint-disable-line
  httpRequest.onload = () => {
    const responseObject = JSON.parse(httpRequest.response);
    callback(responseObject);
  };
  httpRequest.open(method, url);
  httpRequest.setRequestHeader('Content-Type', 'application/json');
  httpRequest.send(JSON.stringify(payload));
};
```


```
// if method='POST'
const ajax = (method, url, callback, payload = data) => {
  const httpRequest = new XMLHttpRequest(); // eslint-disable-line
  httpRequest.onload = () => {
    // check status
  };
  httpRequest.open(method, url);
  httpRequest.setRequestHeader('Content-Type', 'application/json');
  httpRequest.send(JSON.stringify(payload));
};
data = {};
```