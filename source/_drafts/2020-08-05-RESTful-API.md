---
title: RESTful API
tags: 
  - RESTful API
---
### 目的
一套設計規範來協議前後端的API，比較不用花時間猜怎麼使用，送出後會有狀態碼顯示。

### 三種元件組成：
1. URL定位資源。(不同HTTP動詞有對應的URL寫法.寫在網址的最後面)
2. HTTP動詞描述操作：GET、POST、PUT、DELETE…(有很多種.常用的幾個)
3. Content Types 資源呈現方式：JSON、XML…。

| HTTP動詞 | 中文名稱    | 備註                                                 |
|----------|-------------|------------------------------------------------------|
| GET      | 獲取.讀取   | 從伺服器取出資料(一項或多項)。請求展示取得指定的資料 |
| POST     | 新增        | 在伺服器新增資料(用在新增的動作store)                |
| PUT      | 更新.替換   | 跟PATCH類似.一個                                     |
| DELETE   | 刪除        | destroy                                              |
| -        | -           | -                                                    |
| PATCH    | 更新.替換   | 跟PUT類似.選取的批次。                               |
| HEAD     | ----------- | 跟GET方法相同，但沒有回應主體（response body）       |
| OPTIONS  | ----------- | 描述指定資源的溝通方法                               |

每個資源都會有一個 url 位址，利用 url 去做一些事情會使用到 http 動詞

 → 一個檔案：變數{id}。多個檔案：陣列方式丟變數。

 → 加「?」是非必填，不用加參數。

- (思考)為何delete 不是對應 delete 而是 destroy?

請求request 和 操作actions 的指令不同，一開始設定時有分開不要一樣。

4種標準方法： GET、POST、PUT、DELETE

7種RESTful actions：index、new、create、edit、update、show、destroy

(使用destroy可以做批次刪除多個檔案)

[Why the Ruby on Rails action “destroy” is not named “delete”?](https://stackoverflow.com/questions/14730451/why-the-ruby-on-rails-action-destroy-is-not-named-delete)
