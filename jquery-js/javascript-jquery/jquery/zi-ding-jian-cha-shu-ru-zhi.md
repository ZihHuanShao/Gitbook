# 自訂檢查輸入值

```javascript
check_roleidValid: function(roleidStr) {
    var roleidValid = /^[a-zA-Z0-9\u002D\u002E\u005F]{1,50}$/
                
    if (roleidValid.test(roleidStr)) { /*符合格式*/ return true;}
    else { return false}
},
```

