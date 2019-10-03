# 取得上下Safe area高度

```swift
var topSafeAreaHeight: CGFloat = 0
var bottomSafeAreaHeight: CGFloat = 0

  if #available(iOS 11.0, *) {
    let window = UIApplication.shared.windows[0]
    let safeFrame = window.safeAreaLayoutGuide.layoutFrame
    topSafeAreaHeight = safeFrame.minY
    bottomSafeAreaHeight = window.frame.maxY - safeFrame.maxY
  }
```

{% embed url="https://stackoverflow.com/questions/46829840/get-safe-area-inset-top-and-bottom-heights" %}



