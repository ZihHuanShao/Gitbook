# 動態物件click方法

假設`#aaa`為一動態建立的物件\(`button`或`img`或其他\)，若想要實作**點擊觸發事件**，第一個方法會無效，因為`click`方法只能套用在預先建立好的物件。

因此，必須使用第二個方法

```css
// METHOD 1: NOT work!
$("#aaa").click(function(){
	alert("aaa")
	$(this).parent().remove()
})

// METHOD 2: Workabe
$(document.body).on('click', '#aaa', function(event) {
	$(this).parent().remove()
});	
```

