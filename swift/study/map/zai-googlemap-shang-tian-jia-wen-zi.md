# 在googleMap上添加文字

```swift
// EX: 假設現在我有一個多邊形, 我要讓文字在多邊形最北邊的點的上方顯示

// 存放緯度的陣列, 用來找到最北點, 要擺放文字
var latitudes = [CLLocationDegrees]()   

for coordinate in coordinates {
    latitudes.append(coordinate.latitude)
}

// 最大值表緯度最高(北)
let northernmostLat = latitudes.max()  

// 緯度最高(北)的座標
var northernmostCoord: CLLocationCoordinate2D?  

for coordinate in coordinates {
    if northernmostLat == coordinate.latitude {
        northernmostCoord = coordinate
    }
}

if let nCoord = northernmostCoord {
    let overlay = GMSGroundOverlay(position: nCoord, icon: newImage(text: "這是一個多邊形", size: CGSize(width: 100, height: 100)), zoomLevel: 15)    
    overlay.bearing = 0
    overlay.map = mapView
}


// Updated Swift version (參考範例太舊, 已更新)

func newImage(text: String?, size: CGSize) -> UIImage? {

    let data = text?.data(using: String.Encoding.utf8, allowLossyConversion: true)
    let drawText = NSString(data: data!, encoding: String.Encoding.utf8.rawValue)

    let textFontAttributes = [
        NSAttributedString.Key.font: UIFont(name: "Helvetica Bold", size: 20)!,
        NSAttributedString.Key.foregroundColor: UIColor.red,
    ]

    UIGraphicsBeginImageContextWithOptions(size, false, 0)
    drawText?.draw(in: CGRect(x: 0, y: 0, width: size.width, height: size.height), withAttributes: textFontAttributes)
        
    let newImage = UIGraphicsGetImageFromCurrentImageContext()
    UIGraphicsEndImageContext()

    return newImage
}
```

## Ref.

{% embed url="https://stackoverflow.com/questions/33505355/add-a-text-label-to-a-polygon-in-google-maps-for-ios-swift" %}



