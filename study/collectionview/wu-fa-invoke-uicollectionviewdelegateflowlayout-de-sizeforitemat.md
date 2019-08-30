# 無法invoke UICollectionViewDelegateFlowLayout的sizeForItemAt

`UICollectionViewDataSource Protocol`的**`numberOfItemsInSection`** `method`若`return 0`，則不會觸發`UICollectionViewDelegateFlowLayout`的`sizeForItemAt method，所以如果要判斷為0的這個case，必須要提前在UICollectionViewDataSource Protocol`的**`numberOfItemsInSection`** `method`做處理。

\`\`

