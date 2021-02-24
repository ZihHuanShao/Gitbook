# 取得sandbox底下的video檔

  
切記！！  
要拿到video檔案的位置，必須使用`URL(fileURLWithPath: String)`而不是`URL(string: String)`，要播放video需要有`file:///`前贅字的`url`

```swift
(lldb) po URL(fileURLWithPath: filePath)
  - _url : file:///var/mobile/Containers/Data/Application/D47C7DA3-1FA8-44D7-8F03-58B1EFE24E77/Documents/small.mp4

(lldb) po URL(string: filePath)
    - _url : /var/mobile/Containers/Data/Application/D47C7DA3-1FA8-44D7-8F03-58B1EFE24E77/Documents/small.mp4
```



```swift
let fileName = url.lastPathComponent

// 先取得Document資料夾的位置，再加上檔名
let filePath = NSHomeDirectory() + "/Documents/" + fileName

// 務必要使用URL(fileURLWithPath: String)
let video = URL(fileURLWithPath: filePath)
```

