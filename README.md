# Nexus Runtime Assets — Travian Elements Library

A JavaScript selector library generated from the supplied Arabic `قاموس العناصر.txt`.

## Current source
- Version: `1.0.0`
- Parsed records: **307**
- Every parsed record contains at least one CSS selector and one XPath selector.
- Original selector strings are preserved in `src/elements.json`.
- The runtime bundle is `dist/travian-elements.js`.

## Usage

```html
<script src="https://cdn.jsdelivr.net/gh/KhaledOu/nexus-runtime-assets@main/dist/travian-elements.js"></script>
<script>
  const villageFields = TravianElements.getAll(1);
  const selector = TravianElements.selector(1, 'css');
  const villageName = TravianElements.text(12);
</script>
```

Tampermonkey:

```javascript
// @require https://cdn.jsdelivr.net/gh/KhaledOu/nexus-runtime-assets@main/dist/travian-elements.js

const villageName = TravianElements.get(12);
```

## API
- `resolve(key, { mode: 'css' | 'xpath' | 'all' })`
- `selector(key, mode)`
- `get(key, context)` / `getAll(key, context)`
- `waitFor(key, { timeout, interval, context })`
- `exists(key, context)`
- `text(key, context)` / `attr(key, attribute, context)`
- `search(query)`
- `find(key)`

`key` can be a dictionary number, an ID such as `e001`, or a matching Arabic name.

## Important
The selectors are stored as supplied. The library has not been verified against a live Travian server. Some selectors are contextual, some are alternatives separated by commas, and some may depend on browser selector support (for example `:has()`). Test each selector on its intended page before relying on it in automation.

The library only locates elements; it does not implement game actions or click behavior.
