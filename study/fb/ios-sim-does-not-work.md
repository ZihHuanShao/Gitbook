# ios-sim does not work

在FB的應用程式審核步驟跑`ios-sim`指令會沒有反應, 網路上找到有人提供其他指令可以work, 如下

1. `sudo npm install -g ios-sim`
2. `ios-sim launch YourApp.app --devicetypeid iPhone-5s`
   * `YourApp.app`: 替換成自己的app檔    
   * `iPhone-5s`: 替換成要要測試的機型. Ex:`iPhone-8`

## `Ref.`

{% embed url="https://github.com/ios-control/ios-sim/issues/196" %}

\`\`

