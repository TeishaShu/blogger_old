---
title: React 3基礎 - 陳述句(判斷式...)
tags: 
- JavaScript
- React
categories:
- JavaScript
- React
---

### JSX 中的判斷式
JSX 中 {} 內只能放「expressions 表達式」-有個值回應，statement 陳述句是呼叫不會有回應的值。
因此不能在 JSX 中使用 if...else..，需要換成使用[邏輯運算子 ||、&&](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Obsolete_Pages/Obsolete_Pages/Obsolete_Pages/%E9%81%8B%E7%AE%97%E5%AD%90/%E9%82%8F%E8%BC%AF%E9%81%8B%E7%AE%97%E5%AD%90)、[三元判斷式 ?:](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

邏輯運算子中 && 我很容易弄錯~主要是取 false，當2個都是真值時取後面的。(&& 主要抓 false，|| 主要抓 true)
