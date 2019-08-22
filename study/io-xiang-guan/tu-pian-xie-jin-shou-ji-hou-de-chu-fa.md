# 圖片寫進手機後的觸發

範例：將圖片寫進手機相簿後觸警告視窗

```swift
    @IBAction func saveButtonPressed(_ sender: UIButton) {
        if let image = detailImageViews[pageControl.currentPage].image {
            UIImageWriteToSavedPhotosAlbum(image, self, #selector(self.imageSaveFinished(image:error:context:)), nil)
        }

    }
    
    @objc func imageSaveFinished(image: UIImage, error: Error, context: UnsafeRawPointer) {
        if error != nil { print(error) }
        
        let myAlert = UIAlertController(title: "Save successfully", message: "", preferredStyle: .alert)
        let okAction = UIAlertAction(title: "OK", style: .default)
        myAlert.addAction(okAction)
        present(myAlert, animated: true, completion: nil)

    }
```

