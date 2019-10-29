# on: Attach multiple event handlers

```javascript
$(document).ready(function(){
  $("input").focus(function(){
    $(this).css("background-color", "yellow");
  });
  $("input").blur(function(){
    $(this).css("background-color", "green");
  });
});
```

```javascript
$(document).ready(function(){
  $("input").on({
    focus: function(){
      $(this).css("background-color", "yellow");
    },
    blur :function(){
      $(this).css("background-color", "green");
    }
  })
});
```

