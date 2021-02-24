# Share Extension介紹

## Extension介紹

### Extension？

為iOS提供的功能，讓APP之間能夠資料分享

### Extension有哪些類型？

常見的類型如下：

* **Today** Extension
* **Share** Extension
* **Action** Extension etc...

### Extension在App的角色定位？

* Extension是一個App的附加功能，因此，想要有extension功能，必須依附在一個主要的project App底下，而這個被依附的Project App稱之為**Containing app**
* Extension的存在會隨著App的安裝或移除決定

![Share Extension&#x5728;XCode&#x5DE5;&#x4F5C;&#x74B0;&#x5883;](https://github.com/ZihHuanShao/For-mkFile-Use/blob/master/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%202019-07-04%20%E4%B8%8A%E5%8D%8810.01.25.png?raw=true)



![APPLE&#x63D0;&#x4F9B;&#x7684;extension&#x67B6;&#x69CB;&#x5716;](../../../.gitbook/assets/detailed_communication_2x%20%282%29.png)

* **Host app**：user透過哪個app（可以是本機照片或本機檔案）分享檔案到我的app，而透過的這個app稱之
* **App extension**：由extension負責**接收**從Host app傳進來的檔案
* **Containing app**：主要開發的project app，負責將資料如何對外呈現
* **Shared resources**：extension與Containing app透過蘋果提供的一個group space，透過這個space來讓Containing app存取extension所接收到的**當**

## Share Extension介紹

### 使用情景

一般使用的情況會是使用者想要分享網頁文章或照片到FB、IG上，而開發者就是透過自己定義Share Extension功能，讓使用者也能過分享到自己定義的APP上

### 決定Share Extension出現在分享清單中的關鍵

![](../../../.gitbook/assets/img_2205.PNG)

圖中就是share extension功能所呈現的畫面，而**ShareExtension**則是我開發share extension取的名字，當然你也可以自行取名。如果是以最上面第一張圖來看的話，這邊呈現的名稱就會是**hostShareExt**

要讓share extension出現在分享畫面的話，就要看APP允許接受什麼類型的內容，可選擇支援類型如下：

* 可經由share extension自己目錄底下`plist`檔，調整欄位**NSExtension** ➔ **NSExtensionAttributes** 改為**Dictionary** Type ➔ 新增下列欲選取的`key`
  * `NSExtensionActivationSupportsAttachmentsWithMaxCount`
  * `NSExtensionActivationSupportsAttachmentsWithMinCount`
  * `NSExtensionActivationSupportsFileWithMaxCount`
  * `NSExtensionActivationSupportsImageWithMaxCount`
  * `NSExtensionActivationSupportsMovieWithMaxCount`
  * `NSExtensionActivationSupportsText` 
  * `NSExtensionActivationSupportsWebURLWithMaxCount`
  * `NSExtensionActivationSupportsWebPageWithMaxCount`

![](../../../.gitbook/assets/ying-mu-kuai-zhao-20190715-xia-wu-3.35.24.png)

* 例如：若我只想允許接收分享**網頁連結**的類型，就只新增`NSExtensionActivationSupportsWebURLWithMaxCount`屬性並設定其數量
* `NSExtensionActivationSupportsAttachmentsWithMaxCount`：附件最多數量限制。附件類型包括File、Image、movie，可以單一、可以複選，但總數量不得超過指定數量

### 提供的預設介面

會有一個預設畫面、一個**Cancel**按鈕、一個**Post**按鈕 ![](https://github.com/ZihHuanShao/For-mkFile-Use/blob/master/shareExt_default.png?raw=true)



### 提供的實作方式

一開始主要提供基本的三個函式讓我們實作：

* `isContentValid`
* `didSelectPost`
* `configurationItems`

![](../../../.gitbook/assets/ying-mu-kuai-zhao-20190715-xia-wu-3.49.47.png)



### **extension收到檔案後，如何傳給Containing App？**

蘋果提供一項叫**App Groups**的服務，允許開發者能夠在自己的App之間傳遞資料，可透過下列三種方式

* `UserDefaults`
* `FileManager`
* `CoreData`

因此，開發者使用哪個指令操作，取資料就需要鍵值或路徑，而這個相對於在APP Group服務底下稱為group name，這也是開發者可以自行定義的

## 建立與啟用App Group

建立Target

![](../../../.gitbook/assets/ying-mu-kuai-zhao-20190711-shang-wu-10.18.05.png)

選擇Share Extension

![](../../../.gitbook/assets/ying-mu-kuai-zhao-20190711-shang-wu-10.18.24.png)

建立完後，到Project的左側欄位，選擇**Capabilities**，開啟**App Group**功能，Container App（EX: **ShareExtensionTest**）與extension端（EX: **ShareExtension**）都要啟用。

![](https://github.com/ZihHuanShao/For-mkFile-Use/blob/master/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%202019-07-11%20%E4%B8%8A%E5%8D%889.34.37.png?raw=true)

點選+號，新增自己的group name

![](https://github.com/ZihHuanShao/For-mkFile-Use/blob/master/%E8%9E%A2%E5%B9%95%E5%BF%AB%E7%85%A7%202019-07-11%20%E4%B8%8A%E5%8D%889.36.38.png?raw=true)

{% hint style="info" %}
取名建議：結尾名稱跟ContainerApp名稱一致，如：`group.XXX.XXX.yourContainerAppName`，否則可能會有未知的錯誤
{% endhint %}

完成，可以看到XCode工作環境會多一層extension端的目錄。

