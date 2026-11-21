# Usage

```javascript
const item = TravianElements.find(12);
console.log(item.name, item.css, item.xpath);

const villageTitle = TravianElements.get(12);
const villages = TravianElements.getAll(26);
const css = TravianElements.selector(80, 'css');
const xp = TravianElements.selector(80, 'xpath');
```

The numeric keys refer to the numbering in the supplied dictionary.
