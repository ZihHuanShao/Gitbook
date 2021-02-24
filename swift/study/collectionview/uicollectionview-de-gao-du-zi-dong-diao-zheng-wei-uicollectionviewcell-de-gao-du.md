# UICollectionView的高度自動調整為UICollectionViewCell的高度

根據提供的方法步驟如下：

1. UI layout設定`CollectionView`的`height`限制
2. `height`的`priority`改成`999` \(這一步沒有特別設定，我預設為`1000)`
3. 新增`CollectionView`對齊底部\(`Bottom`\)的限制，更改`Relation`為`greater or equal` \(這一步沒有特別設定，我預設為`equal)`
4. 連結`height Constraints`到程式碼，命名為`heightConstraint`
5. 每次要load `CollectionView`時做以下事情:

```swift
CGFloat height = 設定你想要的Cell高度
heightConstraint.constant = height
```

{% embed url="https://stackoverflow.com/questions/42437966/how-to-adjust-height-of-uicollectionview-to-be-the-height-of-the-content-size-of" %}



