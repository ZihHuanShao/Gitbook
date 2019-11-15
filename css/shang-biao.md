# 上標

### METHOD 1

```css
<div>
	<span style="position: relative; top: -25px;">❎</span>醫護兵1
</div>
```

### METHOD 2

```markup
<div>a<span>b</span></div>
```

```css
span {
 vertical-align: super;
 font-size: 2px;
}
```

### METHOD3

使用原生的`<sup>`\(`<sub>`為下標\)

```markup
<p>This text contains <sub>subscript</sub> text.</p>
<p>This text contains <sup>superscript</sup> text.</p>
```

