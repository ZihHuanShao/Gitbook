# 點擊Cell動態更新圖片及文字

`BottomCollectionViewCell`是我客製化的`UICollectionViewCell`

```swift
extension HomeViewController: UICollectionViewDelegate {
    func collectionView(_ collectionView: UICollectionView, didSelectItemAt indexPath: IndexPath) {
        if indexPath.row = 0 {
            // 使用cellForItem
            let cell = collectionView.cellForItem(at: indexPath as IndexPath)! as! BottomCollectionViewCell
            
            // 而不是使用dequeueReusableCell
            //let cell = collectionView.dequeueReusableCell(withReuseIdentifier: "BottomCollectionViewCell", for: indexPath) as! BottomCollectionViewCell

            cell.myImageView.image = UIImage(named: "A1")
            cell.myLabel.text = "hello world"
        }
    }
}
```

