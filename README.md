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


##  11月２日
```html
<h1 id="header">ヘッドスピン</h1>
<div class="btnArea">
  <div class="button dancing">Let’sダンス</div>
  <div class="button stop">ストップ</div>
  <div class="button change">ダンサーチェンジ</div>
</div>
<div class="imgArea">
  <img src="images/dance_breakdance_headspin.png" alt="ブレイクダンサーいらすと" />
</div>
<script>
  //ここに記述します。
  const danceingBtn = document.querySelector(".dancing");
  const stopBtn = document.querySelector(".stop");
  const changeBtn = document.querySelector("change");
  const dancer = document.querySelector(".imgArea img");
  danceingBtn.addEventListener("click", function () {
    dancer.setAttribute("class", "dance");
  })
  stopBtn.addEventListener("click", function () {
    dancer.removeAttribute("class",);
  })
  changeBtn.addEventListener("click", function () {
    dancer.setAttribute("src", "images/ballet_woman.png");
  });
</script>```

```html
<h1 class="title">タイトル</h1>
<script>
    //h1_elementの要素を作る
    const h1_element = document.querySelector("h1");
    //確認重要
    console.dir(h1_element);
    //hasAttribute
    const has_result = h1_element.hasAttribute("class");
    console.log(has_result);//ture or fales
    //getAttribute
    const get_result = h1_element.getAttribute("class");
    console.log(get_result);
    //className
    h1_element.className = "siteanme";
    //classlist
    //addは加えたいとき
    h1_element.classList.add("w-full")
    //classlist.remove("class値");//クラスの削除をします。
    h1_element.classlist.remove("sitename");
    //elem.classList.toggle("class"); //クラスが存在する場合は削除します。なければ追加します。
    const body_element = document.body;
    body_element.addEventListener("click", function () {
        body_element.classlist.toggle("red");
    })
    //elem.classList.contains("class"); //クラスをの有無をチェックし、true/falseを返します。
    const contains_result = h1_element.classList.contains("sitename");
    console.log(contains_result);//上で削除しているのでflales
</script>```
```html
<style>
    body {
        width: 100%;
        height: 1000vh;
    }
</style>

<script>
    //カウンターlet counter 0 を使って、ブラウザー内（body）をクリックしたら、consoleに数字が１ずつ加わった数を表示させてみましょう
    const body_element = document.querySelector("body");
    let counter = 0;
    //要素番号は、0,1,2,3,4
    const color_array = ["pink", "blue", "orange", "green", "tomato"];
    //クリックイベント
    body_element.addEventListener("click", function () {
        /*counter = counter + 1;
        counter += 1 //複合演算子*/
        counter++;
        console.log(counter);
        /*style.setAttribute("backgrondColor", "color_array");*/
        body_element.style.backgroundColor = color_array[counter];
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

<p><span>JavaScript</span>（ジャバスクリプト）とは、プログラミング言語のひとつである。</p>
<button class="redder">赤くなる</button>
<button class="bigger">大きくなる</button>
<script>
    //element.setAttribute("class","??")
    const text = document.querySelector("p span");
    const redBtn = document.querySelector(".redder");
    const bigBtn = document.querySelector(".digger");
    //赤くなるイベント
    redBtn.addEventListener("click", function () {
        text.classList.toggle("redText");
        if (text.classList.contains("redBtn")) {
            redBtn.innerText = "赤くなる";
        }
        redBtn.innerText = "もとに戻す";
    })
    //大きくなるイベント
    bigBtn.addEventListener("click", function () {
        text.classList.toggle("bigText");
        if (text.classList.contains("bigBtn")) {
            bigBtn.innerText = "大きくなる";
        }
        digBtn.innerText = "もとに戻す";
    })```

    ##  11月２日
