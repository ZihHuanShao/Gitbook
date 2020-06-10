# 字串String ↔ 時間Date

```swift
// Date轉換格式
Wednesday, Sep 12, 2018           --> EEEE, MMM d, yyyy
09/12/2018                        --> MM/dd/yyyy
09-12-2018 14:11                  --> MM-dd-yyyy HH:mm
Sep 12, 2:11 PM                   --> MMM d, h:mm a
September 2018                    --> MMMM yyyy
Sep 12, 2018                      --> MMM d, yyyy
Wed, 12 Sep 2018 14:11:54 +0000   --> E, d MMM yyyy HH:mm:ss Z
2018-09-12T14:11:54+0000          --> yyyy-MM-dd'T'HH:mm:ssZ
12.09.18                          --> dd.MM.yy
10:41:02.112                      --> HH:mm:ss.SSS
```

```swift
// String -> Date
// 注意：轉換的格式是有帶小數點的
func string2Date(_ string:String, dateFormat:String = "yyyy-MM-dd HH:mm:ss.SSS") -> Date {
    let formatter = DateFormatter()
    formatter.dateFormat = dateFormat
    let date = formatter.date(from: string)
    return date!
}

// Date -> String
// 注意：轉換的格式是有帶小數點的
func date2String(_ date:Date, dateFormat:String = "yyyy-MM-dd HH:mm:ss.SSS") -> String {
    let formatter = DateFormatter()
    formatter.dateFormat = dateFormat
    let date = formatter.string(from: date)
    return date
}

let time = "2019-08-21 08:38:58.133"
let dateFormat = string2Date(time)
print("dateFormat: ", dateFormat)

let strFormat = date2String(dateFormat)
print("strFormat: ", strFormat)
```

印出結果：

`dateFormat: 2019-08-21 08:38:58 +0000    
strFormat: 2019-08-21 08:38:58.133`

我轉的`time`字串有帶小數點，雖然轉成`date`格式，小數點不會顯示。但若再次將`date`格式轉回字串，可以發現仍然會保留小數點的值

### 計算時間差

```swift
    private func getTimeDifference(from dateTime1: String, to dateTime2: String) -> Int? {
        let dateFormatter = DateFormatter()
        dateFormatter.dateFormat = "yyyy-MM-dd HH:mm:ss"

        let date1 = dateFormatter.date(from: dateTime1)
        let date2 = dateFormatter.date(from: dateTime2)

        // 可以選擇計算時間差的其他格式, 因為我只需要知道兩時間之間的秒數, 所以只選擇.second
        // let components : NSCalendar.Unit = [.second, .minute, .hour, .day, .weekOfMonth, .month, .year]
        let components: NSCalendar.Unit = [.second]
        let difference = (Calendar.current as NSCalendar).components(components, from: date1!, to: date2!, options: [])

        print("difference: \(difference)")

        return difference.second
    }
```

印出的結果會根據所選擇的`components`格式而不同

## Ref.

{% embed url="https://www.hangge.com/blog/cache/detail\_2182.html" caption="" %}

{% embed url="https://stackoverflow.com/questions/35700281/date-format-in-swift" caption="Date格式" %}

{% embed url="https://www.itdaan.com/tw/8d0e3c01b30cff52c12e1055939ce305" caption="" %}

