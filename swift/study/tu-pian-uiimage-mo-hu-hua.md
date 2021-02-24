# 圖片\(UIImage\)模糊化

```swift
let defaultImage = UIImage(named: "sticker_contact.png")!
        

let inputImage =  CIImage(image: defaultImage)

//使用高斯模糊滤镜
let filter = CIFilter(name: "CIGaussianBlur")!
filter.setValue(inputImage, forKey:kCIInputImageKey)

//设置模糊半径值（越大越模糊）
filter.setValue(Float(5), forKey: kCIInputRadiusKey)

let outputCIImage = filter.outputImage!
let rect = CGRect(origin: CGPoint.zero, size: defaultImage.size)
let cgImage = CIContext(options: nil).createCGImage(outputCIImage, from: rect)
        
imageView.image = UIImage(cgImage: cgImage!)
```

## Ref.

{% embed url="https://www.hangge.com/blog/cache/detail\_1424.html" %}



