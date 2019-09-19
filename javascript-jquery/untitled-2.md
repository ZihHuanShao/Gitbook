# JQ .className \*

星號`*`的作用

```javascript
...

<style>
<!-----------------------------------
'*' 會讓<div class="ancestors">底下所有的descendant有作用；
若沒有'*'，則只會對<div class="ancestors">有作用
------------------------------------>
.ancestors * { 
  ...
}
</style>

...

<body>
  <div class="ancestors">
    <div style="width:500px;">div (great-grandparent)
      <ul>ul (grandparent)  
        <li>li (direct parent)
          <span>span</span>
        </li>
      </ul>   
    </div>
  
    <div style="width:500px;">div (grandparent)   
      <p>p (direct parent)
        <span>span</span>
      </p> 
    </div>
  </div>
</body>

...

```

## Ref.

{% embed url="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery\_parent" %}

