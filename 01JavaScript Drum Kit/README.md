# [JS30] DAY1:JavaScript Drum Kit

:::info
`` --> ES6 中的模板字串（在～下方的那個符號）
`${}` --> ES6 template strings
在模版字串中如果有需要引入變數，則可以是用${ }，來代入變數
:::

```javascript=
// 監聽鍵盤按鍵事件，並回傳所按的按鍵為何
  window.addEventListener('keydown', function(e){
    console.log(e);
  });
  
  //  選擇鍵盤按鍵所對應到的網頁元素
  const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
  //  監聽使用者按鍵事件，並取得對應的元素
  const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);
  
```
```javascript=
const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);

寫法等同

const audio = document.querySelector('audio[data-key="'+e.keyCode+'"]');
```
```javascript=
jQuery     寫法 
  key.addClass('playing');
  
Javascirpt 寫法 
  key.classList.add('playing');
  key.classList.remove('playing');
```

#### forEach 方法 (陣列) -- 針對陣列中的每個元素執行指定的動作。

以下為針對每一個需要做監聽的物件進行監聽
```javascript=
keys.forEach(key => key.addEventListener('transitionend', removeTransition));
```
:::warning
forEach 方法
- 會依照遞增索引順序，針對陣列中存在的每個元素各呼叫 callbackfn 函式一次。對於陣列中遺漏的元素則不會呼叫回呼函式。
- 除了陣列物件之外，任何具有 length 屬性且具有數值索引屬性名稱的物件都可以使用 forEach 方法。

- 如果 callbackfn 引數不是函式物件，就會擲回 TypeError 例外狀況。

[範例](https://stackoverflow.com/questions/33763768/loop-through-array-of-values-with-arrow-function)
:::

http://keycode.info/ 

### JS30 day1 學習內容

- 監聽事件（addEventListener(event, function)）--- 在 function 中代入參數會回傳和該事件有關的物件
- 按鍵事件（keydown）
- 透過 CSS 選擇元素（querySelector, querySelectorAll)
- 音效相關（element.play( ), element.currentTime)
- 資料屬性（data-* attribute）
- CSS相關（element.classList.add( ), element.classList.remove( )
- 動畫結束事件 --- [transitionEnd](https://developer.mozilla.org/zh-TW/docs/Web/Events/transitionend)
- forEach( ) -- 針對陣列中的每個元素執行指定的動作。
- 若不符合則退出函式：function( ){if(...) return}