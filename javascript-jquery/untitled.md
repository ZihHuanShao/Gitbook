# jQ CSS 屬性

取得element的CSS屬性，或設定element的CSS屬性

```javascript
// 取得第一個<p>的background-color屬性
$("p").css("background-color");

// 設定所有<p>的background-color屬性
$("p").css("background-color", "yellow");

// 同時設定所有<p>的多個(background-color與font-size)屬性
$("p").css({"background-color": "yellow", "font-size": "200%"});

```

