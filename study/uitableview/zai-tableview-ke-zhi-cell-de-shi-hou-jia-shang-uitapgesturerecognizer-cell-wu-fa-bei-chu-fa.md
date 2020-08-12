# 在TableView客製cell的時候加上UITapGestureRecognizer, cell無法被觸發

加入手勢會影響到點擊cell無法被trigger。

對`UITapGestureRecognizer`的`cancelsTouchesInView`屬性設`false`即可解決此問題

```swift
let tap = UITapGestureRecognizer(target: self, action: #selector(dismissKeyBoard))
// set property to false
tap.cancelsTouchesInView = false
self.view.addGestureRecognizer(tap)
```

## Ref.

{% embed url="https://stackoverflow.com/questions/17684019/uitableview-on-a-uiview-with-uitapgesturerecognizer-cell-selection-doesnt-work" %}

{% embed url="https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E6%95%99%E5%AE%A4/uitableview%E5%92%8Ctap%E6%89%8B%E5%8B%A2%E8%A1%9D%E7%AA%81%E7%9A%84%E5%95%8F%E9%A1%8C-15a5bbce996e" %}



