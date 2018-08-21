---
layout: post
title:  "Week-05 day-01 React Intro"
date:   2018-08-20 20:40:20 +0800
categories: JSA React
---

## export and import
```
// source.js
const a = 5;
const b = 6;
module.exports = {
  a,
  b,
};

// app.js
const mySource = require('./source');
```

**import from is not es6 standard**

## npm initialize

npm initialization: 

```npm init // create package.json```

install packages:

```npm i(install) package-name // create node_modules folder```

modify the .gitignore

```node_modules // cause it's huge```

when we don't have node_modules

```npm install --save package-name // store the dependency to the package.json```

```npm install // to install the dependencies```


### some commands
```
npm i create-react-app
create-react-app project-name

npm install -g
npm install -dev

npm start
npm run build
npm run eject
```

### babel
translate es6 code to es5


### jsx
**in jsx have to use className**


