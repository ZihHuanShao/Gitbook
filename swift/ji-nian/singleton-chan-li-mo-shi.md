# singleton: 單例模式

類別使用`static`變數，並搭配`private init()`，可以確保只能透過類別內部的`mgr`來生成類別實體，且**只有一個**`instance`。

```swift
class BroadcastMessageManager {
    static let mgr = BroadcastMessageManager()
    let syncQueue:DispatchQueue = DispatchQueue(label: "BroadcastMessageManager", attributes: [])

    private init() {       
    }
    
    ...
}
```

## 

## Ref.

{% embed url="https://medium.com/@mikru168/ios-singleton-單例-fcabe0710018" %}



