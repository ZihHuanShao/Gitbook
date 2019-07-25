# UIImage上面加一個浮水印

```swift

let backgroundImage = UIImage(named: "backgroundImage.png")!
let watermarkImage = UIImage(named: "watermarkImage.png")!

// 浮水印的大小，這邊是相對於背景圖縮小3倍
let drawWatermarkWidth = backgroundImage.size.width / 3
let drawWatermarkHeight = backgroundImage.size.height / 3

// 畫浮水印的起點，x跟y，這裡讓它至於背景圖中心位置
let xStart = (backgroundImage.size.width - drawWatermarkWidth) / 2
let yStart = (backgroundImage.size.height - drawWatermarkHeight) / 2

UIGraphicsBeginImageContextWithOptions(backgroundImage.size, false, 0.0)
backgroundImage.draw(in: CGRect(x: 0.0, y: 0.0, width: backgroundImage.size.width, height: backgroundImage.size.height))
watermarkImage.draw(in: CGRect(x: xStart, y: yStart, width: drawWatermarkWidth, height: drawWatermarkHeight))

let result = UIGraphicsGetImageFromCurrentImageContext()
UIGraphicsEndImageContext()
self.imgaeView.image = result

```

{% embed url="https://stackoverflow.com/questions/35091137/how-can-i-add-a-watermark-to-an-image-using-this-code" %}



