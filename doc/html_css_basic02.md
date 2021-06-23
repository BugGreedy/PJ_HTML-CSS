## HTML/CSS入門編2: CSSの基礎を学ぼう (全6回)

### 目次
[2-1_CSSの基本形を理解しよう](#2-1_CSSの基本形を理解しよう)</br>
[2-2_CSSの色指定を理解しよう](#2-2_CSSの色指定を理解しよう)</br>
[2-3_CSSのフォント指定を理解しよう](#2-3_CSSのフォント指定を理解しよう)</br>
[2-4_CSSのレイアウト指定を理解しよう](#2-4_CSSのレイアウト指定を理解しよう)</br>
[2-5_レスポンシブデザインにしよう](#2-5_レスポンシブデザインにしよう)</br>
[2-6_Bootstrapのグリッドシステムを理解しよう](#2-6_Bootstrapのグリッドシステムを理解しよう)</br>


</br>

***
</br>

### 2-1_CSSの基本形を理解しよう
このレッスンではHTMLの見た目を定義するCSSについて学習する。</br>
また、Bootstrapを使って、レスポンシブデザインとグリッドについても解説する。</br>
</br>
別ファイルでCSSを読み込む事も可能だが、今回はhtml内にCSSを記載してみる。</br>

```html
<!-- public_html/basic02.html -->
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css">

        <!-- 下記のstyleタグを追記 -->
        <style>
          body{
            padding: 30px;
          }
        </style>
    </head>

```
これでbody要素の周囲に30pxの余白が追加できた。</br>
ここではbodyタグに対してstyleを指定している。このように指定の対象を表す部分を**セレクタ**という。</br>
また、{}内のstyleの要素を**プロパティ**という。</br>
プロパティと値の間はコロンで区切り、末尾にはセミコロンを置く。
</br>

***
</br>

### 2-2_CSSの色指定を理解しよう
ここではWebページの色を変えるため、CSSファイルの色指定について理解する。</br>
下記の記述でWebページの背景の色を変更する事ができる。</br>
```html
<head>
<style>
  body{
    background-color: red;
    /* backgourndに略せる */
  }
</style>
</head>
```
</br>

* カラーを指定する時の注意</br>
  色の指定は16進数で表される。</br>
  10以上の数字がないのでA~Fで表される。</br>

  ```
  16進数の例

  1桁
   0  1  2  3  4  5  6  7  8  9  A  B  C  D  E  F

  2桁
  10 11 12 13 14 15 16 17 18 19 1A 1B 1C 1D 1E 1F
  ```
  </br>
  そのためRGBが各2桁で表される。00~FF。FFは10進数だと255。</br>
  #000000(真っ黒) ~ #FFFFFF(真っ白)</br>
</br>

次に文字の色を変えてみる。</br>
これは`color`というプロパティで変更する事ができる。</br>

```html
<style>
  body{
    padding: 30px;
    background:#E6A3A0;
    color: #ffFFFF;
  }
</style>
```
</br>

***
</br>

### 2-3_CSSのフォント指定を理解しよう
ここではpタグの文字を太字にしてみる。</br>
```html
<style>
  p {
    font-weight: bold;
  }
</style>
```
次はpタグの文字のサイズを変更してみる。</br>

```html
<style>
  p {
    font-weight: bold;
    font-size: 40px;
  }
</style>
```
また、`font-size: 120%;`など％でも指定する事ができる。</br>
次にフォントを変更してみる。</br>
```html
<style>
  p {
    font-weight: bold;
    font-size: 120%;
    font-family: serif;
  }
</style>
```
**備考**
* `serif`は明朝体のような文字の端にヒゲがある書体の総称。</br>
  逆にゴシック体のような文字の端にヒゲがない書体は**sans-serif**という。</br>
  </br>
* `font-family`をイチから指定するケースは現在は少ない。</br>
  また特定の端末にしか使用されていないフォントを指定しないようにする。</br>
  とはいえ、どの端末で表示されるか分からないから`font-family`は複数のフォントを指定するのが望ましい。</br>
  文章内のどこか一部にフォントを指定する場合は、CSSを用いるのではなく`<span class="フォント名">フォントを指定したい文章</span>`のようにhtmlで指定する。</br>
</br>

***
</br>

### 2-4_CSSのレイアウト指定を理解しよう
ここではCSSを使ったパーツのレイアウトに挑戦する。</br>
そのためにCSSを使った余白や感覚の指定方法について理解する。</br>
</br>
まず、表示されている文章の余白がどうなっているか調べるために、表示領域の枠線を引いてみる。</br>

```html
<style>
 p {
   border: dotted #008080;
 }
</style>
```
これでpタグの表示領域に点線が表示される。</br>
この状態でgoogle chromeのデベロッパーモード(option + command + i)を起動すると余白を確認する事ができる。</br>
</br>

ここまでは`padding`で余白を調整してきたが、このpaddingは内側の余白を調整するものである。</br>
指定の要素の外側の余白を調整する場合は`margin`を用いる。</br>

```html
<style>
  p {
    border: dotted #008080;
    margin: 30px;
  }
</style>
```
</br>

***
</br>

### 2-5_レスポンシブデザインにしよう
ここではBootstrapのコンテナという機能を使って、PCでもスマホでも表示が崩れにくいレスポンシブデザインを導入してみよう。</br>

- **レスポンシブデザインとは**</br>
  レスポンシブデザインとは、スマホやタブレット・PCなどサイズが異なるディスプレイでも、単一のHTMLファイルで、最適なデザインで表示する技術です。</br>
  縦持ちで細長いディスプレイのスマホと、大きな画面のPCでは、最適なレイアウトが違っています。</br>
  レスポンシブデザインでは、これを単一のHTMLで自動的に表示し分けます。</br>
</br>

それではコンテナを追加してみよう。
```php
// public_html/basic02-05.html
<body>
  <!-- 下記のdivタグを追加 -->
  <div class='container'>
    <h1>吾輩は猫である。</h1>
    <p class="lead">名前はまだない。</p>
    <p>どこで生れたかとんと見当がつかぬ。何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれは書生という人間中で一番獰悪な種族であったそうだ。</p>
    <a class="btn btn-primary" href="#">OK</a>
  </div>

  <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>
</body>
```
これで各表示サイズに合わせて余白を入れる事ができるようになった。(表示が広いと広い余白。表示が狭いと狭い余白。)</br>
次に、styleに調整を加えてページをさらに見やすくする。</br>

```html
<!-- public_html/basic02-05.html -->

  <style>
    body {
      padding-top: 50px;
      background-color: lightgray;
    }
    /* 下記のCSSを追加 */
    .starter-template {
      padding: 40px 15px;
      background: white;
    }
  </style>
</head>

<body>
  <div class='container'>
    <!-- 下記のdivタグを追加 -->
    <div class='starter-template'>
      <h1>吾輩は猫である。</h1>
      <p class="lead">名前はまだない。</p>
      <p>どこで生れたかとんと見当がつかぬ。何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれは書生という人間中で一番獰悪な種族であったそうだ。</p>
      <a class="btn btn-primary" href="#">OK</a>
    </div>
  </div>
```
これでコンテナ内のテキスト表示されている部分(div class=starter-container)にCSSが適用され、テキスト部分が見やすくなった。</br>
</br>

* styleタグの中でclass属性にプロパティ指定をする際は、**セレクタの前に.(ドット)をつける。**</br>
</br>

***
</br>

### 2-6_Bootstrapのグリッドシステムを理解しよう
* **Bootstrapのグリッドシステムとは**</br>
  表示サイズに合わせて水平に均一に分割された表示サイズを変更し、表示できなくなると自動的に縦積みになるシステム。</br>
</br>

今回はグリッドを用いて、表示エリアを縦の2行(row)、下の行を横の3列(column)に分ける。</br>
Bootstrapにおいては表示の横幅を12個に分けて、その中から各列が何個使うかを指定する。</br>
たとえば前述の下の行を横の3列として使う場合は、各列グリッドを4個ずつ使う事になる。</br>
指定の方法はhtml上でclass属性として指定していく。</br>
それではやってみよう。</br>
</br>
まず、行と列のclassを追加する。最初は分割せずに12個全部使う1行になるように記述する。</br>
まず上下の2行(row)を記述。</br>

```html
<!-- public_html/basic02-06.html -->
<body>
  <div class="container">
    <div class="starter-template">
      <!-- 下記を2行のdiv(rowとcol-sm-12)を追記 -->
      <div class='row'>
        <div class='col-sm-12'>
          <h1>吾輩は猫である。</h1>
          <p class="lead">名前はまだない。</p>
          <a class="btn btn-primary" href="#">OK</a>
        </div>
      </div>
      <!-- テキスト部分も同様に追記 -->
      <div class='row'>
        <div class='col-sm-12'>
          <h2>どこで生れたか</h2>
          <p>とんと見当がつかぬ。何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれは書生という人間中で一番獰悪な種族であったそうだ。</p>

          <h2>この書生というのは</h2>
          <p>
            時々我々を捕えて煮て食うという話である。しかしその当時は何という考もなかったから別段恐しいとも思わなかった。ただ彼の掌に載せられてスーと持ち上げられた時何だかフワフワした感じがあったばかりである。書生の顔を見たのがいわゆる人間というものの見始であろう。
          </p>

          <h2>掌の上で少し落ちついて</h2>
          <p>書生の顔を見たのがいわゆる人間というものの見始であろう。この時妙なものだと思った感じが今でも残っている。第一毛をもって装飾されべきはずの顔がつるつるしてまるで薬缶だ。</p>
        </div>
      </div>
    </div>
  </div>
  <!-- /.container -->
```
ここで動作確認を行っても得に見た目に変化はない。</br>
次に列(column)を3分割にしてみる。</br>

```html
<!-- public_html/basic02-06.html -->
      <div class='row'>
        <!-- 下記をcol-sm-12から4に変更し、各段落(h2)ごとに記述 -->
        <div class='col-sm-4'>
          <h2>どこで生れたか</h2>
          <p>とんと見当がつかぬ。何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれは書生という人間中で一番獰悪な種族であったそうだ。</p>
        </div>
        <div class='col-sm-4'>
          <h2>この書生というのは</h2>
          <p>
            時々我々を捕えて煮て食うという話である。しかしその当時は何という考もなかったから別段恐しいとも思わなかった。ただ彼の掌に載せられてスーと持ち上げられた時何だかフワフワした感じがあったばかりである。書生の顔を見たのがいわゆる人間というものの見始であろう。
          </p>
        </div>
        <div class='col-sm-4'>
          <h2>掌の上で少し落ちついて</h2>
          <p>書生の顔を見たのがいわゆる人間というものの見始であろう。この時妙なものだと思った感じが今でも残っている。第一毛をもって装飾されべきはずの顔がつるつるしてまるで薬缶だ。</p>
        </div>
```
これで下の行rowが3分割の列columnになった。</br>
</br>

最後に見出しの箇所をより目立つように編集する。</br>
そうするために`jumbotron`クラスを指定する。</br>

```html
<!-- public_html/basic02-06.html -->
<body>
  <div class="container">
    <div class="starter-template">
      <div class='row'>
        <div class='col-sm-12'>
          <!-- 下記を追記 -->
          <div class='jumbotron'>
            <h1>吾輩は猫である。</h1>
            <p class="lead">名前はまだない。</p>
            <a class="btn btn-primary" href="#">OK</a>
          </div>
```
jumbotronクラスを指定するだけで用意されたスタイルを適用する事ができる。</br>
</br>

**備考**：`col-sm-*`の箇所が合計12にならない際、12より大きい数字の際は次の段に繰り下げられ、少ないときは余白が追加されて表示される。</br>

