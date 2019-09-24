# UIScrollView常用方法

```swift
    func scrollViewWillBeginDragging(_ scrollView: UIScrollView) {
        print("開始滑動") // show once
    }

    func scrollViewDidScroll(_ scrollView: UIScrollView) {
        print("滑動中")
    }

    func scrollViewDidEndDragging(_ scrollView: UIScrollView, willDecelerate decelerate: Bool) {
        print("結束滑動") // show once
    }

    func scrollViewWillBeginZooming(_ scrollView: UIScrollView, with view: UIView?) {
        print("開始縮放") // show once
    }

    func scrollViewDidZoom(_ scrollView: UIScrollView) {
        print("縮放中")
    }

    func scrollViewDidEndZooming(_ scrollView: UIScrollView, with view: UIView?, atScale scale: CGFloat) {
        print("結束縮放") // show once
    }
```

{% embed url="https://www.jianshu.com/p/237f29c56c46" caption="" %}

