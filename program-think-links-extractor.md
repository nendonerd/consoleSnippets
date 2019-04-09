## For [program-think.blogspot.com](http://program-think.blogspot.com)
Copy the following code to console, then it will extract all links appeared in the article.

```js
{
  let urls = document.querySelector('#post-body-9131156520945940228').querySelectorAll('a')
  let container = document.createElement('div')
  let br = document.createElement('br')
  urls.forEach(a => {container.append(a); container.append(br.cloneNode(true))})
  document.body.replaceWith(container)
}
```