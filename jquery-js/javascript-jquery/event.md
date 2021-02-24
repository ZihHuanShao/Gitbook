# Event



## Ref.

### **事件捕獲 \(Event Capturing\)** & **事件冒泡 \(Event Bubbling\)？**

{% embed url="https://ithelp.ithome.com.tw/articles/10191970" caption="event機制" %}

### **`.click`**與 **`.on("click", ...)`**的差異

{% embed url="http://skaih.logdown.com/posts/712464-jquery-click-on-the-where-different" caption="JQ click & onclick" %}

{% embed url="https://blog.wu-boy.com/2012/04/use-on-api-to-attach-event-handlers-on-jquery/" %}



### `Event Handler`的隱藏參數`event`代表的意義

包含`this`與`event.currentTarget`的差別

{% embed url="https://ithelp.ithome.com.tw/articles/10192015" %}

### 其他類型的`event`

{% embed url="https://ithelp.ithome.com.tw/articles/10192175" %}

自訂事件\(`CustomEvent`\)範例：

```markup
<!DOCTYPE html>
<html>
<body>
    <div id="mydiv">press</div>
    <script>
        var mdiv = document.getElementById("mydiv");
        var eventName = "MY_EVENT";
        var myEvent = new CustomEvent(eventName,{detail:{data:"Hello myEvent"}});
            mdiv.addEventListener(eventName,function(evt){
                    console.log(evt.detail.data);
            });
        mydiv.onclick = function(){
            mydiv.dispatchEvent(myEvent);
        }
    </script>

</body>
</html>

```

