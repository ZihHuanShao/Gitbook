# 動態建立button within type, id, class, event

```javascript
$("div").append(
    $("<button></button>")
        .attr({
            type: "button",
            id: "GoAdminPageBtn",
            class: "btn btn-warning"
        })
        .text("前往管理頁面")
        .on("click", function () {
            location.href = "https://xxx.xxx";
        })
);
```

