# JavaScript (ES6)

## 環境整備

[nodistインストール](https://github.com/nullivex/nodist/releases)

```
$ nodist -v
$ nodist + 10.13.0
$ nodist global 10.13.0
$ node -v
```

javascriptバージョン関係で

```
$ npm init -y

//babelのインストール
$ npm install --save @babel/core @babel/cli @babel/preset-env

//babelでコンパイル
$ .\\node_modules\\.bin\\babel src --out-dir dist
```

package.jsonを書き換える

```json
  "scripts": {
    "build": ".\\node_modules\\.bin\\babel src --out-dir dist"
  },
```

実行

```
$ npm run build
```

## npmを使う

```
$ npm install
//出力に色がつくやつ
$ npm install --save chalk
```

## Part I

基本

```javascript
//出力
console.log("...");

//変数
let name = "xuelei";

//定数
const name = "xuelei";

//テンプレートリテラル
console.log(`my name is ${name}`);
```

条件分岐

```javascript
if (条件) {
    処理
} else if {
    処理
} else {

}

console.log(a === b);
console.log(a !== b);
```

switch

```javascript
const color = 'red';

switch (color) {
    case 'red':
        処理;
        break;
    case 'blue':
        処理;
        break;
    default:
        処理;
        break;
}
```

## Part II

繰り返し処理

```javascript
//配列
const a = [1,2,3,4,5];
//オブジェクト
const b = {1:'one',2:'two'};

for (let i = 0; i < a.length; i++) {
    処理
}
```

## Part III

関数

```javascript
const kansu = function() {
    内容
};

//アロー関数
const kansu = () => {
    処理
    return ...
}
```

## Part IV

クラス

```javascript
class A{
    constructor() {
        this.hensu = xxx;
    }
    method() {
        処理;
    }
}
const a = new A();

//継承
class B extends A {
    constructor() {
        super();
    }
}
```

## Part V

ファイル分割

```javascript
class A{

}
export default A;

/*----------*/
import A from "./A";
```

```javascript
const a;
const b;
export {a,b};

/*----------*/
import {a,b} from "./xxx";
```

パッケージの使用

```javascript
import 定数名 from "パッケージ名";
```

## Part VI

配列のメソッド

```javascript
a.push(num);

a.forEach((number)=>{console.log(number);});

//find: 1番で条件に満足する要素
a.find((number)=>{return number > 3;});

//filter
a.filter((number)=>{return number > 3;});

//map: 列挙して処理
a.map((number)=>{return number * 2;});
```

## Part VII

コールバック関数:関数を代入するヤツ？

```javascript
const call = (callback) => {
    callback();
};

call(関数名);
```

```javascript
const call = (callback) => {
  callback("にんじゃわんこ", 14);
};

// 関数callの引数の中で2つの引数を取る関数を追加してください
call((name,age) => {
  console.log(`${name}は${age}歳です。`);
});
```