```script
<script>
    const addition = function (a, b) {
        const c = a + b;
        console.log(c)
    }
    addition(30, "6");//306
    const addition2 = function (a, b) {
        const c = a * b;
        return c;//戻り値
    }
    const result = addition2(5, 5);
    console.log(result);
</script>```
```html
<p>ケーキ（450円）の税込価格</p>
<button class="takeOut">テイクアウト</button>
<button class="eatIn">イートイン</button>
<p>税込み価格は、<span class="taxIn"></span>円です。</p>
<script>
    const takeOutBtn = document.querySelector(".takeOut");
    const eatInBtn = document.querySelector(".eatIn");
    const resultRtn = document.querySelector(".taxIn");
    const calculation = function (cake, tax) {
        const result = cake + cake + tax;
        return result;
    };
    takeOutBtn.addEventListener("cick", function () {
        const price = calculation(cake, 0.08);
        result.innerHTML = price;
    });
    eatInBtn.addEventListener("cick", function () {
        const result = calculation(cake, 0.1)
        rersult.innerHTML = price;
    });```
    ```html
    <h1>変数のスコープ</h1>
<script>
    ```html
        <h1>変数のスコープ</h1>
    <script>
        const globalData = "hogehoge";//グローバル変数
        //関数式
        const foobaa = function () {
            const localData = "fugafuga";//ローカル変数
        };
        console.log(globalData);//表示される
        console.log(localData);//ローカルスコープなのでエラー

        const globalData = "hogehoge";//グローバル変数
        const foobaa = function () {
            const globalData = "fugafuga";//ローカル変数なんだけど、グローバルの変数名と同じ
            console.log(globalData);//fugafuga　※ローカル変数は、グローバルよりも優先されるかつ、外にはもれない
        };
        console.log(globalData);//hogehoge ※グローバル変数
        //関数の中だけではなく、｛｝（ブロック）内でしか使えない
        //外に出したいときには
    </script>```
```html
    <h1>変数のスコープ</h1>
    <script>
        // グローバル変数の初期化※再代入可能にするためletを使う。
        let global = "グローバル変数";

        //関数funcの定義
        const func = function () {
            //ローカル変数の初期化
            let local = "ローカル変数";
            //グローバル変数の表示
            console.log(global);
            //ローカル変数の表示
            console.log(local);
            global = "グローバル変数を再代入";

            var global = "グローバル変数を再定義";
            console.log(global);
        }

        if (global) {
            var local2 = "varは関数スコープ";
            let local3 = "letはブロックスコープ";
        }
        //関数funcの実行
        func();
        //グローバル変数の表示
        console.log(global);
        //varは関数スコープなので、if文の外で呼び出せる。
        console.log(local2);
        //letはブロックスコープなので、if文の外で呼び出せない。
        console.log(local3);
    </script>
```
## 12月１４日（木）

```html
<h1>動物のスピード</h1>
<div class="dash">
    <p>START</p>
    <p>GOAL</p>
</div>
<ul>
    <li class="dog">イ　ヌ<span>🐕</span></li>
    <li class="cat">ネ　コ<span>🐈</span></li>
    <li class="horse">ウ　マ<span>🐎</span></li>
    <li class="pig">ブ　タ<span>🐖</span></li>
    <li class="gorilla">ゴリラ<span>🦍</span></li>
</ul>
<button class="startBtn">よーい、ドン！</button>
<script>
    const startBtn = document.querySelector(".startBtn");
    const animalSpeed = [3, 4, 1, 3, 2];
    const animals = document.querySelectorAll("li span");
    // ここに関数animalsRunを作成してください。
    const animalsRun = function (list) {
        for (let i = 0; i < list.length; i++) {
            console.log(animalSpeed[i], list[i])
            list[i].classList.add("run");
            list.style.tarnsitionDuration = animalSpeed[i] +
                "s";
        }
    }
    //startBtn.addEventListener("click", function () {
    //    //animalsRun(animals);
    //    for (let i = 0; i < animals.length; i++) {
    //    }
    //});
    startBtn.addEventListener("click", function () {
        animalsRun(animals);
    })
    //犬を動かす
    //const dog = document.querySelector(".dog span");
    //startBtn.addEventListener("click", function () {
    //    dog.style.transitionDuration = animalSpeed[0] + "s";
    //    dog.classList.add("run");
    //});
</script>
```
```js
        //関数式１
        const concatenateSpace = function (lastName, firstName) {
            return lastName + " " + firstName;
        };
        //関数式２
        const useConcatenate = function (name, func) {
            let concatName = func(name[0], name[1]);
            console.log("結合結果：" + concatName);
        };

        let nameParam = ["橋本", "一輝"];//配列

        //関数式２の実行（引数１=配列、引数２=　関数の名前）
        useConcatenate(nameParam, concatenateSpace);

        //結合結果：中田 雄二


        //コールバック関数基本　※よく使う
        //関数式１
        const testFunc = function (func) {
            //funcには、関数式２
            //関数の実行後のすぐに表示
            console.log("testFuncが実行されました");
            //二秒後に表示
            setTimeout(function () {
                func();
            }, 2000);
        };
        //関数式２
        const callback = function () {
            console.log("callbackが実行されました");
        };
        //関数式１を実行
        //callbackは関数式２の関数名
        testFunc(callback);
```
```html
    <p>これ</p>

    <script>
        //従来の関数式
        const dog = function () {
            return "わんわん";
        };
        //関数の定義
        function dog2() {
            return "バウワウ";
        }
        console.log(dog()); //わんわん
        console.log(dog2())

        //アロー関数の関数式　※アロー関数は関数式で使う
        const cat = () => {
            return "にゃーにゃー";
        };

        //鳴き方を決めたい　アロー関数＋引数
        const animal = (voice) => {
            return voice;
        }
        console.log(animal("みゃあみゃあ"));


        console.log(cat()); //にゃーにゃー

        //p
        //thisは予約語なので変数名、関数名に使えない
        const thisElm = document.querySelector("p");
        console.log(thisElm);
        thisElm.addEventListener("click", (e) => {
            console.log("クリック")
            //console.log(this.textContent)
            console.log(e.target.innerText)
        });

    </script>

```