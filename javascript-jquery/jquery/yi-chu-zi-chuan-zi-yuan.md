# 移除字串字元

```javascript
var uList = params.userformlist;
var uListDesc = "";
for (var i = 0; i < uList.length; i++) {
    if      ("0" == uList[i]) { uListDesc = uListDesc + "app, "; } 
    else if ("1" == uList[i]) { uListDesc = uListDesc + "gw, "; } 
    else if ("2" == uList[i]) { uListDesc = uListDesc + "radio, "; }   
}
uListDesc = uListDesc.substring(0, uListDesc.length - 2); // 移除最後兩個字元', '

// Resault: app, gw, radio
```

