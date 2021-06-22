## HTML/CSS入門編2: CSSの基礎を学ぼう (全6回)

### 目次
[2-1_CSSの基本形を理解しよう](#2-1_CSSの基本形を理解しよう)</br>
[2-2_CSSの色指定を理解しよう](#2-2_CSSの色指定を理解しよう)</br>
[2-3_CSSのフォント指定を理解しよう](#2-3_CSSのフォント指定を理解しよう)</br>
[2-4_CSSのレイアウト指定を理解しよう](#2-4_CSSのレイアウト指定を理解しよう)</br>


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
  また特定の端末にしか使用されていないフォントを使用しないようにする。</br>
  とはいえ、どの端末で表示されるか分からないから`font-family`は複数のフォントを指定するのが望ましい。</br>
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

### 