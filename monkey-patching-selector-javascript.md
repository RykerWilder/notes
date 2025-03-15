# Monkey Patching QuerySelector JavaScript

This is a way not to write repetitive code in JavaScript and that simplifies readability in the selection of elements of the DOM.

---

```bash
const $one = document.querySelector.bind(document);
const $all = document.querySelectorAll.bind(document);

// Select the first item with class "container"
const container = $one(".container");

// Select all items with class "item"
const items = $all(".item");
```
**$one** is a function that executes document.querySelector. You can use it to select a single element from the DOM.
**$all** is a function that executes document.querySelectorAll. You can use it to select all items that match a selector.

The bind method creates a new function that, when called, has its this value set to the provided object (in this case, document). This is useful because querySelector and querySelectorAll are document methods, and by using bind(document), we make sure that these methods are always called with document as the context (this).
