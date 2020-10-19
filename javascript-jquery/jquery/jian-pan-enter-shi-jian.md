# 鍵盤Enter事件

直接複製下面程式碼丟到[w3school](https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_hover)測試

```javascript
<!DOCTYPE html>

<html>
    <head>
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    </head>
    <body>
        <h1>Detect ENTER key with jQuery</h1>
        <label>TextBox Area: </label>
        <div id="someTextBox">
	        <input id="" type="text" size="40" />
            <input type="radio" name="tree_node_list">
        </div>
        
        <script type="text/javascript">
            //Bind keypress event to textbox
            $('#someTextBox').keypress(function(event){
                var keycode = (event.keyCode ? event.keyCode : event.which);
                if(keycode == '13'){
                    alert('You pressed a "enter" key in textbox');  
                }
                //Stop the event from propogation to other handlers
                //If this line will be removed, then keypress event handler attached 
                //at document level will also be triggered
                event.stopPropagation();
            });
             
            //Bind keypress event to document
            $(document).keypress(function(event){
                var keycode = (event.keyCode ? event.keyCode : event.which);
                if(keycode == '13'){
                    alert('You pressed a "enter" key in somewhere');    
                }
            });
        </script>
    </body>
</html>
```

## Ref.

{% embed url="https://howtodoinjava.com/jquery/jquery-detect-if-enter-key-is-pressed/" %}



