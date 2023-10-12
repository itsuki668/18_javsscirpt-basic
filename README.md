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