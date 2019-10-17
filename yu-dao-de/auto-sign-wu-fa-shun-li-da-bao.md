# auto sign無法順利打包

當案子一切就緒準備打包\(Archive\)上架時，使用`Automatically manage singing`時卻遇到下面狀況：

![](../.gitbook/assets/ying-mu-kuai-zhao-20191017-shang-wu-10.41.00.png)

![](../.gitbook/assets/ying-mu-kuai-zhao-20191016-xia-wu-4.11.03.png)

## 解決方法

改由手動建立sign所需要的檔案\(**開發憑證**與**發布憑證**\)

![](../.gitbook/assets/ying-mu-kuai-zhao-20191017-shang-wu-10.45.56.png)

![&#x78BA;&#x8A8D;&#x9019;&#x88E1;&#x7684;IDENTIFIER&#x8981;&#x8207;&#x5C08;&#x6848;&#x7684;Bundle ID&#x4E00;&#x81F4;](../.gitbook/assets/ying-mu-kuai-zhao-20191017-shang-wu-10.47.00.png)

![&#x65B0;&#x589E;&#x6191;&#x8B49;](../.gitbook/assets/ying-mu-kuai-zhao-20191017-shang-wu-10.56.28.png)

![](../.gitbook/assets/ying-mu-kuai-zhao-20191017-shang-wu-10.47.41.png)

這邊為了方便，直接在圖上標註要新增兩個檔，但實際上這邊一次只能建立一個檔案，所以這裡要操作兩次。



![&#x5EFA;&#x7ACB;&#x5B8C;&#x6210;](../.gitbook/assets/ying-mu-kuai-zhao-20191017-shang-wu-10.50.08.png)

這邊建立完成之後，下載這兩個檔案，下載好之後再分別點擊兩下，XCode會自動去偵測並更新有哪些可用的憑證，此時可以在XCode直接選擇要套用的憑證，之後再重新一次打包流程即可

![](../.gitbook/assets/ying-mu-kuai-zhao-20191017-shang-wu-10.40.37.png)



















