## HTML/CSS入門編1: HTML/CSSを理解しよう (全4回)

### 目次
[1-1_Webページの仕組みを知ろう](#1-1_Webページの仕組みを知ろう)</br>
[1-2_Webページを作ってみよう](#1-2_Webページを作ってみよう)</br>
[1-3_テキストを表示してみよう](#1-3_テキストを表示してみよう)</br>
[1-4_Bootstrapを使ってみよう](#1-4_Bootstrapを使ってみよう)</br>

</br>

***
</br>

### 1-1_Webページの仕組みを知ろう
- HTMLとCSSについて</br>
  簡単に言うと、ユーザーのブラウザからのリクエストに対して、サーバーからHTMLファイルやCSSファイル、画像ファイルやJSをお繰り返している。</br>
  それをブラウザが処理する事によってWebページをユーザーが見ることができる。</br>
</br>

- **HTML**
  - Hyper Text Markup Languageの略で、Webページの内容と構成を指定します。
  - テキストファイルとして保存。
  - 基本的に1つのページに1つのHTMLファイル。</br>
</br>

- **CSS**
  - Cascading Style Sheetsの略で、Webページのスタイル(サイズ・色・フォント・レイアウトなど)を指定する。
  - テキストファイルとして保存。
  - 複数のCSSを組み合わせたり、複数のHTMLから共通のCSSを利用したりできる。</br>
</br>

- **HTMLフレームワーク**
  あらかじめデザインされたHTML/CSSをセットにしたもの。CSSフレームワークと呼ばれる事もある。
- **Bootstrap**
  - ツイッター社が開発した高機能なHTMLフレームワーク。Webページの便利な部品を多数装備している。</br>
  - <u>レスポンシブデザインに対応</u>している。</br>
</br>

**レッスンの手順**</br>
1. 単純なWebページを作成する。
2. 文章を追加する。
3. Bootstrapを利用する。
4. CSSを追加する。
5. リンクと画像を追加する。
6. リストとナビゲーションバーを追加する。
7. テーブルを追加する。</br>
</br>

***
</br>

### 1-2_Webページを作ってみよう
次のファイルを作成し、編集する。</br>

```html
<!-- public_html/basic.html -->
<html>
  <h1>hello HTML&CSS</h1>
</html>
```
これで(http://localhost:8888/PJ_HTML-CSS/public_html/basic.html)
にアクセルするする事で上記の内容を表示できる。</br>
</br>

* **タグ**</br>
  この<~>で囲った部分を**タグ**という。</br>
  タグは`<*>~</*>`というふうに2つ一組で使用される場合が多い。</br>
</br>

* **コメント**</br>
  `<!-- ここがコメント -->`というふうに記述するとページに表示されない記述が可能。</br>
  コメントは後から人間がHTMLを見た際にその内容を理解するため、また一時的に記述内容を除外するために用いる。</br>
  コメントにする事を**コメントアウト**するという。</br>
</br>

* **インデント**</br>
  コード中に故意に空白を付けて、先頭を揃える事をインデントという。</br>
  インデントを用いる事で、セットになったタグの関係がひと目で分かり、コードの視認性が向上する。</br>
</br>

***
</br>

### 1-3_テキストを表示してみよう

* **pタグ**</br>
  `<p>`と`</p>`ではさまれた部分が、段落になる。</br>
  pタグのpとはparagraph(段落)の事。</br>
  pタグは画面の端で折り返して表示される。</br>
</br>

* **brタグ**</br>
  `<br>`単独で使用するタグ。</br>
  この位置で改行する。</br>
</br>

* **strongタグ**</br>
  `<strong>`と`</strong>`ではさまれた部分を強調する。</br>
</br>

***
</br>

### 1-4_Bootstrapを使ってみよう
ここではWebページを作成するために、HTML5という最新の企画に基づいて、HTMLフレームワークのBootstrapを導入してみる。</br>
まずはHTMLのタグの基本について理解する。</br>
```html
<!-- public_html/basic.html -->

<!-- ドキュメントタイプの指定 -->
<!DOCTYPE html>
<!-- Webページの言語の指定 -->
<html lang="ja">
    <head>
        <meta charset="utf-8">
        <title>Project Mole</title>
    </head>
    <body>
        <h1>吾輩は猫である。</h1>
    </body>
</html>
```
</br>

* **タグの属性**</br>
  `<html lang='ja'>`や`<div class='*'>`のようにタグに対して付属するものを**タグの属性**という。</br>
  `<html lang='ja'>`はhtmlタグのランゲージ属性にja(ジャパニーズ)を指定している。</br>
</br>

* **headタグ**</br>
  Webページ全体の情報を指定するタグ。</br>
  ここではmetaタグで文字コードを指定して、titleタグでWebページのタイトルを指定している。</br>
</br>

それではBootstrapを導入してみよう。
```html
<!-- public_html/basic.html -->
<!DOCTYPE html>
<html lang="ja">
    <head>
        <meta charset="utf-8">
        <!-- 下記2行のmetaタグを追加 -->
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1">

        <title>Project Mole</title>
        <!-- 下記を追加 -->
        <!-- Bootstrap -->
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">
    </head>
    <body>
        <h1>吾輩は猫である。</h1>

        <!-- 下記のscriptタグを追加 -->
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
        <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
    </body>
</html>
```
ここでページを表示してもフォントが変わるくらいでさほど見た目に変化はない。</br>
ここでpタグで文章を追加してみる。</br>

```html
<body>
        <h1>吾輩は猫である。</h1>
        <p class='lead'>名前はまだない。</p>>
```
ここで追加したクラス属性の`lead`とは文章の内容をまとめた要約文の事。ここでは文章を強調表示してくれる。</br>
</br>

さらに文章の下にボタンを設置してみる。</br>

```html
<body>
  <h1>吾輩は猫である。</h1>
  <p class='lead'>名前はまだない。</p>
  <a class='btn btn-primary' href='#'>OK</a>
```
これでBootstrapのCSSが反映された文章とボタンを追加できた。</br>
</br>

***
</br>

