# 取得現在時間\(TW\) GMT +8

```swift
// 取得時區名
print(TimeZone.current.identifier)

// 
print(TimeZone.current.abbreviation())

// 取得GMT偏移秒数
print(TimeZone.current.secondsFromGMT())
```

輸出：（有可能因為所在地或電腦設定而不同）

`"Asia/Taipei"`  
`GMT+8  
28800`

```swift
let date: Date = Date()
// 當前時間
print(date)

let dateFormatter: DateFormatter = DateFormatter()
dateFormatter.dateFormat = "yyyy/MM/dd HH:mm:ss.SSS"
dateFormatter.locale = Locale(identifier: "zh_Hant_TW") // 設定地區(台灣)
dateFormatter.timeZone = TimeZone(identifier: "Asia/Taipei") // 設定時區(台灣)
dateFormatter.timeZone = TimeZone(secondsFromGMT: +28800)

// 轉成台灣時間
print(dateFormatter.string(from: date))

```

輸出：

`2019-09-05 08:09:31 +0000  
2019/09/05 16:09:31.726`

