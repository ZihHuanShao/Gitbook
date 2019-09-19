# JS function method

### **`arguments`**

取得`function`傳進來的**參數陣列**，比如傳進來`function`有三個參數，則`arguments`為包含三個元素的陣列

```javascript
function sum() {
    vat total = 0;
    for (var i = 0; i < arguments.length; i++) {
        total += arguments[i];
    }
    return total;
}

document.write(sum());
document.write(sum(1,2));
document.write(sum(1,2,3,4,5,6,7,8,9,10));
```

### **`callee`**

為`arguments`的屬性之一，可以取得被呼叫的`function`本身

* **`callee.caller`**
  * 被呼叫`function`本身的`Object`
* 
### `length`

* **`arguments.length`**
  * 取得`function`**宣告**的參數長度\(`function`本體宣告幾個參數\)
* **`arguments.callee.length`**
  * 取得 `function`**實際**參數長度\(呼叫方看傳入幾個參數\)

### `call`/ `apply`/ `bind`

`apply`與`call`兩者功能相同，皆是回傳`function`執行結果，都可以指定被呼叫`function`中的`this`變數。差別只在於傳入參數的寫法不同。

* **call**
  * `apply(某個Object的this, 參數1, 參數2, ... );` 
* **apply**
* * `call(某個Object的this, [參數1, 參數2] );`
* **bind**
  * 回傳的是綁定 `this` 後的**原函數**



EXAMPLE 1

```javascript
<script>

function methodA(p1, p2, p3) {
  document.write('========================' + '<br>');
  document.write("arguments: " + arguments + '<br>');
  document.write("arguments.callee: " + arguments.callee + '<br>');
  document.write("arguments.callee.caller: " + arguments.callee.caller + '<br>');
  document.write('宣告參數長度: '+ arguments.callee.length + '<br>');
  document.write('實際參數長度: '+ arguments.length + '<br>');
  document.write('this: ' + this + '<br>');
  document.write('p1: ' + p1 + '<br>');
  document.write('p2: ' + p2 + '<br>');
  document.write('p3: ' + p3 + '<br>');
}

function handleCaller() {
	methodA('xxx', 'yyy');
    document.write('<br>');
	methodA.apply(handleCaller, ['xxx', 'yyy']);
}

function init() {
  handleCaller();
  document.write('<br>');
  methodA.call(handleCaller, 'xxx', 'yyy');
}

init();

</script>
```

印出：

```text
========================
arguments: [object Arguments]
arguments.callee: 
	function methodA(p1, p2, p3) { 
		document.write('========================' + ''); 
		document.write("arguments: " + arguments + ''); 
		document.write("arguments.callee: " + arguments.callee + ''); 
		document.write("arguments.callee.caller: " + arguments.callee.caller + ''); 
		document.write( '宣告參數長度: '+arguments.callee.length + ''); 
		document.write( '實際參數長度: '+arguments.length + ''); 
		document.write( 'this: ' + this + ''); 
		document.write( 'p1: ' + p1 + ''); 
		document.write( 'p2: ' + p2 + ''); 
		document.write( 'p3: ' + p3 + ''); 
	}
arguments.callee.caller: 
	function handleCaller() { methodA('xxx', 'yyy'); 
		document.write(""); 
		methodA.apply(handleCaller,	['xxx', 'yyy']);
	}
宣告參數長度: 3
實際參數長度: 2
this: [object Window]
p1: xxx
p2: yyy
p3: undefined

========================
arguments: [object Arguments]
arguments.callee: 
	function methodA(p1, p2, p3) {
		document.write('========================' + ''); 
		document.write("arguments: " + arguments + '');
		document.write("arguments.callee: " + arguments.callee + ''); 
		document.write("arguments.callee.caller: " + arguments.callee.caller + '');
		document.write( '宣告參數長度: ' + arguments.callee.length + '');
		document.write( '實際參數長度: ' + arguments.length + ''); 
		document.write( 'this: ' + this + ''); 
		document.write( 'p1: ' + p1 + ''); 
		document.write( 'p2: ' + p2 + ''); 
		document.write( 'p3: ' + p3  + ''); 
	}
arguments.callee.caller: 
	function handleCaller() { 
	methodA('xxx', 'yyy'); 
	document.write(""); 
	methodA.apply(handleCaller, ['xxx', 'yyy']); // 指定this object 
	}
宣告參數長度: 3
實際參數長度: 2
this: 
	function handleCaller() { 
	methodA('xxx', 'yyy'); 
	document.write(""); 
	methodA.apply(handleCaller, ['xxx', 'yyy']); // 指定this object 
	}
p1: xxx
p2: yyy
p3: undefined

========================
arguments: [object Arguments]
arguments.callee: 
	function methodA(p1, p2, p3) {
		document.write('========================' + '');
		document.write("arguments: " + arguments + ''); 
		document.write("arguments.callee: " + arguments.callee + ''); 
		document.write("arguments.callee.caller: " + arguments.callee.caller + ''); 
		document.write('宣告參數長度: '+ arguments.callee.length + ''); 
		document.write('實際參數長度: '+ arguments.length + ''); 
		document.write('this: ' + this + ''); 
		document.write('p1: ' + p1 + ''); 
		document.write('p2: ' + p2 + ''); 
		document.write('p3: ' + p3 + ''); 
	}
arguments.callee.caller: 
	function init() { 
		handleCaller(); 
		methodA.call(handleCaller, 'xxx', 'yyy'); 
	}
宣告參數長度: 3
實際參數長度: 2
this: 
	function handleCaller() { 
		methodA('xxx', 'yyy'); 
		document.write(""); 
		methodA.apply(handleCaller, ['xxx', 'yyy']); 
	}
p1: xxx
p2: yyy
p3: undefined
```

EXAMPLE 2

```javascript

function f1(argv0, argv1) {
  document.write('f1: ' + this.v, argv0, argv1 + '<br>');
}

function f2(argv0, argv1) {
  document.write('f2:  ' + this.w, argv0, argv1 + '<br>');
}

var obj =  { v: 'I am v of obj ' };
var obj2 = { w: 'I am w of obj ' };


obj.func = f1;
obj.func(1, 2);

obj2.func = f2;
obj2.func(3, 5);

f1.apply(obj, [1, 2]);
f1.bind(obj)(1, 2);
f1.call(obj, 1, 2);

f2.apply(obj2, [3, 5]);
f2.bind(obj2)(3, 5);
f2.call(obj2,3,5);

```

印出：

```text
f1: I am v of obj 12
f2: I am w of obj 35
f1: I am v of obj 12
f1: I am v of obj 12
f1: I am v of obj 12
f2: I am w of obj 35
f2: I am w of obj 35
f2: I am w of obj 35
```

## Ref.

{% embed url="http://fstoke.me/blog/?p=1932" %}

{% embed url="https://medium.com/@realdennis/javascript-聊聊call-apply-bind的差異與相似之處-2f82a4b4dd66" %}



