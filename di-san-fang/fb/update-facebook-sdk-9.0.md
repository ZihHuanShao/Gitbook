# Update Facebook SDK \(9.0\)

因登入的流程幾乎沒什麼變動，只要重新安裝，可以取得改版後相關的code即可

### 更新FB套件方式

[https://developers.facebook.com/docs/facebook-login/ios](https://developers.facebook.com/docs/facebook-login/ios)

1. **Cocoapods** 該方法在本專案的.xcworkspace project執行環境中，無法抓到改版後相關的code，故捨棄 
2. **Swift Package manager** iOS 11.2以上可使用該方法，本專案目前使用此方法

### FB原生按鈕

[https://developers.facebook.com/docs/facebook-login/limited-login/ios](https://developers.facebook.com/docs/facebook-login/limited-login/ios)

若有使用FB的按鈕，在建立時要再多設定一個屬性

```swift
loginButton.loginTracking = .limited
```

若使用`.limited`，允許的權限只有`email, public_profile, gaming_profile, gaming_user_picture`套用方式`EX: loginButton.permissions = ["public_profile"]`

### 驗證登入狀態

登入後，FB會回傳一個`token`來驗證登入狀態，取得方式可以透全域變數取得`AuthenticationToken.current?.tokenString` \(舊方式為`AccessToken.current?.tokenString`\)

另外，還有其他登入資訊可以取得：

```swift
let userID = Profile.current?.userID
let email = Profile.current?.email
```



