# JQ input radio之check, trigger

一般來說，會讓使用者選擇他想要的item，但若想透過程式碼來做到，選擇某個item並trigger相對應的事件函式，可參考如下：

假設我現在有個input radio的item，並有各自的事件函式要執行：

```javascript
// 假設我現在有個input radio的item，並有各自的事件函式要執行
'click input[type=radio][name=groupType]': function(event) {
	var thisView = this;
  
  // var $node = $(event.currentTarget);
  // console.log("group type: ", $node.val());
  // $node.val() 等於 $("input[type=radio][name=groupType]:checked"
	
	switch ($("input[type=radio][name=groupType]:checked").val()) {
		case "1": // 一般群組
			  thisView.listChatgroup(1, -1, -1, CGTYPE_NORMAL);
    		thisView.currentGroupType = CGTYPE_NORMAL;
    		break;

    case "3": // Sip會議室
			  thisView.listChatgroup(1, -1, -1, CGTYPE_SIPROOM);
    		thisView.currentGroupType = CGTYPE_SIPROOM;
    		break;

		case "2": // 無線電群組
			  thisView.listChatgroup(1, -1, -1, CGTYPE_RADIO);
    		thisView.currentGroupType = CGTYPE_RADIO;
    		break;  	
	}
}
```

現在被選擇的item是哪一個：  
`$("[name=fieldChatgroupType]:checked").val()`



先選擇到指定的item，再trigger

```javascript
// trigger item值為1的click事件
$("input[type=radio][name=groupType][value=1]").prop('checked',true).trigger("click");

// 若要動態執行相對應的事件, 可以用+號運算子連接
$("input[type=radio][name=groupType][value=" + currentGroupType + "]").prop('checked',true).trigger("click");
```



