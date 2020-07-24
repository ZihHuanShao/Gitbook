# 設定特定方位的圓角

```swift
    /**
     設定view的圓角: 符合iOS 11以下版本
     */
    private func roundCorners(view: UIView, cornerRadius: Double) {
        let path = UIBezierPath(
            roundedRect: view.bounds,
            byRoundingCorners: [.topLeft, .topRight], // 只設定左上角與右上角
            cornerRadii: CGSize(width: cornerRadius, height: cornerRadius)
        )

        let maskLayer = CAShapeLayer()
        maskLayer.frame = self.view.bounds
        maskLayer.path = path.cgPath
        self.view.layer.mask = maskLayer
    }
```

## Ref.

{% embed url="https://www.appcoda.com.tw/rounded-corners-uiview/" %}



