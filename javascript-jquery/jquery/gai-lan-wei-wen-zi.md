# 改欄位文字

第一種方法

```javascript
<script>
  $(document).ready(function(){
    $("#show").click(function(){
      $("#aaa").text("hello world!");
      // 或
      $("#aaa").html("hello world!");
    });
  });
</script>

<body>
  <p id="aaa">If you click on the "Hide" button, I will disappear.</p>
  <button id="show">Show</button>
</body>
```

{% embed url="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery\_hide\_show" %}



第二種方法

```javascript
<body>

  <p id="demo" onclick="myFunction()">Click me to change my HTML content (innerHTML).</p>
  
  <script>
    function myFunction() {
      document.getElementById("demo").innerHTML = "Paragraph changed!";
      // 或
      document.getElementById("demo").innerText = "Paragraph changed!";

    }
  </script>
  
</body>
```

{% embed url="https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref\_element\_innerhtml" %}



