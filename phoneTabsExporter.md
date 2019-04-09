## For Android Phones

1. set up USB debugging on your phone
2. plug your USB in and allow MTP connection
3. open Chrome devtool remote device panel
4. choose your device, and expand the list
5. make your devtool in pop-out mode
6. option+cmd+I to open a new devtool for the old devtool
7. copy paste and run the following code, which will copy the results as markdown to clipboard

```js
tabs = document.querySelectorAll('div /deep/ div /deep/ div /deep/ div /deep/ div /deep/ .device-page-list .vbox')
str = '';
for (i=0;i<tabs.length;i++){
  if (tabs[i].querySelector('.device-page-url .devtools-link') != null){
    str += '- ['+tabs[i].querySelector('.device-page-title').textContent + '](' + tabs[i].querySelector('.device-page-url .devtools-link').getAttribute('href') +')\n'
  } else {
    console.log(tabs[i])
  }
}
copy(str)
```

8. paste the results to vscode, save the file and shift+cmd+V to preview the markdown file