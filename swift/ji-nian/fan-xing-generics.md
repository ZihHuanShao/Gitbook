# 泛型 Generics

泛型共分為五個部分：

1. Generic Functions 
2. Generic types
3. Type Constraint
4. Associated Types
5. Generic Where Clause

Generic Functions範例

```swift
import Foundation

class AppleIPhone7 {}
class SamsungNote7 {}
class AsusZenfone {}

protocol Chargeable {}      // 可充電的
protocol HeadphoneJack {}   // 有 Headphone Jack 的

extension AppleIPhone7: Chargeable {}
extension SamsungNote7: HeadphoneJack {}
extension AsusZenfone: Chargeable, HeadphoneJack {}

func charge<Phone: Chargeable>(phone: Phone) {
  print("\(type(of: phone)) is charging")
}

func listenMusic<Phone: HeadphoneJack>(phone: Phone) {
  print("Listen music with \(type(of: phone))")
}

func listenMusicWhileCharging<Phone: Chargeable & HeadphoneJack>(phone: Phone) {
  print("Listen music with \(type(of: phone)) while charging")
}


let iphone7 = AppleIPhone7()
let note7 = SamsungNote7()
let zenfone = AsusZenfone()

// charge(phone: zenfone)
charge(phone: iphone7)
// charge(phone: note7)

// listenMusic(phone: zenfone)
// listenMusic(phone: iphone7)
// listenMusic(phone: note7)

// listenMusicWhileCharging(phone: zenfone)
// listenMusicWhileCharging(phone: iphone7)
// listenMusicWhileCharging(phone: note7)
```

## Ref.

{% embed url="https://medium.com/@apppeterpan/%E5%B9%AB%E5%8A%A9-protocol-%E5%AF%A6%E7%8F%BE%E5%9E%8B%E5%88%A5%E4%BB%A3%E8%99%9F%E7%9A%84-associated-type-44cb2d25952e" caption="Associated Type範例" %}

{% embed url="https://medium.com/@jerrywang0420/generic-%E6%B3%9B%E5%9E%8B%E6%95%99%E5%AD%B8-swift-3-ios-8754dd835b39" caption="Generic 泛型教學" %}

{% embed url="https://weihanglo.tw/posts/2017/swift-generics/" caption="理解 Swift Generics" %}



