---
description: 透過程式碼來設定UI元件的auto layout
---

# NSLayoutConstraint參數說明

```swift
// Function Prototype
NSLayoutConstraint(
    // 要約束的物件，可以是button、label、image view等等
    item: Any,

    // 要對約束物件的屬性進行設定，屬性包括如leading、trailing、top、centerX等等
    attribute: NSLayoutConstraint.Attribute, 

    // 兩個attribute之間的關係，如.equal、.greaterThanOrEqual、lessThanOrEqual等等
    relatedBy: NSLayoutConstraint.Relation,

    // 約束物件的參考物件(也可以想成：約束對象相對於參考物件的位置)，可以是button、label、image view等等
    toItem: Any, 

    // 參考物件的屬性，屬性包括如leading、trailing、top、centerX等等
    attribute: SLayoutConstraint.Attribute, 

    // multiplier與後者attribute相乘積，加上constant值，再指定給約束對象
    // 線性關係(y = mx + c)：item = multiplier * attribute + constant
    // 讓約束對象做一個線性的操作(如果運用在可以滑動的頁面，會造成動畫效果)
    multiplier: CGFloat, 

    // 相對於toItem的偏移量
    constant: CGFloat
)


// Example1：myButton的中央X軸位置，會對齊相對於myImageView的左邊起始位置
NSLayoutConstraint(
    item:       myButton,
    attribute:  .CenterX, 
    relatedBy:  .equal,
    toItem:     myImageView,
    attribute:  .leading, 
    multiplier: 1.0, 
    constant:   0
)

// Example2：myButton左邊的起始位置，會對齊相對於myImageView的左邊起始位置，置於一個view的寬度大小再加上往右邊偏移10個單位的位置
NSLayoutConstraint(
    item:       myButton,
    attribute:  .leading, 
    relatedBy:  .equal,
    toItem:     myImageView,
    attribute:  .leading, 
    multiplier: 1.0, 
    constant:   myImageView.frame.width + 10
)

// Example3：設定約束物件本身的size
// toItem與attribute設為nil及.notAnAttribute
// 此例是將myButton的寬度設為200
NSLayoutConstraint(
    item:       myButton,
    attribute:  .width, 
    relatedBy:  .equal,
    toItem:     nil,, 
    attribute:  .notAnAttribute, 
    multiplier: 1.0, 
    constant:   200
)

// Example4：multiplier數值的套用效果，newImageView左邊的起始位置，會對齊相對於myImageView的左邊起始位置，置於一個view的寬度大小後的位置
// 效果可以參考下面附檔
NSLayoutConstraint(
    item:       newImageView,
    attribute:  .leading, 
    relatedBy:  .equal,
    toItem:     myImageView,, 
    attribute:  .leading, 
    multiplier: 2.0, 
    constant:   myImageView
)
```

Example4 效果：

{% file src="../.gitbook/assets/rpreplay\_final1565916472.mp4" %}

## Ref.

{% embed url="https://medium.com/@denkeni/%E7%B4%94%E7%A8%8B%E5%BC%8F%E7%A2%BC-auto-layout-%E8%88%87%E6%A6%82%E8%A6%81%E6%95%99%E5%AD%B8-%E4%B8%80-6077dd73dd3f" caption="" %}

{% embed url="https://www.appcoda.com.tw/auto-layout-programmatically/" caption="" %}

{% embed url="https://shenfive.pixnet.net/blog/post/58766426-autolayout-%282%29-%E6%89%8B%E5%8B%95%E5%BB%BA%E7%AB%8B-nslayoutconstraint" caption="" %}

## Ref. for using

{% embed url="https://stackoverflow.com/questions/26180822/how-to-add-constraints-programmatically-using-swift" caption="" %}

