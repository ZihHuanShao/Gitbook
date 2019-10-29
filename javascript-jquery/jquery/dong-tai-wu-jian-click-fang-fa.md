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

{% hint style="info" %}
**Note:** Event handlers attached using the on\(\) method will work for both current and FUTURE elements \(like a new element created by a script\).

添加事件的方法`on`，適用於當前及未來的元素\(由腳本動態建立的新元素\)
{% endhint %}

## Ref.

{% embed url="https://www.w3schools.com/jquery/event\_on.asp" %}



