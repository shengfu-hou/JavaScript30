# Update CSS variable with JS 
[DEMO](http://htmlpreview.github.io/?https://github.com/shengfu-hou/JavaScript30/blob/master/03%20-%20CSS%20Variables/index.html)

## 摘要

   這個case要做的事情是透過input改變CSS的變數，這裡的CSS變數為`內邊距(padding)` `模糊度(blur)` `顏色`;

   想法如下:

   1.  監聽三個input,`input`時觸發事件`handleUpdate`，範例是用`change`，`mousemove`兩個事件完成，這裡可以用一個input代替
    
 ```
    (DOM).forEach(input=>input.addEventListener("input",handleUpdate));
 ```

   2.  handleUpdate()內容為改變變數值為目前value,先 DOM `:root` 裡面的變數,然後改變屬性為觸發事件那個input對應的變數

   其中`suffix`為 `this.dataset.sizing || ''` 

   是CSS變數需要的單位px,不需要時為空

 ```
    document.documentElement.style.setProperty(`--${this.name}`,this.value + suffix);
 ```


## 重點提醒

1. `type="range"`會呈現可左右移動的滑動桿。
```html
<input type="range" min="0" max="100" step="1" value="10">
```
2. `:root`是DOM元件的根元素，相當於`<html>`，一般會把CSS的變數聲明在內，CSS3原生的變數表示法: `--variable`;

```css
\\宣告方式
:root{
      --base: #ffc600;
      --blur: 10px;
      --spacing: 10px;
}
\\使用方式
span.hl{
	color: var(--base);
}
img{
	padding: var(--spacing);
    filter: blur(var(--blur));
    background: var(--base);
}
```

