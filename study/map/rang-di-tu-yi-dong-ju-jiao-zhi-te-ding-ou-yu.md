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

