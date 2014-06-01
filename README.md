#Comparify

Simple criteria checking, so you can test a subset of an object's properties.

```
var comparify = require('comparify');

var data = {
  timestamp: 1395877795067,
  deviceID: '765CBA',
  recipient: {
    name: 'Thomas'
  },
  uses: ['making pancakes', 'running', 'hugs']
};

comparify(data, {deviceID: '765CBA'}) === true;
comparify(data, {deviceID: 'ABC123'}) === false;

comparify(data, {'recipient.name': 'Thomas'}) === true;
comparify(data, {recipient: {name: 'Thomas'}}) === true;

comparify(data, {uses: 'running'}) === true;
comparify(data, {uses: 'skiing'}) === false;

comparify(data, {uses: ['running', 'hugs']}) === true;
comparify(data, {uses: ['running', 'skiing']}) === false;
```

## To Do

- [x] Add support for arrays (any / all matching)
- [ ] Add support for more types of comparison
  - [ ] Greater than / less than
  - [ ] Range
- [ ] Add support for regex comparison