# ScrollView移動至起始位置

```swift
// 設定一開啟畫面，畫面就移到動第5張照片(因為起始位置是在四張照片的寬度之後)的位置
myScrollView.setContentOffset(CGPoint(x: view.frame.width * 4, y: 0), animated: true)

```

## Ref.

{% embed url="https://gist.github.com/pocketkk/909abd3ae4ba4b5f8352" %}



