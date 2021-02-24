# 取得file檔案大小

* `path`: 檔案路徑

```swift
// 取得檔案大小(Bytes)
func getSize(atPath path: String) -> UInt64? {
    do {
        // METHOD 1
        let attr = try FileManager.default.attributesOfItem(atPath: path)
        let fileSize = attr[FileAttributeKey.size] as! UInt64
            
        /*
        // METHOD 2: Old way
        let dict = attr as NSDictionary
        fileSize = dict.fileSize()
         */
            
        return fileSize
   } catch {
        print("getSize Error: \(error)")
        return nil
    }
}

// 取得檔案格式
func covertToFileString(with size: UInt64) -> String {
    var convertedValue: Double = Double(size)
    var multiplyFactor = 0
    let tokens = ["bytes", "KB", "MB", "GB", "TB", "PB",  "EB",  "ZB", "YB"]
    while convertedValue > 1024 {
        convertedValue /= 1024
        multiplyFactor += 1
    }
    return String(format: "%4.2f %@", convertedValue, tokens[multiplyFactor])
}
```

