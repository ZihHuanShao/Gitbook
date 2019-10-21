# for-loop 建立高重複性的物件

建立程式碼高重複性的`click`物件可利用`for`迴圈替代

## 原始碼

```css
$("#add1").click(function(){
	var img = $("<img id='closeImg1' src='http://icons.iconarchive.com/icons/hopstarter/sleek-xp-software/16/Windows-Close-Program-icon.png'/>").attr({
		"width": '20',
		"height": '20'
		});
	var div 	  = $("<div></div>");		
	var div_img   = $("<div></div>").attr('id', 'removePannel');
	var div_title = $("<div></div>").text("醫護第1班");

	div.addClass('col-3 pannelUI');
	div_img.addClass('mr-auto');

	div_img.append(img)

	div.append(div_img);
	div.append(div_title);

	$("#pannel").append(div);
});	

$("#add2").click(function(){
	var img = $("<img id='closeImg1' src='http://icons.iconarchive.com/icons/hopstarter/sleek-xp-software/16/Windows-Close-Program-icon.png'/>").attr({
		"width": '20',
		"height": '20'
		});
	var div 	  = $("<div></div>");		
	var div_img   = $("<div></div>").attr('id', 'removePannel');
	var div_title = $("<div></div>").text("醫護第1班");

	div.addClass('col-3 pannelUI');
	div_img.addClass('mr-auto');

	div_img.append(img)

	div.append(div_img);
	div.append(div_title);

	$("#pannel").append(div);
});	

$("#add3").click(function(){
	var img = $("<img id='closeImg1' src='http://icons.iconarchive.com/icons/hopstarter/sleek-xp-software/16/Windows-Close-Program-icon.png'/>").attr({
		"width": '20',
		"height": '20'
		});
	var div 	  = $("<div></div>");		
	var div_img   = $("<div></div>").attr('id', 'removePannel');
	var div_title = $("<div></div>").text("醫護第3班");

	div.addClass('col-3 pannelUI');
	div_img.addClass('mr-auto');

	div_img.append(img)

	div.append(div_img);
	div.append(div_title);

	$("#pannel").append(div);
});	

$("#add4").click(function(){
	var img = $("<img id='closeImg1' src='http://icons.iconarchive.com/icons/hopstarter/sleek-xp-software/16/Windows-Close-Program-icon.png'/>").attr({
		"width": '20',
		"height": '20'
	});
	var div 	  = $("<div></div>");		
	var div_img   = $("<div></div>").attr('id', 'removePannel');
	var div_title = $("<div></div>").text("醫護第4班");

	div.addClass('col-3 pannelUI');
	div_img.addClass('mr-auto');

	div_img.append(img)

	div.append(div_img);
	div.append(div_title);

	$("#pannel").append(div);
});	
```

## 改善：for-loop

```css
for(let index = 1; index < 5; index++){
	console.log(index);
	$("#add" + index).click(function() {
		var img = $("<img id='closeImg1' src='http://icons.iconarchive.com/icons/hopstarter/sleek-xp-software/16/Windows-Close-Program-icon.png'/>").attr({
			"width": '20',
			"height": '20'
			});
		var div 	  = $("<div></div>");		
		var div_img   = $("<div></div>").attr('id', 'removePannel');
		var div_title = $("<div></div>").text("醫護第" + index + "班");

		div.addClass('col-3 pannelUI');
		div_img.addClass('mr-auto');

		div_img.append(img)

		div.append(div_img);
		div.append(div_title);

		$("#pannel").append(div);
		});
}
```

## Ref.

{% embed url="https://neohsuxoops.blogspot.com/2017/02/jqueryeachfor.html" %}



