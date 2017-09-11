# [JS30] DAY2: JS and CSS Clock

## 目標：製作一個好看且會動的時鐘

## CSS Transform
[CSS3 transform Property](https://www.w3schools.com/cssref/css3_pr_transform.asp)
```Css=
寫法:
transform: translateX(20px);
transform: rotate(45deg);
```
<ul class="origin">
    <li>translateX(x) --> X軸平移</li>
    <li>translateY(y) --> Y軸平移</li>
    <li>translateZ(z) --> Z軸平移</li>
    <li>translate3d(x,y,z) --> X、Y、Z軸平移 <span class="red">(3D)</span></li>
</ul>

<ul class="green">
    <li>scaleX(x) -->  X軸放大</li>
    <li>scaleY(y) -->  Y軸放大</li>
    <li>scaleZ(z) -->  Z軸放大（視覺上會有前後放大縮小的感覺，3D時使用）</li>
    <li>scale(x,y)    X、Y軸放大</li>
    <li>scale3d(x,y,z) X、Y、Z軸放大 <span class="red">(3D)</span></li>
</ul>

<ul class="blue">
    <li>rotate(angle), 旋轉</li>
    <li>rotateX(angle), X軸固定的旋轉 <span class="red">(3D)</span></li>
    <li>rotateY(angle), Y軸固定的旋轉 <span class="red">(3D)</span></li>
    <li>rotateZ(angle), Z軸固定的旋轉 <span class="red">(3D)</span></li>
    <li>rotate3d(x,y,z,angle), 3D旋轉 <span class="red">(3D)</span></li>
</ul>

<ul>
    <li>skewX(angle), 水平歪斜 (2D)</li>
    <li>skewY(angle), 垂直歪斜 (2D)</li>
    <li>skew(x-angle,y-angle), 水平＋垂直歪斜 (2D)</li>
</ul>

<ul class="din">
    <li>matrix(n,n,n,n,x,y) x,y平移、n歪斜, 6個值 (2D)</li>
    <li>matrix3d(n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n)平移＋歪斜, 16個值 <span class="red">(3D)</span></li>
</ul>

<ul class="yellow">
    <li>perspective(n), 透視 <span class="red">(3D)</span></li>
</ul>

## Transition-timing-function 「過場時」的變化函數

[CSS3 transition-timing-function Property](https://www.w3schools.com/cssref/css3_pr_transition-timing-function.asp)
```css=
寫法：
transition-timing-function: ease(可替換以下函數)
```
- ease
- linear
- ease-in 類似cubic-bezier(0.42,0,1,1))
- ease-out 類似cubic-bezier(0,0,0.58,1))
- ease-in-out 類似cubic-bezier(0.42,0,0.58,1))
- step-star
- step-en
- steps(int,start|end)
- cubic-bezier(n,n,n,n), 貝玆函數 算是自訂變化曲線函數

## Javascript

### 取得現在的時間

>關於更多 [JavaScript 時間函式](https://www.evernote.com/l/AcVsMUPlMCxLoL5ovXUzbpfymBO2f7O2aBY)

```javascript
const now = new Date()
const hour = now.getHours()
const minute = now.getMinutes()
const second = now.getSeconds()
```

### 將時間轉換成角度
```javascript
const hourDeg = (hour / 12) * 360
const minuteDeg = (minute / 60) * 360
const secondDeg = (second / 60) * 360
```
### setInterval()
調用函數或重複執行代碼片段，每次調用該函數之間具有固定的時間延遲。
```Javascript=
function setDate(){
  //data
}
setInterval(setDate, 1000);
```
### CSS 操作

利用 `el.style.<styleAttribute>` 來操作 CSS：

> 關於更多 [JavaScript CSS 操作](https://www.evernote.com/l/AcXWcdQgs6RJtKs0TrVOtckwttSaaLATZcU)

```javascript
const hourHand = document.querySelector('.hour-hand')
hourHand.style.transform = `rotate(${hourDeg + 90}deg) scaleX(0.7)`
```
