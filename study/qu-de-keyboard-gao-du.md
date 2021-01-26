# 取得keyboard高度

使用原生系統提供的事件

```swift
NotificationCenter.default.addObserver(
    self,
    selector: #selector(keyboardWillShow),
    name: UIResponder.keyboardWillShowNotification,
    object: nil
)
```

## Ref.

{% embed url="https://stackoverflow.com/questions/31774006/how-to-get-height-of-keyboard" %}



