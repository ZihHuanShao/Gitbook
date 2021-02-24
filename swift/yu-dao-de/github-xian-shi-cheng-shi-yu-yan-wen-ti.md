# github顯示程式語言問題

## 狀況

有時候明明專案是用swift語言寫的，顯示不是顯示swift而是顯示html

## 解決

專案根目錄新增一個**`.gitattributes`**檔案，並填入

```ruby
*.* linguist-language=Swift
```

![](../../.gitbook/assets/ying-mu-kuai-zhao-20191021-shang-wu-10.35.41.png)

![](../../.gitbook/assets/ying-mu-kuai-zhao-20191021-shang-wu-10.36.01.png)

![](../../.gitbook/assets/ying-mu-kuai-zhao-20191021-shang-wu-10.38.10.png)

## Ref.

{% embed url="https://jmln.tw/blog/2017-08-13-set-github-repo-lang.html" %}



