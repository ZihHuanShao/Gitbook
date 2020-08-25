# APNG

## Ref.

{% embed url="https://github.com/onevcat/APNGKit" %}

{% embed url="https://stackoverflow.com/questions/29844885/apng-inside-ios-app" %}

```swift
let image = APNGImage(named: "your_apng_image")
let imageView = APNGImageView(image: image)

imageView.startAnimating()

view.addSubview(imageView)
```

