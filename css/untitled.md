# box設計

設計三個block，每一個block的大小為320px寬且並排

* width\(原始寬度\): 280px
* padding\(框內偏移\): 20px \(左+右\)
* margin\(框外偏移\): 20px \(左+右\)



```css
.box {
    width: 280px;
    padding: 10px;
    margin: 10px;
    background-color: white;
    display: inline-block;/*顯示模式並排*/
    vertical-align: top;/*垂直對齊, 對齊上方*/
}
```

