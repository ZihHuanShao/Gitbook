# Int64 ➜ Int

先將`Int64`轉為`NSString`字串，再透過底下的`intValue`方法取得`Int32`，再直接轉成`Int`即可

```swift
let sizeInt64: Int64 = getSize(atPath: absoluteFilePath)
let sizeInt32: Int32 = NSString(string: size64).intValue
let sizeInt = Int(size32)
```



