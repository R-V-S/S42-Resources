`innerText` will return what you _see_ while `textContent` will return what's there. If an element is hidden, for example, `innerText` won't return that content. But the biggest difference is that `textContent` is standard and fully cross-browser compatible.

As far as where to use them:

* Just plain don't use `innerText`.
* Use `textContent` to get the text of an **element**.
* Use `innerHTML` to get the raw HTML of an **element**.
* Use `nodeValue` to get the content of a **node**. Note that you'll rarely – if ever – have to do this. Note also that this **doesn't work on elements**.
* Use `firstChild`, `lastChild`, or `childNodes` to get the **nodes** of an **element**. Note that you'll rarely have to do this.