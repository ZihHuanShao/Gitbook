# 回應式排版\(手機自動調整版面\)

RWD \(Responsive Web Design\)



```css
<head>
    ...
    /*手機不要對網頁做任意的縮放*/
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1"/>
    <style>
        ...
        /*使用者使用螢幕, 螢幕最大寬度尺寸為600*/
        @media screen and (max-width: 600px) {
            .content {
                width: 100%;
                text-align: center;
            }
        }
    </sty/e>
</head>
```

