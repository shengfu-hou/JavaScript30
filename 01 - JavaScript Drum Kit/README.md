# Drum kit

### js 理解整理
這個case需求的案件事件為 事件A.利用輸入鍵盤的案件事件`keydown`觸發功能，放出音樂  事件B.音樂放完該執行什麼？

 
 ```
window.addEventListener('keydown', playsound);
```
事件A.利用輸入鍵盤的案件事件`keydown`觸發功能：
1. playSound() 內容思維為利用`keyCode`取值，並將`keyCode`的值對應到`data-key`，接者對相對應的`audio[data-key="${e.keyCode}"]`放出音樂	 `audio.play()`,並且綁定`div[data-key="${e.keyCode}"]`用`selector.classList.add('playing')`將標籤加入.playing

2.控制音樂重置時間 `audio.currentTime = num`  ，本案 num = 0； (才能連續按鍵發聲) 

 

```
(DOM每個.key標籤).addEventListener('transitionend', removeTransition)；
```
事件B. 音樂結束移除.playing標籤:

1.transitionend事件主要是對應到 CSS 中 transition 的動畫效果，當這個 transition 效果執行結束的時候會引發事件。
2.removeTransition() 內容為 `e.target.classLiss.remove("playing")`  將對應標籤移除.playing


### 學習 ，重新了解

監聽事件addEventListener(event, function)--- 在 function 中代入參數會回傳和該事件有關的物件
按鍵事件 keydown
透過 CSS 選擇元素 querySelector, querySelectorAll
音效相關 element.play( ), element.currentTime 
資料屬性 data-* attribute
CSS相關 element.classList.add( ), element.classList.remove( )
動畫結束事件 --- transitionend
forEach( )
若不符合則退出函式：function( ){if(...) return}
