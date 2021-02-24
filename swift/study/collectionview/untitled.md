# 點擊cell變色

```swift
class ViewController: UICollectionViewCell {

    // 點擊當下呈現的顏色
    override var isHighlighted: Bool {
            didSet {
                itemBgView.backgroundColor = isHighlighted ? .red : .clear
            }
        }
    }
    
    // 點擊完後呈現的顏色
    override var isSelected: Bool {
            didSet {
                itemBgView.backgroundColor = isSelected ? .red : .clear
            }
        }
    }
}
```

