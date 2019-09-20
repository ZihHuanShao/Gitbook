# UITextView 調整文字行距

```swift
let str = "ABCD\n" + "EFGH\n" + "IJKL\n"

let paraph = NSMutableParagraphStyle()
paraph.lineSpacing = 40
let attributes = [NSAttributedString.Key.font:UIFont.systemFont(ofSize: 15), NSAttributedString.Key.paragraphStyle: paraph]
            
contentTextView.attributedText = NSAttributedString(string: str, attributes: attributes)
```

## Ref.

{% embed url="https://blog.csdn.net/mo\_xiao\_mo/article/details/60954036" %}



