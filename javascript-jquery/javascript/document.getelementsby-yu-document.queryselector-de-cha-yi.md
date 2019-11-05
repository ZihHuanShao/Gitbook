# JS document.getElementsBy\*\* 與 document.querySelector\*\*\* 的差異

透過 `document.querySelector` / `document.querySelectorAll` 取得的 NodeList 是**靜態**的。

### 範例1

使用`getElementsBy**`取得的`allDivs`為動態的值，會隨者元素的變化及時更新

```markup
<!DOCTYPE html>
<html>
<body>
<p id="demo"></p>
<p id="demo2"></p>

<div id="outer">
  <div id="inner">inner</div>
</div>

<script>

  // <div id="outer">
  var outerDiv = document.getElementById('outer');

  // 所有的 <div> 標籤
  var allDivs = document.getElementsByTagName('div');

  console.log(allDivs.length);    // 2
  document.getElementById("demo").innerHTML = allDivs.length;

  // 清空 <div id="outer"> 下的節點
  outerDiv.innerHTML = '';

  // 因為清空了<div id="outer"> 下的節點，所以只剩下 outer
  console.log(allDivs.length);    // 1
  document.getElementById("demo2").innerHTML = allDivs.length;

</script>

</body>
</html>

```

### 輸出

```text
2
1
```

### 範例2

使用`querySelector***`取得的`allDivs`為靜態的值，永遠為第一次取得的值

```markup
<!DOCTYPE html>
<html>
<body>
<p id="demo"></p>
<p id="demo2"></p>

<div id="outer">
  <div id="inner">inner</div>
</div>

<script>

  // <div id="outer">
  var outerDiv = document.getElementById('outer');

  // 所有的 <div> 標籤
  var allDivs = document.querySelectorAll('div');

  console.log(allDivs.length);    // 2
  document.getElementById("demo").innerHTML = allDivs.length;

  // 清空 <div id="outer"> 下的節點
  outerDiv.innerHTML = '';

  // 因為清空了<div id="outer"> 下的節點，所以只剩下 outer
  console.log(allDivs.length);    // 1
  document.getElementById("demo2").innerHTML = allDivs.length;

</script>

</body>
</html>

```

### 輸出

```text
2
2
```

雖然第二次印出為2，不過實際上`<div id="inner">inner</div>`已經被清空了

## Ref.

{% embed url="https://ithelp.ithome.com.tw/articles/10191765" %}



