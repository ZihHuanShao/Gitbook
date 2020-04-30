# Hex String ↔ UInt

```swift
// Int -> Hex String

let rStr = String(format:"%02X", rgbColor.red)   // 255 -> "FF"
let gStr = String(format:"%02X", rgbColor.green) //  10 -> "0A"
let bStr = String(format:"%02X", rgbColor.blue)  //  11 -> "0B"

// Hex String -> UInt

let rUInt = UInt(rStr, radix: 16) // "FF" -> 255
let gUInt = UInt(gStr, radix: 16) // "0A" -> 10
let bUInt = UInt(bStr, radix: 16) // "0B" -> 11

// WRONG!!!
// Hex String -> UInt
// 邏輯錯誤!!!遇到非數字則會轉型失敗, 但就算是數字轉換後也是非預期結果
let rUInt = UInt(rStr) // "FF" -> nil
let gUInt = UInt(gStr) // "0A" -> nil
let bUInt = UInt(bStr) // "0B" -> nil

let testUInt = UInt("05") // "05" -> 05
let test2UInt = UInt("55") // "55" -> 55

```

## Ref.

{% embed url="https://stackoverflow.com/questions/41843262/convert-hex-color-as-string-to-uint" %}



