# [JS30] DAY3:CSS Variables

## 改變三個變數: Space, Blur, Base，當我們在畫面改變設定值(拉動range或改變顏色)，它會立即更新畫面

## CSS 變數

CSS 原生變數，可以透過 JavaScript 擷取，並動態修改變數值，而這個變數值一變，所有套用這個變數的 Style 屬性值也都會連帶變更。

### :root 宣告文件的根元素
[:root](https://css-tricks.com/almanac/selectors/r/root/) 用來宣告文件的根元素，而網頁的根元素一定是 HTML；所以只有兩種使用情形：（一）:root。（二）HTML:root

#### 使用 `--` 來自訂變數名稱
```HTML=
:root{
    --main-color: hotpink;
    --pane-padding: 5px 10px;
}
//--main-color 為自定義變數名稱，hotpink 為值
```
#### 用 var() 來使用自訂的 CSS 變數
```html=
img{
    padding: var(--pane-padding);
}
```
## HTML data-* Attributes
#### 在 HTML 自定義變數 data-* 以及用 JS 取出變數
```html=
例如：
在 html 嵌入自定義的 sizing 資料
<p data-sizing="px"></p>

JS 取變數:
在element取dataset就可以用相同的「自定義名稱」讀/寫 自定義資料了，資料型態是字串。
p.dataset.sizing = "";
```
## Javscript
#### JS 修改 css 變數
```javascript=
element.style.setProperty('--main-bg-color', 'brown');
```
#### JS 取 html element
```javascript=
document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
```

- document.documentElement 回傳<html>的節點