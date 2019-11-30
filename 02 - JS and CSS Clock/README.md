# JS&CSS CLOCK  在頁面上做出一個會轉動的虛擬時鐘

## 摘要
CSS Transform()屬性：

1.使用`transform:rotate(90deg)`,將三根指針向上指(12點鐘方向)

2.使用`transform-origin:100%` ,將中心點移動到最右 (預設`transform-origin:50% ` 中心點會在指針中間)

JavaScript:

1.取時間使用`now = new Date()`, 可以取得的分秒時`now.getSeconds()`

2.`setInterval(setDate, 1000)`, 一秒執行一次setDate()

此範例秒針在59跳0秒時
秒針會瞬間逆時針轉回0度再馬上轉回到目前的位置。
這是因為作者在旋轉角度的寫法，是將當下的時間換算成角度，
因此當秒針從59秒要跳回0秒的時候，transform的rotate角度會由接近360轉回接近0度，以致於逆時針旋轉的產生。

可以將時間用加的方式,每秒加一次,就不會有這個問題
[myself](http://htmlpreview.github.io/?https://github.com/shengfu-hou/JavaScript30/blob/master/02%20-%20JS%20and%20CSS%20Clock/myself.html)
