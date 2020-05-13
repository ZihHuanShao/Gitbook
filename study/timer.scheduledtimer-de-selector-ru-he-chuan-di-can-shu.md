# Timer.scheduledTimer 的selector如何傳遞參數

宣告一全域`Timer`物件

```swift
// 全域
var timer: Timer!
```

透過`Timer`物件`timer`來接收

```swift
let data: String = "Hello world"
timer = Timer.scheduledTimer(timeInterval: 0.2, target: self, selector: (#selector(show(sender:))), userInfo: data, repeats: false)
```

再透過`timer.userInfo`來取得參數

```swift
@objc func show(sender: Timer) {
    if let data = timer.userInfo as? String {
        print(data)
    }
}
```



## Ref.

{% embed url="https://stackoverflow.com/questions/49436223/how-can-i-send-parameter-with-selector" %}



