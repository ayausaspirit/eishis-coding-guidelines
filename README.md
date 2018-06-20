# コーディングガイドライン
# シンタックス
- インデントはスペース2つで
    - 全ての環境で同じようにコードをrenderさせる
- 階層が違う場合はインデントする
- 属性にはダブルクオーテーションを使用
- 空要素には `/` を入れない
- 閉じタグは任意でも必ず記入する

![Screen Shot 2018-05-28 at 4.12.58 PM.png (38.1 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/05/28/13434/2097aafc-0a5b-4dc9-824f-89090b766405.png)

# 必要のないスペース
エディタで消すように設定する

# DOCTYPE宣言
下記のように記述する
![Screen Shot 2018-05-28 at 4.13.36 PM.png (10.9 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/05/28/13434/6e96da5b-f54b-4eb8-bbf2-329a680d4773.png)

# Language属性
lang="ja"を設定する
![Screen Shot 2018-05-28 at 4.14.26 PM.png (7.2 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/05/28/13434/055f8ba0-ce9e-48cf-ba95-908c10c1f733.png)

# IE compantibility mode
edg modeでrenderするように設定
![Screen Shot 2018-05-28 at 4.15.06 PM.png (11.5 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/05/28/13434/2cca2b5c-e655-4d26-87cf-2082255caf43.png)

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
![Screen Shot 2018-05-28 at 4.15.27 PM.png (9.9 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/05/28/13434/3a8bdb41-f865-456b-b845-e80ef4430ca2.png)

# CSS と JSの読み込み
`type` 属性は必要ないので、書かない。
CSS と JavaScript のファイルは `text/css` と `text/javascript` として読みこむ
![Screen Shot 2018-05-28 at 4.16.25 PM.png (34.8 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/05/28/13434/c3d114ce-4106-4c87-be0c-cf01e5dc2da7.png)

# 属性の順番
属性は読みやすいように以下順番で表記する
<ul>
      <li><code>class</code>,<code>id</code></li>
      <li><code>data-*</code>,<code>name</code>,<code>src</code>, <code>for</code>, <code>type</code>, <code>href</code>, <code>value</code>,<code>title</code>, <code>alt</code>,<code>role</code>, <code>aria-*</code></li>
    </ul>

![Screen Shot 2018-05-28 at 4.17.35 PM.png (26.3 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/05/28/13434/fa9fc74b-42c1-4aee-80b8-2fbab63d51e1.png)

# ブーリアン属性
`disabled` や `checked` などのブーリアン属性には `value` を追加しない
![Screen Shot 2018-05-28 at 4.18.55 PM.png (27.2 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/05/28/13434/c9ebe15c-e367-48cc-aa92-34cde824edff.png)

# マークアップはなるべく簡潔に
必要ない要素は取り除き、なるべくマークアップを簡潔にまとめる
![Screen Shot 2018-05-28 at 4.19.34 PM.png (22.0 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/05/28/13434/e0de7c89-a394-40ad-9f1f-a08fb47e4a65.png)

# HTMLディレクトリ構造

![Frame (1).png (195.1 kB)](https://bagelee.s3-ap-northeast-1.amazonaws.com/uploads/production/attachments/5668/2018/06/13/13434/d6b26971-cbb9-4de2-b324-3c01e2393885.png)

※ただし２ページ以下の場合はrootに下層ページをおいても問題ないものとする
※HTMLディレクトリ構造を変更する場合は下記Figmaより変更する
https://www.figma.com/file/zowxzbuF5uuYi1g0kRbh0l/directory-structure-diagram/duplicatehtml
