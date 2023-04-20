# 手写AJAX

```javascript
const request = new XMLHttpRequest();
request.open('GET', '/xxx');

request.onreadystatechange = function () {
  if (request.readyState === 4) {
    if (request.status >= 200 && request.status < 300) || request.status === 304) {
      success(request);
    } else {
      fail(request);
    }
  }
};

request.send('{"name":"request"}');

```
