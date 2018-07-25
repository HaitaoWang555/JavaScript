## 写一个 ajax
```
var xhr = new XMLHttpRequest()
xhr.open('GET','/XXX',true)
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log(xhr.responseText)
  }
}
xhr.send()
```