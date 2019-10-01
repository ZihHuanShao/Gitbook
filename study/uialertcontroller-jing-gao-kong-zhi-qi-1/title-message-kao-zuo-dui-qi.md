# title, message靠左對齊

```swift
    private func showDialMessage() {
        
        let alertController = createAlertController()

        let dialAction = UIAlertAction(title: "我要撥號", style: .default) {
            (UIAlertAction) in
        }
        let cancelAction = UIAlertAction(title: "取消", style: .default) {
            (UIAlertAction) in
            self.dismiss(animated: true, completion: nil)
        }
        alertController.addAction(dialAction)
        alertController.addAction(cancelAction)
        present(alertController, animated: true, completion: nil)
    }
    
    private func createAlertController() -> UIAlertController {
        let title = "撥打專線："
        let message = "\n0800-000-000\n" + "服務時間：週一至週日\n" + "８：30 ~ 21：00\n"
        
        let alertController = UIAlertController(title: title, message: message, preferredStyle: .alert)
        
        // 屬性設為靠左對齊
        let paragraphStyle = NSMutableParagraphStyle()
        paragraphStyle.alignment = .left
        
        // 設定title對齊
        let titleAttribute = NSMutableAttributedString (string: title, attributes: [NSAttributedString.Key.paragraphStyle: paragraphStyle])
        
        // 設定message對齊
        let messageAttribute = NSMutableAttributedString (string: message, attributes: [NSAttributedString.Key.paragraphStyle: paragraphStyle])
        
        alertController.setValue(titleAttribute, forKey: "attributedTitle")
        alertController.setValue(messageAttribute, forKey: "attributedMessage")
        
        return alertController
    }
```

