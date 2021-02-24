# 移除containerView的subViews

```swift
// METHOD 1
for view in containerView.subviews {
    view.removeFromSuperview()
}

// METHOD 2
containerView.subviews.forEach({ $0.removeFromSuperview() }) // this gets things done

// METHOD 3
containerView.subviews.map({ $0.removeFromSuperview() }) // this returns modified array
```

## Ref.

{% embed url="https://stackoverflow.com/questions/24312760/how-to-remove-all-subviews-of-a-view-in-swift" %}



