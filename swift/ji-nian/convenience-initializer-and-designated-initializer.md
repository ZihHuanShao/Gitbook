# Convenience initializer & Designated Initializer

* **Designated Initializer**
  * Class的`init(a: Int)`，也就是我們一般所稱的建構式
* **Convenience initializer**
  * 同一個Class裡使用其他的**Designated Initializer**的建構式，但必須加上`convenience`關鍵字：比如我們建立一個`convenience init()`，然後裡面會再呼叫原本的`init(a: Int)`

```swift
class ColorTable {
    var color: String?
    
    // Designated Initializer
    init(color: String) {
        self.color = color
    }
    
    // Convenience initializer
    convenience init() {
        self.init(color: "Green")
    }
}
```

## Ref.

{% embed url="https://medium.com/@boshilee/swift-3-%E5%9F%BA%E7%A4%8E-class-part-3-aa1a096c3ab9" %}



