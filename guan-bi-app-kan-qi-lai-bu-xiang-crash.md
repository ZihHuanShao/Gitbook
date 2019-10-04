# 關閉App看起來不像crash

```swift
 
 // home button pressed programmatically - to thorw app to background
 UIControl().sendAction(#selector(URLSessionTask.suspend), to: UIApplication.shared, for: nil)
 
 // terminaing app in background
 DispatchQueue.main.asyncAfter(deadline: .now() + .seconds(1), execute: {
  exit(EXIT_SUCCESS)
 })
 
```

## Ref.

{% embed url="https://gist.github.com/yoni-g/f6deb954ad31fef288662949bf7c9cbe" %}



