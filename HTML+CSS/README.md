# HTMLコーディングガイドライン

# シンタックス
- インデントはスペース2つで
    - 全ての環境で同じようにコードをrenderさせる
- 階層が違う場合はインデントする
- 属性にはダブルクオーテーションを使用
- 空要素には `/` を入れない
- 閉じタグは任意でも必ず記入する

```
<!DOCTYPE html>
  <html>
    <head>
      <title>Page title</title>
    </head>
    <body>
      <img src="img/logo.png" alt="company logo">
      <h1 class="hello-world">Hello, world!</h1>
    </body>
</html>
```

# 必要のないスペース
エディタで消すように設定する

# DOCTYPE宣言
下記のように記述する
```
<!DOCTYPE html>
<html>
  <head>
  </head>
</html>
```

# Language属性
lang="ja"を設定する
```
<html lang="ja">
  <!-- ... -->
</html>
```
# IE compantibility mode
edge modeでrenderするように設定
```
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

# headの中身

- charsetを一番最初に記述する

```
  <meta charset="utf-8">
  <meta http-equiv="x-ua-compatible" content="ie=edge">
  <title></title>
  <meta name="description" content="">
  <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

  <link rel="manifest" href="site.webmanifest">
  <link rel="apple-touch-icon" href="icon.png">
  <!-- Place favicon.ico in the root directory -->

  <link rel="stylesheet" href="css/normalize.css">
  <link rel="stylesheet" href="css/main.css">

  <!-- OGPの必須プロパティ -->
  <meta property="og:title" content="ページのタイトル" />
  <meta property="og:type" content="article" /> <!--またはwebsite, blog-->
  <meta property="og:url" content="ページのURL" />
  <meta property="og:image" content="画像のURL" />

  <!-- OGPのオプションプロパティ -->
  <meta property="og:site_name" content="サイト名" />
  <meta property="og:description" content="ページのディスクリプション" />

  <!-- Facebook専用のプロパティ -->
  <meta property="fb:app_id" content="App-ID（15文字の半角数字）" />

  <!-- Twitter Cardsの記述 -->
  <meta name="twitter:card" content="summary">
  <meta name="twitter:site" content="@[Twitter ID]">
```


# 文字エンコード
基本UTF-8に設定する
```
<head>
  <meta charset="UTF-8">
</head>
```

# CSS と JSの読み込み
`type` 属性は必要ないので、書かない。
CSS と JavaScript のファイルは `text/css` と `text/javascript` として読みこむ
```
<!-- CSS -->
<link rel="stylesheet" href="code-guide.css">

<!-- JavaScript -->
<script src="code-guide.js"></script>
```

# 属性の順番
属性は読みやすいように以下順番で表記する

<ul>
  <li><code>class</code>,<code>id</code></li>
  <li><code>data-*</code>,<code>name</code>,<code>src</code>, <code>for</code>, <code>type</code>, <code>href</code>, <code>value</code>,<code>title</code>, <code>alt</code>,<code>role</code>, <code>aria-*</code></li>
</ul>


# ブーリアン属性
`disabled` や `checked` などのブーリアン属性には `value` を追加しない
```
<input type="text" disabled>

<input type="checkbox" value="1" checked>

<select>
  <option value="1" selected>1</option>
</select>
```

# マークアップはなるべく簡潔に
必要ない要素は取り除き、なるべくマークアップを簡潔にまとめる
```
<!-- 避ける -->
<span class="avatar">
  <img src="...">
</span>

<!-- こちらがOK -->
<img class="avatar" src="...">
```

# CSSコーディングガイドライン

# CSS命名規則
## BEMとOOCSSとFLOCSSを組み合わせて命名する

### そもそもOOCSSとは？
- https://hajipion.com/1879.html
- 構造とみためを切り離す

### そもそもBEMとは？
- https://ferret-plus.com/7808
- .inner__itemみたいに上の要素を継承して命名する

### そもそもFLOCSSとは？
- https://qiita.com/sueshin/items/dcbaf3d8a0adb6b087db
- ファイル名に相当するプレフィックスがつく

## 上記を踏まえた上での命名規則

### 例　こんな感じの構造だった場合
<pre class="line-numbers"><code class="language-markup">&lt;div class=&quot;container&quot;&gt;
    &lt;div class=&quot;container__inner&quot;&gt;
          &lt;ul class=&quot;container__inner__nav&quot;&gt;
                &lt;a href=&quot;#&quot; class=&quot;inner__nav__item&quot;&gt;
                    &lt;li class=&quot;c-btn c-btn1 c-btn1--active&quot;&gt;hogehoge&lt;/li&gt;
                &lt;/a&gt;
                &lt;a href=&quot;#&quot; class=&quot;inner__nav__item&quot;&gt;
                    &lt;li class=&quot;c-btn c-btn1&quot;&gt;hogehoge&lt;/li&gt;
                &lt;/a&gt;
                &lt;a href=&quot;#&quot; class=&quot;inner__nav__item&quot;&gt;
                    &lt;li class=&quot;c-btn c-btn1&quot;&gt;hogehoge&lt;/li&gt;
                &lt;/a&gt;
          &lt;/ul&gt;
    &lt;/div&gt;
&lt;/div&gt;
</code></pre>
- コンポーネントを作る際など、構造と見た目を切り離してコーディングする
#### component.scss
<pre class="line-numbers"><code class="language-css">//ボタンで使う共通のスタイル
.c-btn {
    width:120px;
    height:40px;
    font-size:16px;
    font-weight:bold;
    text-align:center;
    line-height:40px;
    border-radius:8px;
    border-style:solid;
    border-width:2px;
}
//個別のスタイル
.c-btn1 {
    background-color:blue;
    border-color:#ccc;
    color:#123456;
    &--active {
        opacity:0.6;
    }
}
//個別のスタイル
.c-btn2 {
    background-color:red;
    background-color:#bbb;
    color:#234567;
}
</code></pre>
- BEMではハイフン（-）とアンダーバー（_）は２文字づつ使用する
    - `.container__inner`
- BEMのBlock（親要素）の継承は２つ上まで記載する
<pre class="line-numbers"><code class="language-css">.container {
    width:960px;
    margin:0 auto;
    &&#x5F;&#x5F;inner {   (.container&#x5F;&#x5F;inner)
        background-color:#eee;
        &&#x5F;&#x5F;nav {   (.container&#x5F;&#x5F;inner&#x5F;&#x5F;nav)
            background-color:#ccc;
            padding:5px;
            display:flex;
            justfy-content:flex-start;
            .inner&#x5F;&#x5F;nav&#x5F;&#x5F;item {   (下の要素になったら、直近の２要素を継承する)
                color:#fff;
            }
        }
    }
}
</code></pre>

- （特にコンポーネントなど）プレフィックスをつけてわかりやすくする
    - `.c-btn` `.p-card`
- 2語以上で命名したい際はスネークケースを使用する（ハイフン使用-）
    - `.main-visual`

# HTMLディレクトリ構造

![html_css](./../assets/html_css.png)

# Figma

https://www.figma.com/file/zowxzbuF5uuYi1g0kRbh0l/directory-structure-diagram/duplicate
