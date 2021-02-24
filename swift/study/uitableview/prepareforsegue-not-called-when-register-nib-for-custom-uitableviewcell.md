# prepareForSegue not called when register nib for custom UITableViewCell

因為`prepareforsegue`只運行在原生的`TableViewCell`上, 所以只要透過registe nib註冊客製化的`tableViewCell`, 那麼`prepareforsegue`就不會被呼叫到.

### 解決方法

使用delegate

## Ref.

{% embed url="https://stackoverflow.com/questions/28741734/prepareforsegue-not-called-when-load-and-register-nib-for-custom-uitableviewcell" %}

{% embed url="https://stackoverflow.com/questions/39234792/prepareforsegue-out-of-custom-uitableviewcell" caption="use delegate" %}





