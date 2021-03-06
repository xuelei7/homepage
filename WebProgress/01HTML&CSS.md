# HTML & CSS

## 環境構築

## HTML基礎

```html
<!--コメント-->

<!--ヘッダー-->
<h1></h1>

<!--段落-->
<p></p>

<!--リンク-->
<a href="http://www.xuelei7.github.io/homepage">title</a>

<!--画像-->
<img src="url">

<!--リスト-->
<ul>
    <li class="selected">aaa</li>
    <li>bbb</li>
</ul>
```

## CSS基礎

```css
h1 {
    /*文字色の指定*/
    color: #ff0000;
    font-size: 10px;
    font-family: serif;
    font-weight: bold;
    background-color: #dddddd;
    width: 500px;
    height: 80px;
}
.class {
    padding: 10px;
    border: 2px solid #ff0000;
    margin: 20px;
    float: left;
    background-image: url(https://www.xx.png);
    background-size: cover;
    opacity: 0.7;
    letter-spacing: 2px;
}
```

## レイアウト

```html
<!DOCTYPE html>
<html>
    <head>
        <!--全体の文字コード-->
        <meta charset="utf-8">
        
        <!--タイトル-->
        <title>title</title>

        <!--CSSの読み込み rel:種類 href:ファイル名-->
        <link rel="stylesheet" href="stylesheet.css">
    </head>
    <body>
        <div class="class"></div>
        <form>
            <!--入力-->
            <input>
            <textarea></textarea>
            <!--ボタン-->
            <input type="submit" value="保存">
        </form>
    </body>
</html>
```

## その他

display: block, inline-block, inline

:hover

border-radius: 角を丸くする

text-align: left, center, right そろえるヤツ

Font Awesome: <link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">

rgba, rgb: rgb(255,147,30) <-> #ff931e background-colorに指定する

transition: all(変化対象) 1s(変化時間) アニメーション付ける

line-height: 行間指定

位置指定：
position: absolute/relative/fixed; 
top: oopx; 
left: oopx;

影の指定：box-shadow: 水平　垂直　色

カーソル指定：cursor: text/pointer/default:

letter-spacing: 文字間隔

## 上級編

レスポンシブデザイン：画面に対応するレイアウト変更

---
### CSSにおける設定

- メディアクエリ(Media Queries)

```css
@media (max-width: 1000px) {
    /* 1000px 以下のときに適用したいCSSを記述*/
    /* max-width: 最大幅 */
    /* min-width: 最小幅 */
    /* ブレイクポイント: スマホ <= 670px < タブレット <= 1000px < パソコン */
}

.item {
    width: 25%;
}
@media (max-width: 1000px) {
    .item {
        width: 50%;
    }
}
@media (max-width: 670px) {
    .item {
        width: 100%;
    }
}
```

- box-sizing: border-box;

レイアウト崩れ防止

border-box: width + padding + border (marginは含まれない)

```css
/* 全要素に適応させる */
* {
    box-sizing: border-box;
}

.container {
    max-width: 1170px;
    width: 100%;
}
```

---
### HTMLにおける設定

- viewportの設定

```html
<head>
    <meta name="viewport" content="width=device-width, initiaal-scale=1.0">
</head>
```