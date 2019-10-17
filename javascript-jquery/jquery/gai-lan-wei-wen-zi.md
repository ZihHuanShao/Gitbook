# 改欄位文字

第一種方法

```javascript
<script>
  $(document).ready(function(){
    $("#show").click(function(){
      $("p").show();
      //或
      $("#aaa").text("hello world!");
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
    }
  </script>
  
</body>
```

{% embed url="https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref\_element\_innerhtml" %}



