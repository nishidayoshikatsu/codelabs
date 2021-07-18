author: Yoshikatsu
summary: Webアプリケーション開発体験講座「ToDoアプリを作ってみよう！」
id: todo-web-app
categories: webapp
environments: Web
status: Published
feedback link: https://github.com/nishidayoshikatsu/codelabs/issues
analytics account:

# Webアプリケーション開発体験講座「ToDoアプリを作ってみよう！」

## はじめに
Duration: 0:03:00

このCodelabは、2021.07.04, 2021.07.17, 2021.07.18に開催する[【うべスタートアップ×Code for Yamaguchi×Code for Ube】Webアプリケーション開発体験講座「ToDoアプリを作ってみよう！」](https://codeforyamaguchi-handson1.peatix.com/)イベントのワークショップ資料です。

イベントスライドは[こちら](https://docs.google.com/presentation/d/1UrjH4HynMHAi5Fx70gVswZOnKaCZuF9HUfiWOJwmjoQ/edit?usp=sharing)

### 本講座の目的

プログラミングを全くやったことがない方でも以下のことを習得してもらうことが目的です。
* ものづくりの楽しさを知ってもらう
* プログラミングを学んでいけば実際にものづくりが出来ることを実感してもらう
* Webアプリケーション開発の流れがなんとなくわかる

### ToDoアプリ機能要件

* ToDoアイテムを追加できる
* ToDoアイテムを削除できる


### Day1の開発環境について

Day1は、Web上で利用することができる統合開発環境（複数の一般的な開発者用ツールを 1 つのグラフィカル・ユーザー・インタフェース (GUI) で使えるようにしたもの）である[CodeSandbox](https://codesandbox.io/)を利用します。

詳細な利用方法は、[Day1: 環境構築](https://nishidayoshikatsu.github.io/codelabs/todo-web-app/index.html#3)で説明します。


※CodeSandboxは、必ずしも会員登録する必要はありませんが、会員登録すればハンズオンのデータが保存できるようになる、複数のプロジェクトを作成できるなどのメリットがあります。
Day2以降は直接はDay1のコードを使わない上、CodeSandboxも利用しない予定なので、会員登録するか否かは参加者の皆様のご判断に任せます。

## Day1: プログラミング基礎
Duration: 0:10:00

それでは、プログラミング

### プログラミングとは？

プログラミング = コンピュータにわかる言葉で命令すること。

コンピュータにわかる言葉 = プログラミング言語

プログラミング言語はたくさんある
→目的によって選択肢が絞られる。

* JavaScript
* Python
* Java
* Ruby
* PHP
* C
* C++
* C#
* Swift
* Kotlin
* Dart  
etc...

### Webアプリケーションとは？

動的なサイトのこと = ユーザーごとに表示内容が異なる

例）ショッピングサイト、動画視聴サイトなど

### HTML/CSS, JavaScriptの違い

* HTML: 部品と構造
* CSS: デザイン
* JavaScript: 動き

## Day1: 環境構築
Duration: 0:20:00

1. [CodeSandbox](https://codesandbox.io/)にアクセスし、Create a Sandboxボタンを押す
2. 画面中央のメニューにて、CreateSandbox、Vanillaを選択
3. デフォルトのコードを以下のものに置き換える

index.html
```html:index.html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello World!</title>
    <meta charset="UTF-8" />
    <link rel="stylesheet" href="src/styles.css" />
  </head>

  <body>
    <div>
      Hello World!
    </div>

    <script src="src/index.js"></script>
  </body>
</html>
```

src/styles.css
```css:src/styles.css
body {
  background-color: lightgray;
}
```

src/index.js
```javascript:src/index.js
console.log("test");
```

これで環境の準備は完了です。
次回のセクションから、実際にコードを書いていきます。
まずは真似しながらでもコピペでも良いので、理解しながら進めていきましょう。

今回は、[FizzBuzz](https://ja.wikipedia.org/wiki/Fizz_Buzz#:~:text=Fizz%20Buzz%EF%BC%88%E3%83%95%E3%82%A3%E3%82%BA%E3%83%BB%E3%83%90%E3%82%BA%E3%80%81,%E3%82%8F%E3%82%8C%E3%82%8B%E8%A8%80%E8%91%89%E9%81%8A%E3%81%B3%E3%81%A7%E3%81%82%E3%82%8B%E3%80%82)という、企業が求める最低限のプログラミング能力があるかを確認するための問題に挑戦してみましょう。

仕様は以下の通りです。1~100の数字を仕様に基づいて全て表示してください。

* 数字（3の倍数でも5の倍数でもない場合）
* Fizz（3の倍数の場合）
* Buzz（5の倍数の場合）
* FizzBuzz（3と5の倍数の場合）

## Day1: HTML/CSSを書いてみよう
Duration: 0:20:00

それでは、まずはHTMLのコードについて説明します。

HTML = HyperText Markup Languageの略です。
通称マークアップ言語と呼ばれ、Webサイトの部品と構造を作るために書かれています。
そして、HTMLタグ（要素）と呼ばれているもので構成されています。

HTMLタグのリファレンスは[こちら](http://www.htmq.com/html/indexm.shtml)にあるので、照らし合わせながら確認してみましょう！

次に、CSSのコードについて説明します。
CSS = Cascading StyleSheetsの略です。
通称スタイルシート言語と呼ばれ、Webサイトのデザインを整えるために書かれています。

CSSの指定の仕方は[こちら](https://developer.mozilla.org/ja/docs/Learn/Getting_started_with_the_web/CSS_basics)にあるので書きながら解説していきます！

ここでは、以下の条件でコードを追加してみましょう！（できたら、色々いじって動かしてみましょう！）
* <h1>タグを追加して、背景をlightblueに。高さは50px、FizzBuzzを表示


```html
<!-- ヒント: bodyの中にh1タグを入れてね -->
<body>
    <h1>FizzBuzz</h1>
</body>
```

```css
h1 {
    background-color: lightblue;
}
```



## Day1: JavaScriptを書いてみよう
Duration: 0:20:00

[参考](https://jsprimer.net/basic/)

### 変数

プログラミング言語には、文字列や数値などのデータに名前をつけることで、繰り返し利用できるようにする変数という機能があります。

```javascript
let a = "ube-startup";
console.log(a);
```

### コメント

コメントはプログラムとして評価されないため、ソースコードの説明を書くために利用されています。

```javascript
let a = "ube-startup"; // aと名前の変数にube-startupという名前の文字列を代入
```

### 条件分岐

if文を使うことで、プログラム内に条件分岐を書けます。

```javascript
let x = 42;
if (x > 10) {
    console.log("xは10より大きな値です");
}
```

複数の条件分岐を書く場合は、if文に続けてelse if文を使うことで書けます。

```javascript
let x = 42;
if (x > 10) {
    console.log("xは10より大きな値です");
} else if(x < 10) {
    console.log("xは10より大きな値です");
}
```

if文とelse if文では、条件に一致した場合の処理をブロック内に書いていました。 一方で条件に一致しなかった場合の処理は、else文を使うことで書けます。

```javascript
let num = 1;
if (num > 10) {
    console.log(`numは10より大きいです: ${num}`);
} else {
    console.log(`numは10以下です: ${num}`);
}
```

### ループと反復処理

プログラミングにおいて、同じ処理を繰り返すために同じコードを繰り返し書く必要はありません。 ループやイテレータなどを使い、反復処理として同じ処理を繰り返し実行できます。

for文は繰り返す範囲を指定した反復処理を書くことができます。

```javascript
for (初期化式; 条件式; 増分式) {
    実行する文;
}
```

```javascript
let total = 0; // totalの初期値は0
// for文の実行フロー
// iを0で初期化
// iが10未満（条件式を満たす）ならfor文の処理を実行
// iに1を足し、再び条件式の判定へ
for (let i = 0; i < 10; i++) {
    total += i + 1; // 1から10の値をtotalに加算している
}
console.log(total); // => 55
```

それでは、先程の仕様に基づいてFizzBuzzをconsoleに表示させてみましょう！

* 数字（3の倍数でも5の倍数でもない場合）
* Fizz（3の倍数の場合）
* Buzz（5の倍数の場合）
* FizzBuzz（3と5の倍数の場合）

```javascript
// ヒント
for (let i = 1; i <= 100; i++) {
    //条件文を書く
}
```

お疲れ様でした！

## Day2, 3の開発環境のダウンロード

Day2, 3は開発環境としてVSCodeを利用します。

VSCodeは、Microsoft社が提供するエディタです。
プログラミングするのに便利な機能が多く含まれています。
[ここ](https://azure.microsoft.com/ja-jp/products/visual-studio-code/)からダウンロードお願いします。


## Day2: Gitのダウンロード

Gitは、「分散型バージョン管理システム」と呼ばれるツールです。

Gitを使うことで、ソースコードに対して行った変更を複数人で共有し、効率よく開発を進めることができます。

Windowsの人は[ここ](https://gitforwindows.org/)から、Macの人はデフォルトでインストールされているので不要です。

## Day2: Githubのアカウント登録

Githubは、一言で言うと「ソースコード管理サービス」です。

ソースコードの変更履歴の管理や閲覧、バグ追跡機能などを備えており、開発者にとってなくてはならないサービスです。

また、GitHubを使ってソースコードの管理を行っている企業も多数あります。

[こちら](https://github.co.jp/)よりご登録ください。

現在Code for Yamaguchiで運用している[山口県新型コロナウイルス感染症対策サイト](https://yamaguchi.stopcovid19.jp/)も[githubでソースコードを管理](https://github.com/nishidayoshikatsu/covid19-yamaguchi)しています。

## Day2: Gitを使ったバージョン管理の仕方

ローカルリポジトリの内容をリモートリポジトリに送信（アップロード）することを「push」と呼びます。
```
git push
```

ワークツリーとは、実際に作業している場所(ディレクトリ)のことを指します。ここでああでもあい、こうでもないと試行錯誤して開発を進めるわけですね。

そのあとソースコードが完成したら、リポジトリに更新する必要があります。このソースコードの更新作業を「commit」と呼びます。

```
git commit -m "コミットメッセージをここに書く"
```

ここでワークツリーとリポジトリの間には、インデックスというスペースがあります。これはコミットするファイルを準備するところです。ワークツリーからインデックスに登録することを「add」と呼びます。

```
git add
```

### まとめ

1. git addコマンドで、インデックスにコミットしたいファイルを登録する。

2. git commitコマンドで、インデックスにあるファイルを更新する。

3. git pushコマンドで、ローカルリポジトリの内容をリモートリポジトリに送信する

## Day2: Git, Githubワークショップ

まずは、[ここ](https://github.com/nishidayoshikatsu/todo-handson)より今回のハンズオンで利用するコードを以下のコマンドを実行してpc内に環境をコピーしましょう。

```
git clone https://github.com/nishidayoshikatsu/todo-handson.git
```

次に、自分の作業の変更を管理するための場所を作るために、branchを作りましょう。

```
git branch yoshikatsu
```

そして、README.mdを変更して変更履歴を保存しましょう！

```
git add README.md
git commit -m "README.mdを変更”
```

次に、githubでリポジトリを新規作成しましょう！
できたら、コマンドリモートリポジトリにpushしましょう！

```
git remote add origin url
git push -u origin main
```

これで自分のコード履歴をリモートで管理できるようになりました！

## Day2: コードを変更してToDoアプリを作っていこう

最終的なデザインは[こちら](https://www.figma.com/file/XvpbfsVDFliraLAqwf0exp/ToDoApp?node-id=0%3A1)

1. 先ほどgit cloneしたフォルダをVSCodedeで開きましょう。
2. VSCodeの拡張をインストール
3. ToDoに書かれている内容を実装！

本日はここまででokです！

## Day3: 本日作り込んでいく部分

* HTMLで入力フォームを追加
* 削除ボタンの実装
* デプロイ
* レスポンシブ対応
* その他改善・修正

※LINE APIとの連携は、時間が足りなさそうなので説明を省かせてもらいます。
興味ある方は以下のチュートリアルをやってみてください。

https://developers.line.biz/ja/docs/messaging-api/nodejs-sample/

