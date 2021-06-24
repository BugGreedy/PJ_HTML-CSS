## HTML/CSS入門編3: HTML要素を学ぼう(全6回)
(全6回)

### 目次
[3-1_画像とリンクを載せよう](#3-1_画像とリンクを載せよう)</br>
[3-2_リストとナビゲーションバーを追加しよう](#3-2_リストとナビゲーションバーを追加しよう)</br>
[3-3_テーブルを表示しよう](#3-3_テーブルを表示しよう)</br>
[3-4_基本的なフォームを作ろう](#3-4_基本的なフォームを作ろう)</br>
[3-5_フォームにパーツを追加しよう](#3-5_フォームにパーツを追加しよう)</br>
[3-6_グリッドでフォームを作ろう](#3-6_グリッドでフォームを作ろう)</br>



</br>

***
</br>

### 3-1_画像とリンクを載せよう
ここではWebページに画像を表示してみる。</br>
```html
<!-- public_html/basic03.html -->
<body>
  <div class="container">
    <div class="starter-template">
      <h1>吾輩は猫である。</h1>
      <p class="lead">名前はまだない。</p>
      <!-- 下記を追記 -->
      <img src='https://paiza-webapp.s3.amazonaws.com/files/learning/photo_cat_1024.jpg'>
```
これで画像の表示はできる。</br>

* `<img src='*'>`：画像の表示にはimgタグを用いる。`src`(ソース)という属性は表示する画像のアドレスを指定する。</br>
</br>

先程の画像表示の方法だと、レスポンシブ対応になっておらずスマホなどで表示した際に画像がはみ出てしまう。</br>
Bootstrapを使うと、ウィンドウサイズに対して画像のサイズを自動調整したり、中央に表示したりなどができる。</br>
</br>
ではやってみよう。</br>

```html
<!-- public_html/basic03.html -->
<body>
  <div class="container">
    <div class="starter-template">
      <h1>吾輩は猫である。</h1>
      <p class="lead">名前はまだない。</p>
      <!-- 下記にclass属性を追加 -->
      <img class='img-responsive center-block' src='https://paiza-webapp.s3.amazonaws.com/files/learning/photo_cat_1024.jpg'>
```
これで表示サイズに応じて画像サイズが代わり、同時にセンター表示を常に行えるようになった。</br>
</br>

次にリンクを貼ってみる。</br>
ここではWikipediaの夏目漱石のページにリンクを貼ってみる。</br>

```html
<!-- public_html/basic03.html -->
<p>
  どこで生れたかとんと見当がつかぬ。何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれは書生という人間中で一番獰悪な種族であったそうだ。この書生というのは時々我々を捕えて煮て食うという話である。しかしその当時は何という考もなかったから別段恐しいとも思わなかった。ただ彼の掌に載せられてスーと持ち上げられた時何だかフワフワした感じがあったばかりである。
</p>
<a class="btn btn-primary" href="#">OK</a>
<!-- 下記を追記 -->
<a href='https://ja.wikipedia.org/wiki/%E5%A4%8F%E7%9B%AE%E6%BC%B1%E7%9F%B3' target="_blank">夏目漱石wiki</a>
```
</br>

* リンクを設置する際はa(アンカー)タグを用いる。</br>
  href属性はリンクのアドレスを指定する。</br>
  target属性は同じページで遷移するか、別ベージでリンクを開くかを指定する。`_blank`とすると別ページで開き、この属性を省略すると同ページからリンクへ遷移する。</br>
</br>

また、現在ダミーで設置しているOKボタンもリンクを設定する事が可能。</br>

```html
<!-- 下記を編集 -->
<a class="btn btn-primary" href="http://paiza.jp/" target='_blank'>OK</a>
```
</br>

また、画像もリンクを設定する事が可能。</br>
基本的にはaタグの通常はテキストにする箇所をimgタグの部位にする事で可能。</br>
```html
<!-- 下記にリンクを追加 -->
<a href='https://ja.wikipedia.org/wiki/%E5%A4%8F%E7%9B%AE%E6%BC%B1%E7%9F%B3' target='_blank'><img class='img-responsive center-block' src='https://paiza-webapp.s3.amazonaws.com/files/learning/photo_cat_1024.jpg'></a>
```
</br>

***
</br>

### 3-2_リストとナビゲーションバーを追加しよう
ここではWebページに箇条書きのリストを追加する。</br>
また、Bootstrapを用いて見栄えの良いナビゲーションバーを追加する。</br>
このナビゲーションバーには同ページ内でのジャンプができる機能をもたせる。</br>
</br>

まず、ページ全体の見通しが分かりやすくなるように見出しを追加する。
```html
<!-- public_html/basic03-02.html -->
      <p>
        どこで生れたかとんと見当がつかぬ。何でも薄暗いじめじめした所でニャーニャー泣いていた事だけは記憶している。吾輩はここで始めて人間というものを見た。しかもあとで聞くとそれは書生という人間中で一番獰悪な種族であったそうだ。この書生というのは時々我々を捕えて煮て食うという話である。しかしその当時は何という考もなかったから別段恐しいとも思わなかった。ただ彼の掌に載せられてスーと持ち上げられた時何だかフワフワした感じがあったばかりである。
      </p>
      <!-- 下記を追記 -->
      <h2 id='list'>動物リスト</h2>
      <a class="btn btn-primary" href="#">OK</a>
```
</br>

* 見出しについて：
  ページの表題にh1タグを用いて、後はその見出しによって使う見出しサイズを区別する。
  ```html
  <h1>と</h1>の間が、表題になる。
  <h2>と</h2>の間が、大見出しになる。
  <h3>と</h3>の間が、中見出しになる。
  <h4>と</h4>の間が、小見出しになる。
  ```
</br>

次にこの見出しの下にリストを追加する。
```html
<h2 id='list'>動物リスト</h2>
<ul>
  <li>ねこ</li>
  <li>いぬ</li>
  <li>うさぎ</li>
</ul>
```
これでリストを表示できた。</br>

ここにBootstrapを追加して見た目を整える。
```html
<body>
<nav class="navbar navbar-inverse navbar-fixed-top">
	<div class="container">
		<div class="navbar-header">
			<button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="faaria-controls="navbar">
				<span class="sr-only">Toggle navigation</span>
				<span class="icon-bar"></span>
				<span class="icon-bar"></span>
				<span class="icon-bar"></span>
			</button>
			<a class="navbar-brand" href="#">Project Nyaan</a>
		</div>
		<div id="navbar" class="collapse navbar-collapse">
			<ul class="nav navbar-nav">
				<li class="active"><a href="#">Home</a></li>
				<li><a href="#list">List</a></li>
				<li><a href="">Table</a></li>
			</ul>
		</div>
	</div>
</nav>
<div class="container">
```
これでナビゲーションバーが追加できた。</br>
</br>

このナビゲーションバーの中の
```html
<ul class="nav navbar-nav">
	<li class="active"><a href="#">Home</a></li>
	<li><a href="#list">List</a></li>
	<li><a href="">Table</a></li>
</ul>
```
という箇所について、`<li><a href="#list">List</a></li>`というリストの1つは先程追加したリストの`<h2 id='list'>動物リスト</h2>`へのリンクとなっている。</br>
このようにページ内のリンクはid名に対してリンクを貼ることができる。</br>
href属性の値を`#id名`とする事でリンクの指定ができる。</br>
このとき`href='#'`のように#だけを指定した場合はページの一番上へのリンクとなる。</br>
</br>

***
</br>

### 3-3_テーブルを表示しよう
ここでは表(テーブル)を表示し、リスト同様にBootstrapを用いて見た目を整える。</br>
まず見出しを追加する。
```html
<!-- public_html/basic03-03.html -->
  </ul>
  <!-- 下記の見出しを追加 -->
  <h2 id='table'>猫テーブル</h2>
  <a class="btn btn-primary" href="#">Topに戻る</a>
</div>

<!-- ついでに上部のナビゲーションバーのtableボタンにリンクをつける。 -->
<div id="navbar" class="collapse navbar-collapse">
  <ul class="nav navbar-nav">
    <li class="active"><a href="#">Home</a></li>
    <li><a href="#list">List</a></li>
    <!-- 下記のリンクに#tableを追記 -->
    <li><a href="#table">Table</a></li>
  </ul>
</div>
```
これで見出しとリンクはOK。</br>
次にテーブルを作っていく。

```html
<h2 id='table'>猫テーブル</h2>
<table>
  <thead>
    <tr>
      <th>#</th>
      <th>名前</th>
      <th>特徴</th>
      <th>住所</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>たま</td>
      <td>靴下</td>
      <td>東京都武蔵野市</td>
    </tr>
    <tr>
      <td>2</td>
      <td>ミケ</td>
      <td>三毛</td>
      <td>東京都千代田区</td>
    </tr>
    <tr>
      <td>3</td>
      <td>トラ</td>
      <td>シマ</td>
      <td>兵庫県西宮市</td>
    </tr>
    <tr>
      <td>4</td>
      <td>クーガー</td>
      <td>トラの兄弟</td>
      <td>兵庫県西宮市</td>
    </tr>
  </tbody>
</table>
```
これでシンプルな表の表示ができるようになった。</br>
続いてここにBootstrapのデザインを追加する。</br>

```html
<h2 id='table'>猫テーブル</h2>
<!-- tableタグにclassを追加する -->
<table class='table table-striped' >
```
これで先程の表にデザインが追加された。</br>
</br>

***
</br>

### 3-4_基本的なフォームを作ろう
ここでは会員登録や問い合わせに利用できるフォームを作ってみる。</br>
まずは簡素な1行フォームを追加してみる。

```html
<!-- public_html/basic03-04.html -->
<h2 id="form">猫フォーム</h2>
<!-- 下記に1行フォームの内容を記載 -->
<form action='#' method='post'>
  <label for='title'>タイトル</label>
  <input type='text' name='title' id='title'>
  <button type='submit'>送信する</button>
</form>
```
</br>

**フォームについて**
* formタグ：`action`で呼び出すプログラムを指定、`method`で呼び出し方式を指定。</br>
* labelタグ：入力欄の隣に表示される見出しになる。
* inputタグ：入力欄を指定する。`type`で入力欄のタイプを指定する。`text`でテキストボックスを表示する。</br>
  `name`はフォームのデータを送信する時のデータの名前を指定する。</br>
  ※labelタグの`for`とinputタグの`id`は対になるので同じ値を記述する。</br>
* buttonタグ：送信ボタンを指定する。</br>
</br>

次にフォームにBootstrapのデザインを追加する。
```html
<h2 id="form">猫フォーム</h2>
<form action='#' method='post'>
  <!-- 下記divを追記 -->
  <div class='form-group'>
    <label for='title'>タイトル</label>
    <!-- inputにclassを追記 -->
    <input type='text' class='form-control' name='title' id='title'>
  </div>
  <button type='submit'>送信する</button>
</form>
```
これでフォームにBootstrapのデザインを追加できた。</br>
入力欄が画面の横いっぱいに入力欄が広がったと同時にレスポンシブデザイン対応となった。</br>
</br>

***
</br>

### 3-5_フォームにパーツを追加しよう
ここではフォームに複数行の入力欄や、プルダウンメニューなどのパーツを追加してみる。</br>
</br>

まずはBootstrapのない、通常のフォームのパーツを追加していく。</br>
```html
<!-- public_html/basic03-05.html -->
<h2 id="form">猫フォーム</h2>
<form action="#" method="post">
  <div class="form-group">
    <label for="title">タイトル</label>
    <input type="text" class="form-control" name="title" id="title">
  </div>
  <!-- 下記を追記 -->
  <label for='message'>メッセージ</label>
  <textarea name='message' id='message' rows='3'></textarea>
  <!-- ここまで -->
  <button type="submit">送信する</button>
</form>
```
これでとりあえずの3行の入力欄を作成できた。</br>

ここにBootstrapのテーマを追加し、見ためを整える.
```html
<h2 id="form">猫フォーム</h2>
<form action="#" method="post">
  <div class="form-group">
    <label for="title">タイトル</label>
    <input type="text" class="form-control" name="title" id="title">
  </div>
  <!-- 下記を追記 -->
  <div class='form-group'>
  <label for='message'>メッセージ</label>
  <!-- 下記にclass属性を追加 -->
  <textarea class='form-control' name='message' id='message' rows='3'></textarea>
  </div>
  <button type="submit">送信する</button>
</form>
```
これでinputタグと同様にレスポンシブのテーマが反映された。</br>
</br>

次にプルダウンリストを追加する。
```html
<h2 id="form">猫フォーム</h2>
<form action="#" method="post">
  <div class="form-group">
    <label for="title">タイトル</label>
    <input type="text" class="form-control" name="title" id="title">
  </div>
  <div class='form-group'>
  <label for='message'>メッセージ</label>
  <textarea class='form-control' name='message' id='message' rows='3'></textarea>
  </div>
  <!-- 下記を追記 -->
  <label for='select'>好みの猫</label>
  <select name='select' id='select'>
    <option>タマ</option>
    <option>ミケ</option>
    <option>トラ</option>
  </select>
  <!-- ここまで -->
  <button type="submit">送信する</button>
</form>
```
これでプルダウンリストが追加できた。</br>
次にこれまで同様にBootstrapのテーマを反映させる。</br>

```html
<h2 id="form">猫フォーム</h2>
<form action="#" method="post">
  <div class="form-group">
    <label for="title">タイトル</label>
    <input type="text" class="form-control" name="title" id="title">
  </div>
  <div class='form-group'>
  <label for='message'>メッセージ</label>
  <textarea class='form-control' name='message' id='message' rows='3'></textarea>
  </div>
  <!-- 下記を追記 -->
  <div class='form-group'>
  <label for='select'>好みの猫</label>
  <!-- 下記にclassを追加 -->
  <select class='form-control' name='select' id='select'>
    <option>タマ</option>
    <option>ミケ</option>
    <option>トラ</option>
  </select>
  </div>
  <button type="submit">送信する</button>
</form>
```
これでOK。</br>
</br>

***
</br>

### 3-6_グリッドでフォームを作ろう
ここではBootstrapのグリッドを使ってフォームのレイアウトを整理する。</br>
構成は下記の通り。</br>
</br>

* 行(row)の項目
1. input:name
2. textarea:message
3. select:select
4. button:submit</br>
</br>

* 列(column)のWidthの比率
  - ラベル:2
  - 入力欄:10</br>
</br>

```html
<!-- public_html/basic03-06.html -->
<h2 id="form">猫フォーム</h2>
<!-- class属性を追加 -->
<form class='form-horizontal' action="#" method="post">
  <div class="form-group">
    <!-- class属性を追加 -->
    <label class='col-sm-2 control-label' for="title">タイトル</label>
    <!-- divタグを追加 -->
    <div class='col-sm-10'>
      <input type="text" class="form-control" name="title" id="title">
    </div>
  </div>
  <!-- 残りの項目も同様に編集 -->
  <div class="form-group">
    <label class='col-sm-2 control-label' for="message">メッセージ</label>
    <div class='col-sm-10'>
      <textarea class="form-control" rows="3"></textarea>
    </div>
  </div>
  <div class="form-group">
    <label class='col-sm-2 control-label'for="select">好みのネコ</label>
    <div class='col-sm-10'>
      <select class="form-control" name="select" id="select">
        <option>タマ</option>
        <option>ミケ</option>
        <option>トラ</option>
      </select>
    </div>
  </div>
  <!-- 送信ボタンにはラベルがないので下記のように記述する -->
  <div class='form-group'>
    <div class='col-sm-offset-2 col-sm-10'>
      <button type="submit">OK</button>
    </div>
  </div>
</form>
```
