# 建立文字標籤

下面使用三種方式都可以建立字串"`Hello.`"：

```javascript
// html語法：完整寫出內容
var txt1 = "<p>Hello.</p>";
  
// jQuery語法：利用.text() method將字串append進去
var txt2 = $("<p></p>").text("Hello.");

// DOM語法
var txt3 = document.createElement("p");
txt3.innerHTML = "Hello.";


$("body").append(txt1, txt2, txt3);
```

