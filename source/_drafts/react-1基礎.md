---
title: React 1基礎 - JSX
tags: 
- JavaScript
- React
categories:
- JavaScript
- React
---
因為工作的需要，從原本使用 Vue 的框架需要轉乘的框架需要轉成 React。
之前在讀 Vue、React 的差異時發現雷同處很多畢竟都是 JavaScript 延伸出來的，下面開始記錄自己學習 React 的筆記。

### JSX 是什麼?
JSX 可以當做 HTML 的進階版，把 HTML 寫在 JavaScript 做一個整合，當成變數來使用(下面文章有詳細的說明)。
透過 JSX 不用再使用 querySelector 選到該元素後才能換，可以在 HTML 中帶入 js 變數

比較 Vue
Vue 是在 HTML 中放入 js，React 是 js 放在 HTML 中。
Vue 開發速度比較快，React 是需要 code review 比較直覺，不會 HTML 上有程式邏輯。

### 設定
[React - Hello World 範例](https://codepen.io/pen?editors=1010)
由上面連結的 js 左上角齒輪中可以看出使用 React 前需要先做什麼設定
1. 使用 Babel：
把 js 先進行編譯處理，讓最新的 js 語法在不同版本、不同瀏覽器中都可以運行，不會發生新的寫法有些瀏覽器無法讀取的狀態。
2. 載入 2 個 js 套件：react.development.js、react-dom.development.js
react 讀取 JSX，react-dom 把寫的內容放在 HTML DOM 上。

### 架構分析與寫畫面
HTML 中使用 id="root" 把 js 中的 JSX 寫好後放進來。
```
<div id="root"></div>
```

js 中上半部把需要的變數寫一寫，在最後使用 JSX
```
// 需要使用的變數
const name = 'Teisha';
const waterMoney = 30;
const spend = (waterAmount, waterMoney) => waterAmount*waterMoney;

// JSX，1.標籤內容後需要「,」再把內容丟回 HTML 中。
// 2.「{}」符號中可以放變數、表達式(會回傳一個值-可以變數、計算，不是 if、for 的陳述句)
ReactDOM.render(
  <h1>{name}今天出門忘了帶水，買了售價 {waterMoney} 元的水 3 瓶，共花了 {spend(3,waterMoney)} 元</h1>, 
  document.getElementById('root')
);
```

3. 如果覺得上面 JSX 太長，可以把內容變成一個變數放入符號「()」中再丟回去。這邊的變數習慣大寫開頭
```
const Content = (
  <h1>{name}今天出門忘了帶水</h1>
  <p>買了售價 {waterMoney} 元的水 3 瓶，共花了 {spend(3,waterMoney)} 元</p>
)
ReactDOM.render(Content, document.getElementById('root'));
```

如果在同一行「()」可加可不加，下面2行程式碼都可以。
```
const Element = <div>123</div>;
const Element = (<div>123</div>);
```

4. 在 JSX 中標籤內沒有內容可以自己關閉
一般都要寫完整，但是 JSX 有這個特性，另有些原本的標籤也有這樣的特色
ex: <img />、<hr />、<br />、<input />
```
// 原本
<i class="fas fa-angle-right"></i>

// 可以縮寫成自己關閉
<i class="fas fa-angle-right" />
```

5. 使用 CSS 樣式
class 已經是 js 的關鍵字，因此在 JSX 中要改成 className
```
<i className="fas fa-angle-right" />
```

6. 使用 inline-style 行內樣式
a. style 屬性可以用物件的方式
b. 名稱使用「小駝峰」
c. 結束換行用「,」不是分號，因為是物件
d. 屬性值要變成字串使用「單引號或雙引號」--> boxShadow: "0 0 10px #ccc"
e. 屬性值預設是 px 為單位，因此 padding: 10 相等於 padding: "10px"。(注意加單位外面要有引號)
```
// 原本
<div style="color: #ccc; box-shadow: 0 0 10px #ccc; border:1px solid black">123</div>

// JSX
const elementStyle = {
  color: "#ccc",
  boxShadow: "0 0 10px #ccc",
  border: "1px solid black",
  padding: 10
}
<div style={elementStyle}>123</div>
```

有時候不會特別把行內樣式額外定義直接寫，會變成下面樣子
「{{}}」裡面代表是物件，外面需要用物件(表達式的關係)所以要再用一個括號包起來。
```
// 原本
<div style="color: #ccc; border:1px solid black">123</div>

// JSX
<div style={{
  color: "#ccc",
  border: "1px solid black"
  }}
>
  123
</div>
```

到這邊已經可以把畫面都寫出來的。
下一篇開始介紹元件

-----
補充：註解符號
- HTML 中
<!--我是註解-->
- JS 中
（1）/* */ 多行的註解
（2）// 單行註解
- JSX 中
{/* 我是註解 */}