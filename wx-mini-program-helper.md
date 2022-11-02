### wx.navigateTo params need decode twice
use case
```js
 uni.navigateTo({
    url: fullUrl,
    query:{
        data:JSON.stringfy([{name:12}])
        }
})
JSON.parse(decodeURIComponent(decodeURIComponent(arrayJsoned)))
```
https://www.mybj123.com/15009.html

