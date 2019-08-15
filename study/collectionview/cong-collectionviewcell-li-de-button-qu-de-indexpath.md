# 從CollectionViewCell裡的button取得Indexpath

## 使用情景

在main `view`底下加一個`UITapGestureRecognizer`，目的是想要按空白處能夠讓鍵盤縮下來，但這樣會與`UICollectionViewDelegate`的`didSelectItemAt`方法有衝突。

EX：按下`CollectionView`的其中一個`Cell`沒有反應

## 暫時解決方式

`CollectionView`的`Cell`裡面塞一個`button`，這樣可以解決`cell`跟`UITapGestureRecognizer`優先權的問題，所以如果要取得`cell`的`indexPath`就可以使用以下方式：

```swift


@IBAction func cellBtnPressed(_ sender: Any) {
    if let location = (sender as? UIView)?.convert(CGPoint.zero, to:self.myCollectionView) {
        if let indexPath = self.myCollectionView.indexPathForItem(at: location) {
            print(" \(location), \(indexPath)")
        }
    }
}
```

未來找到新的解決方案再回頭修改吧～

