## For crawling any site's <img>
1. copy the following code into console and run
2. Chrome may prompt for your permission to download multiple files! hit allow and enjoy

```js
let srcs = $$('img').map(img => img.src)

for (src of srcs) {

  fetch(src).then(res => res.blob()).then(blob => {

    let e = document.createEvent('MouseEvents')
    let a = document.createElement('a')

    a.download = String(Date.now())
    a.href = window.URL.createObjectURL(blob)

    e.initMouseEvent('click', true, false, window, 0, 0, 0, 0, 0, false, false, false, false, 0, null)
    a.dispatchEvent(e)

  })
}
```