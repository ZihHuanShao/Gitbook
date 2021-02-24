# View橫跨SplitViewController

{% code title="AppDelegate.swift" %}
```swift
class AppDelegate: UIResponder, UIApplicationDelegate {
    
    var splitView: UISplitViewController?
}

extension AppDelegate {
    func showOverlay() {
        // grab a screenshot
        let screenshot = grabScreenshot()

        
        // create a new view controller with it
        let underlay = UIViewController.init()
        let background = UIImageView.init(image: screenshot)
        underlay.view = background
        
        // grab the overlay controller
        let storyboard = UIStoryboard(name: STORYBOARD_NAME_GROUP, bundle: nil)
        let overlay = storyboard.instantiateViewController(withIdentifier: "Overlay")
        
        overlay.modalPresentationStyle = .formSheet
        
        // swap the split view
        
        splitView = window?.rootViewController as? UISplitViewController
        window?.rootViewController = underlay
       
        
        // present the overlay
        underlay.present(overlay, animated: true, completion: nil)
    }
    
    func dismissOverlay() {
        
        // dismiss the overlay
        window?.rootViewController?.dismiss(animated: true, completion: {
            self.window?.rootViewController = self.splitView
        })
    }
}

```
{% endcode %}

```swift
// 要呼叫彈出的ViewController

// 按下button呼叫彈出的ViewController
@IBAction func createGroupButtonPressed(_ sender: UIButton) {

        // wait a moment before taking the screenshot
        let _ = Timer.scheduledTimer(
                  timeInterval: 0.2, 
                  target: self, 
                  selector: #selector(showOverlayDelayed), 
                  userInfo: nil, 
                  repeats: false
                  )
}

@objc func showOverlayDelayed() {
        let appDelegate = UIApplication.shared.delegate as? AppDelegate
        appDelegate?.showOverlay()
    }
```

```swift
// 彈出的ViewController

// 按下button返回
@IBAction func finishButtonPressed(_ sender: UIButton) {
        let appDelegate = UIApplication.shared.delegate as? AppDelegate
        appDelegate?.dismissOverlay()
}
```

## Ref.

{% embed url="https://pinkstone.co.uk/how-to-present-a-view-controller-on-top-of-a-uisplitview-controller/" caption="Part 1" %}

{% embed url="https://pinkstone.co.uk/how-to-present-a-view-controller-on-top-of-a-uisplitview-controller-part-2/" caption="Part 2" %}



