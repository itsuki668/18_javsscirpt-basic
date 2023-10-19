## 10 月 5 日

- インターネットの基本について理解する。
- Web の基本的な仕組みを理解する。
- Web サーバーの役割について理解する。
- 開発環境の構築
- JavaScript を書く場所

### JavaScript を書く場所

1. HTML ファイルの中
1. 外部 JS ファイルの中
1. ブラウザのコンソール

基本は、外部 JS ファイルを読み込むが、HTML 内に各場合は、`</body>`の上に書く。

```html
<!doctype html>
<html lang=ja>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>演習</title>
</head>
<body>
    <script>
</script>
</body>
</html>
```

### フロントエンドロードマップ

フロントエンドエンジニアに必要なスキルの[ロードマップ](https://roadmap.sh/frontend)がある。



##  10月１２日

- リテラルと演算子

### 文字列の計算

```js
///文字列の連結
cosole.log("ABC" + "DEF"); //文字列＋文字列
cosole.log("円周率は" + 3.14 + "です"); //文字列＋数値＋文字列
cosole.log("計算結果：" + 123 + 456); //文字列＋数値＋数値
console.log(123 + 456 + "となりました。") //数値＋数値＋文字列
cosole.log("計算結果：" + (123 + 456)); //文字列＋（数値＋数値）
cosole.log("2" - 1);//文字列ー数値
cosole.log("2" * 2);//文字列*数値
cosole.log("2" / 3);//文字列/数値
```
### 変数の宣言・代入
```js
let a; //変数の宣言
a = 10; //値の代入(数値型)
cosole.log(a);
a = "Hello"; //値の再代入（文字列型）
/*cosole.log(a);
let a = "World"; //変数の宣言と代入を同時に行っています。更に再宣言なので、エラーとなります。
*/
//定数の宣言・代入
const PI = 3.14;
cosole.log(PI)
//再代入
/*PI = 3.1415926535
const PI;
*/
```
### 複合演算子
```js
let n = 5;
n = n + 2;
cosole.log(n); //7
let n2 = 5;
n2 += 2; //複合代入演算子　n2 = n2 + 2と同じ。　
cosole.log(n2);
//インクリメント
let n3 = 5;
n3++;//インクリメント　１足す
```

### ul要素を取り入れ
```js
const element = document.querySelector("ul");
console.log(element);

//selectorってCSSのセレクターなので、
const element2 = document.querySelector("#fruitslist");
console.log(element2);

//classもいける？
const element3 = document.querySelector(".listbox_list");
console.log(element3);

//新しい要素を作る。
const lilast = document.createElement("li");

console.dir(lilast); //dirに変更。オブジェクトの中身が見れる。
lilast.textContent = "メロン";
console.log(lilast);
```

##  10月１９日

- for文（繰り返し文）
- コレクション（配列）

### lastに２つの文字を加える

 ```html
 <h1>果物の種類</h1>
<ul id="fruitslist" class="listbox__list">
    <li>りんご</li>
    <li>みかん</li>
    <li>バナナ</li>
</ul>
<!--リストを操作するDOM操作のスクリプト-->
<script>
    //メロンを加えたい。
    //ul要素を取り入れる。
    const element = document.querySelector("ul");
    console.log(element);
    //selectorってCSSのセレクターなので、
    const element2 = document.querySelector("#fruitslist");
    console.log(element2);
    //classもいける？
    const element3 = document.querySelector(".listbox_list");
    console.log(element3);
    //新しい要素を作る。
    const lilast = document.createElement("li");
    console.dir(lilast); //dirに変更。オブジェクトの中身が見れる。
    lilast.textContent = "メロン";
    console.log(lilast);
    //リストの最後に追加する。↑<li>メロン</li>を変数element内の<ul></ul>に追加する。
    //メロンの下にいちごを加える
    const lilast2 = document.createElement("li");
    element.appendChild(lilast);
    lilast2.textContent = "いちご";
    element.appendChild(lilast2);
</script>
 ```

 ### for文を使い繰り返し文を作る
 ```js
 for (let i = 0; i < 4; i++) {
    //繰り返しの処理を入れていく。
    //0~3を表示したい。
    console.log(i);
}
const name_list = ["松田", "田中", "中山", "山本", "本田"]
console.log(name_list);
//山本がほしい。
console.log(name_list[3]);
for (i = 0; i < 5; i++) {
    console.log(i);
    console.log(name_list[i]);
}
 ```

### for文を使い７の九九を実行

 ```js
 for (let i = 0; i < 9; i++) {
    console.log(i)
    console.log(i + 1);
    console.log(`7 × ${i + 1} = ${7 * (i + 1)}`);
}
 ```

 ### lastからulのなかの要素を出しulのなかに新しい要素を入れる
 ```html
 <h1>人気フルーツ一覧</h1>
<ul id="fruitslist" class="listbox__list"></ul>

<script>
  //ulの中に果物一覧を一度に入れたい。
  //配列fruitsを宣言・値を代入
  const fruits = ["りんご", "もも", "バナナ"];
  //ulをJavaScript空間に引きずり込む
  const element = document.querySelector("#fruitslist li a");
  console.log(element);
  //fruitsの要素数文だけfor文で回す。
  for (let i = 0; i < fruits.length; i++) {
    //liを創出する。
    const lilast = document.createElement("li");
    //liに値（果物→配列fruitsの中にある。）を代入
    console.log(fruits[i]);//りんご、もも、バナナが取れる。
    //創出したliの内容に果実を代入
    lilast.textContent = fruits[i];
    //element(ul)の中に最後に追加
    element.appendChild(lilast);
  }
</script>
 ```
