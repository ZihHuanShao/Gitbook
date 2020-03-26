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



