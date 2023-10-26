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

 ##  10月26日
 ```html
 <section>
  <h1>犬のギャラリー</h1>
  <div class="card1">
    <h2>柴犬の散歩</h2>
    <p>雨だったけど、散歩に連れて行った</p>
  </div>
  <div class="card2">
    <h2>秋田犬の寝顔</h2>
    <p>普段は不細工だけど、寝顔はかわいい</p>
  </div>
  <img src="images/dog001.png" alt="柴犬" id="pochi"
class="shibaDog" />
  <img src="images/dog002.png" alt="秋田犬" id="hachiko"
class="akitaDog" />
</section>
<script>
  //ここに記述していきます
  //柴犬と秋田犬の画像を取得
  const pochi = document.querySelector('#pochi');
  const hachiko = document.querySelector("#hachiko");
  //柴犬カードに柴犬の画像（変数）を挿入する
  const pochisCard = document.querySelector(".card1");
  pochisCard.appendChild(pochi);
  //秋田犬カードに秋田犬の画像を挿入する
  const hachikoCard = document.querySelector(".card2");
  hachikoCard.appendChild(hachiko);
</script>
<script>
  //両方とも秋田犬にする。
  const shibainu = document.querySelector(".sibaDog");
  shiba.setAttribute("src", "imges/dog002.png");
  //Attributeは属性という意味
</script>
 ```

 ```html
 <button id="btn" onclick="alert('クリックされました！')">ハン
ドラを起動する</button>
<button id="nonFunc">関数を使わない</button>
<script>
    const btn = document.querySelector("#btn");
    console.log(btn);
    //感想を定義
    function showMessage() {
        alert("イベントが発生しました。")
    }
    //イベント
    //何を何をしたら、どうなる。
    //「ボタン」に「クリック」したら、「アラートが出る」
    btn.addEventListener("click", showMessage);
    //加える＋イベント＋リスト　
    //関数を使わない
    const nonFuncBtn = document.querySelector("#nonFunc");
    nonFuncBtn.addEventListener("click", function () {
        alert("関数を使わないボタンをクリック");
    });
    //例）「ブラウザで発生する主なイベント」から"resize"（サイズが
変更する）タイミングで console に文字が発生するようにします。
    //resizeは、DOM内にはありませんのでwindowで取得します。
    window.addEventListener("resize", function () {
        //ここに処理を書きます。
        console.log("サイズが変わりました。");
    });
</script>```

```html
<p class="text"><span>色の名前</span>です。</p>
<button class="red">赤色</button>
<button class="blue">青色</button>
<button class="yellow">黄色</button>
<script>
    //文字の色を変えてみましょう。
    //ボタンを取得する
    const redBtn = document.querySelector(".red");
    const blueBtn = document.querySelector(".blue");
    const yellowdBtn = document.querySelector(".yellow");
    //文字を取得する
    const text = document.querySelector(".text");
    const textSpan = document.querySelector(".text span")
    //ボタンにClikイベントを設定する。
    redBtn.addEventListener("click", function () {
        console.dir("text");
        text.style.color = "red";
        textSpan.fontSize = "50px"
        textSpan.innerText = "赤色"
    })
    //青
    blueBtn.addEventListener("click", function () {
        console.dir("text");
        text.style.color = "blue";
        textSpan.innerText = "青色"
    })
    //黄色
    yellowdBtn.addEventListener("click", function () {
        console.dir("text");
        text.style.color = "yellow";
        textSpan.innerText = "黄色"
    })
</script>
<script>
    //スクロールされるたびにconsoleに「スクロールされました」と表示
されるプログラムを書いてください。
    //windowのしごとです。
    window.addEventListener("scroll", function () {
        console.log("スクロールされました。")
    })
</script>```

```html
<style>
    .redText {
        color: red;
    }
    .bigText {
        font-size: 25px;
    }
</style>

<p><span>JavaScript</span>（ジャバスクリプト）とは、プログラミン
グ言語のひとつである。</p>
<button class="redder">赤くなる</button>
<button class="bigger">大きくなる</button>
<script>
    //element.setAttribute("class","??")
    const text = document.querySelector("p span");
    const btnRed = document.querySelector("redder");
    const btnBig = document.querySelector("digger");
    //赤くなるイベント
    btnRed.addEventListener("click", function () {
        text.setAttribute("clas", "redText");
    })
    //大きくなるイベント
    btnBig.addEventListener("click", function () {
        text.setAttribute("class", "bigText");
    })
</script>```
