# 如何進入背景模式 EX: Finite-Length Tasks



{% tabs %}
{% tab title="AppDelegate.swift" %}
```swift
@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {

    var backgroundTask: UIBackgroundTaskIdentifier = .invalid

    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // 註冊進入背景
        registerBackgroundTask()
        
        return true
    }

    ...

    func applicationWillTerminate(_ application: UIApplication) {
        // Called when the application is about to terminate. Save data if appropriate. See also applicationDidEnterBackground:.
        if backgroundTask != .invalid {
            endBackgroundTask()
        }
    }
}

extension AppDelegate {
    
    func registerBackgroundTask() {
        backgroundTask = UIApplication.shared.beginBackgroundTask { [weak self] in
            self?.endBackgroundTask()
            print("Background task start.")
        }
        assert(backgroundTask != .invalid)
    }
    
    func endBackgroundTask() {
        print("Background task ended.")
        UIApplication.shared.endBackgroundTask(backgroundTask)
        backgroundTask = .invalid
    }
}


```
{% endtab %}
{% endtabs %}

### Ref.

{% embed url="https://medium.com/@vin20777/background-modes-tutorial-getting-started-ios-%E8%83%8C%E6%99%AF%E4%BD%9C%E6%A5%AD%E7%B0%A1%E4%BB%8B-e028856bf98b" caption="背景模式簡介" %}

{% embed url="https://www.raywenderlich.com/5817-background-modes-tutorial-getting-started\#toc-anchor-004" %}



