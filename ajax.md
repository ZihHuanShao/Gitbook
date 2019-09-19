# JS AJAX

* AJAX = **A**synchronous **J**avaScript **A**nd **X**ML
* AJAX是關於在後台加載數據並將其顯示在網頁上，而無需重新加載整個頁面。
  * 例子：Gmail, Google Maps, Youtube, and Facebook tabs
* AJAX不是程式語言，而是使用下列組合：
  * 瀏覽器有內建`XMLHttpRequest object`\(用來向web server請求數據\)
  * JavaScript與HTML DOM

瀏覽器支援的object：

* **`XMLHttpRequest`**：現今所有瀏覽器均支援（包含IE7+、Firefox、Chrome、Safari 以及 Opera）
* **`ActiveXObject`**：IE5 和 IE6
* 
建立`XMLHttpRequestb object`語，且判斷是否為老版本：

```javascript
if (window.XMLHttpRequest) {
   // code for modern browsers(IE7+, Firefox, Chrome, Opera, Safari)
   xmlhttp = new XMLHttpRequest();
 } else {
   // code for old IE browsers(IE6, IE5)
   xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
}
```

**XMLHttpRequest** 方法列表

| Method | Description |
| :--- | :--- |
| `new XMLHttpRequest()` | 建立 XMLHttpRequest object |
| `abort()` | 取消當前請求 |
| `getAllResponseHeaders()` | 回傳標頭訊息 |
| `getResponseHeader()` | 回傳指定的標頭訊息 |
| `open(`_`method, url, async, user, psw)`_ | 指定請求： _`method`_: 請求類行為 GET 或 POST _`url`_: 檔案位置 _`async`_: true \(非同步\) or false \(同步\) _`user`_: optional user name _`psw`_: optional password |
| `send()` | 向server發送請求 \(用於GET要求\) |
| `send(`_`string`_`)` | 向server發送請求 \(用於POST要求\) |
| `setRequestHeader()` | 增加一組label/value到要發送的標頭 |

**XMLHttpRequest** 屬性列表

| 屬性 | Description |
| :--- | :--- |
| **`onreadystatechange`** | `readyState`屬性更改時要呼叫的函數 |
| **`readyState`** | `XMLHttpRequest`請求的狀態： 0: 請求未初始化 1: server connection建立 2: 接收請求 3: 處理請求 4: 請求完成並且響應準備就緒  |
| **`responseText`** | 回傳數據以string格式 |
| **`responseXML`** | 回傳數據以XML格式 |
| **`status`** | 回傳請求的狀態status： 200: "OK" 403: "Forbidden" 404: "Not Found" 完整列表清參考 [Http Messages Reference](https://www.w3schools.com/tags/ref_httpmessages.asp) |
| **`statusText`** | 回傳狀態的text格式 \(如"OK" or "Not Found"\) |







#### Ref.

{% embed url="https://www.w3schools.com/js/js\_ajax\_http.asp" %}



