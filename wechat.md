## For [微信网页版](https://wx.qq.com/)

1. login wechat
2. scroll friend list to find who you want to contact
3. paste the following code into console and run
4. then type `autoSend(user, text)` in console, `user` is a string of the username which you want to contact, `text` is a string of text you want to send.
5. you can wrap the function with anything, such as send in specify time`setTimeout(() => autoSend(...), TimeToSend - Date.now())`

```js
function autoSend(username, text) {
  let nameElems = document.querySelectorAll('span.nickname_text.ng-binding')
  let pre = document.querySelector('div.content.ng-isolate-scope > pre')
  let send = document.querySelector('a.btn.btn_send')

  try {
    [...nameElems]
      .find(elem => elem.textContent === username)
      .parentElement.parentElement.parentElement
      .click()
  } catch(e) {
    console.log(`username:"${username}" not found`)
  }

  angular.element(pre).scope().editAreaCtn = text
  send.click()
}
```
