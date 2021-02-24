# 讓地圖移動聚焦至特定區域

```swift
    private func focusOnElectrFence(coordinates: [CLLocationCoordinate2D]) {
       
        path = GMSMutablePath()
        for coordinate in coordinates {
            path.add(coordinate)
        }
        var bounds: GMSCoordinateBounds = GMSCoordinateBounds()
        for index in 0 ..< path.count() {
            bounds = bounds.includingCoordinate(path.coordinate(at: index))
        }
        
        mapView.animate(with: GMSCameraUpdate.fit(bounds))
        mapView.animate(toZoom: 15)
    }
```

## Ref.

{% embed url="https://medium.com/@mikru168/ios-%E4%BD%BF%E7%94%A8-google-map-sdk-%E6%88%96-google-map-app-deep-link-%E4%BE%86%E9%81%94%E5%88%B0%E7%B9%AA%E8%A3%BD%E5%9C%B0%E5%9C%96%E7%9A%84%E6%95%88%E6%9E%9C-b2efd56b3d6f" %}



