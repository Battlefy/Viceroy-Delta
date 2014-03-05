Viceroy Delta
=============

Viceroy Schema is a delta implementation
developed for the (soon to be released) Viceroy ORM.

Designed as a standalone package to allow anyone
to create and apply deltas without needing an entire
ORM.

Use it with node or in the browser using
browserify.

```shell
npm install viceroy-delta
```

[![NPM version](https://badge.fury.io/js/viceroy-delta.png)](http://badge.fury.io/js/viceroy-delta)

[![Browser Support](https://ci.testling.com/Battlefy/Viceroy-Delta.png)](https://ci.testling.com/Battlefy/Viceroy-Delta)

Example
-------
```javascript
var delta = require('viceroy-delta');

// create an old version of a person record
var oldRecord = {
  name: {
    first: 'John',
    last: 'Doe'
  },
  born: new Date('Jan 23, 1981'),
  sex: 'M'
};

// create an new version of a person record
var newRecord = {
  name: {
    first: 'Johnny',
    last: 'Doe'
  },
  born: new Date('Jan 24, 1981'),
  sex: 'M'
};

// create a delta from the old and new copy of the record
var delta = delta.create(oldRecord, newRecord);

// lets look at the diff
delta.diff => {
  $set: {
    'name.first': 'Johnny',
    born: Sat Jan 24 1981 00:00:00 GMT-0800 (PST)
  }
};
```
