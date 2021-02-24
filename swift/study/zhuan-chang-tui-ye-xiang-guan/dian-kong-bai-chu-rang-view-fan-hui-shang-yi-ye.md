# 點空白處讓View返回上一頁

```swift
let tap: UITapGestureRecognizer = UITapGestureRecognizer(target: self, action: #selector(dismissView))
self.view.addGestureRecognizer(tap)


@objc func dismissView() {
        willMove(toParentViewController: nil)
        removeFromParentViewController()
        view.removeFromSuperview()
    }
```

