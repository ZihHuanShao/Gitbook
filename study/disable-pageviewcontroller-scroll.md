# Disable PageViewController scroll

```swift
// Disable Page Curl
for gesture in pageViewController!.gestureRecognizers {
    gesture.isEnabled = false
}

// Disable Scroll
for view in self.pageViewController!.view.subviews {
    if let subView = view as? UIScrollView {
        subView.scrollEnabled = false
    }
}
```

## Ref.

{% embed url="https://stackoverflow.com/questions/15829197/disable-enable-scrolling-in-uipageviewcontroller" %}

{% embed url="https://stackoverflow.com/questions/22098493/how-do-i-disable-the-swipe-gesture-of-uipageviewcontroller" %}



