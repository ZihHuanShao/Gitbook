# timer傳值

```swift
let timer = Timer.scheduledTimer(timeInterval: 1.0, target: self, selector: #selector(fire(timer:)), userInfo: ["score": 10], repeats: true)

@objc func fire(timer: Timer) 
{
    if  let userInfo = timer.userInfo as? [String: Int],
        let score = userInfo["score"] {

        print("You scored \(score) points!")
    }
}
```

## Ref.

{% embed url="https://learnappmaking.com/timer-swift-how-to/" %}



