# 顯示自訂的UIColor



```text
func UIColorFromRGB(rgbValue: UInt) -> UIColor {
    return UIColor(
        red: CGFloat((rgbValue & 0xFF0000) >> 16) / 255.0,
        green: CGFloat((rgbValue & 0x00FF00) >> 8) / 255.0,
        blue: CGFloat(rgbValue & 0x0000FF) / 255.0,
        alpha: CGFloat(1.0)
    )
}

view.backgroundColor = UIColorFromRGB(0xBD1E49)
```

## Ref.

{% embed url="https://stackoverflow.com/questions/24074257/how-can-i-use-uicolorfromrgb-in-swift" %}



