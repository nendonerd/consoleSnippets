## For [天天美剧](http://www.ttmeiju.me/)
Go to a page with download links. Copy the following code into console and run, then it will copy the links to clipboard. You can paste them into download software such as 115.com

There're 2 parameters in this code
> `resolution` can be any string that all your desired download links have in common. e.g I want to download all 1080p videos, and their filenames all have '1080' in common.

> `method` specify download method. it has only 5 valid value:
  - `"百度云盘下载"`
  - `"磁力下载"`
  - `"ed2k高清片源"`
  - `"迅雷高清美剧下载"`
  - `"玩客云免费会员加速"`


```js
{
  const resolution = '1080'
  const method = '磁力下载'

  let urls = []
  let trs = document.querySelectorAll('#seedlist > tr')
  for (let i=0; i<trs.length; i++) {
    let id = document.querySelector(`#seedlist > tr:nth-child(${i}) > td:nth-child(2) > a`)
    let methods = document.querySelectorAll(`#seedlist > tr:nth-child(${i}) > td:nth-child(3) > a`) || []
    let url = [...methods].find(m => m.title === method)
    id && id.textContent && id.textContent.includes(resolution) && url && url.href && urls.push(url.href)
  }
  let urlStr = urls.reduce((pre, cur) => pre += cur.slice(0, cur.indexOf('&')) + '\n', '')

  console.log(urlStr)
  copy(urlStr)
  console.log('-'.repeat(Math.round(urlStr.length / urls.length - 1)))
  console.log(`${urls.length} urls copied!`)
}
```
