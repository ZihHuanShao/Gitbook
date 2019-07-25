# UIImage上面加一個浮水印

```swift
func getWatermarkImg(backgroundImage: UIImage, watermarkImage: UIImage) -> UIImage {
    
    // 選擇要在哪個圖上畫浮水印，這邊是選擇背景圖
    UIGraphicsBeginImageContextWithOptions(backgroundImage.size, false, 0.0)
            
    // 浮水印的大小，這邊是相對於背景圖縮小2倍
    let drawWidth  = backgroundImage.size.width / 2
    let drawHeight = backgroundImage.size.height / 2
            
    // 畫浮水印的起點，x跟y，這裡讓它至於背景圖中心位置
    let xStart     = (backgroundImage.size.width - drawWidth) / 2
    let yStart     = (backgroundImage.size.height - drawHeight) / 2
            
    backgroundImage.draw(in: CGRect(x: 0.0, y: 0.0, width: backgroundImage.size.width, height: backgroundImage.size.height))
    watermarkImage.draw(in: CGRect(x: xStart, y: yStart, width: drawWidth, height: drawHeight))
            
    let resultImg = UIGraphicsGetImageFromCurrentImageContext()
    UIGraphicsEndImageContext()
            
    return resultImg!
}

...

let watermarkImage = getWatermarkImg(backgroundImage: backgroundImg, watermarkImage: UIImage(named: "play.png")!)
self.imgaeView.image = watermarkImage
```

{% embed url="https://stackoverflow.com/questions/35091137/how-can-i-add-a-watermark-to-an-image-using-this-code" %}



