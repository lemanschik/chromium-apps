# Comlink
you should avoid it but if you got existing code this could help you to understand the concepts


```js
let rR = (el={}) => {
  console.log(el && el.tagName)
  return el && el.tagName ? (el.parentElement ? rR(el.parentElement) + ' > ' : '') + el.tagName + (el.id ? '#' + el.id : '') : ''
}

// 
// Comlink.transferHandlers.set("EVENT", {
//   canHandle: (obj) => obj instanceof Event,
//   serialize: (ev) => {
//     ev.target.setAttribute(ev.type, "")
//     return [
//       {
//         target: {
//           id: ev.target.id,
//           tagName: ev.target.tagName,
//           classList: [...ev.target.classList],
//           innerText: ev.target.innerText
//         },
//         type: ev.type
//       },
//       [],
//     ];
//     // document.querySelector(ev.target.tagName[ev.type]).removeAttribute(ev.type)
//   },
//   deserialize: (obj) => obj,
// });
```
