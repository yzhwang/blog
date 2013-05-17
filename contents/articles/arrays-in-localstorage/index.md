title: Arrays in LocalStorage
author: Juan Olvera
date: 2013-05-02 12:00
template: article.jade

One of the first things I tried with *localStorage* is to store an array, but what I got instead when was a string.

```javascript
// create a var and store an array on it
var languages = ['c','python','javascript','php'];

// save it on localStorage
localStorage.setItem('languages', languages);

console.log(localStorage.getItem('languages'));

// response
c,python,javascript,php
```

Screenshot:

![](http://i.imgur.com/ifIHfH8.png)

The reason is that *localStorage* only accept strings, so after googled a bit I learned that the right way to use it is with `JSON.stringify` and `JSON.parse`:

```javascript
// create an array
var languages = ['c', 'python', 'javascript', 'php'];
	
// save the array in localStorage using JSON.stringify
localStorage.setItem('languages', JSON.stringify(languages));

// create a variable and store localStorage data using JSON.parse
var data = JSON.parse(localStorage.getItem('languages'));

// log the variable to see how are we getting the data
console.log(data);

// response 
["c", "python", "javascript", "php"]
```

Screenshot:

![](http://i.imgur.com/AX11Yyp.png)

More info about localStorage:

- [Diving into localStorage](http://diveintohtml5.info/storage.html)
- [Storing data in the browser with the HTML5 localStorage API](http://toddmotto.com/storing-data-in-the-browser-with-the-html5-local-storage-api/)
- [There is no simple solution for local storage](https://hacks.mozilla.org/2012/03/there-is-no-simple-solution-for-local-storage/)