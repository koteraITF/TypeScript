## 型推論
TypeScriptには型推論という機能があり、最初に変数を入れると、その変数の型を推測してくれるため、  
下記コマンドのように入力するとエラーが起きる。
```
let number1 = 2;
let number1 = "aaa" //エラー
```
一応、冗長ではあるが、下記のように書いても問題ない。
```
let number1: number =2; 
```

## tuple型

下記のように配列には型を入れることができ、型に入れる要素の型を決めるものをtuple型という。
```
const person: {
  name: string;
  role: [number, string]; //tuple型
} = {
  name: "yota",
  role: [2, "student"]
};

```

## Enum型
下記のように記述することで、それぞれの要素に自動的に番号が振り分けられる。  
これがenumの利点
```
enum Role {
  ADMIN,
  READ_ONLY,
  author,
}
```
## Union型

`const comibine(n1 : number | string ,n2: number | stromg )`のように
一つの変数に対して複数の型を設定することができる

## Literal型

変数に対して特定の値を入れる型
```
const combine(n1: SampleText)
const SampleText = "sample"]
```
のようにn1にはSampleTextしかいれられなくなる。

## エイリアス（Alias）型

`type SampleText = number | string;`
のようにtype関数を使うことで、あらかじめSampleTextの型を定義することができる。

## Function型

`let comibine: Function;`  
上記のようにFunction型を指定することで、combineには関数しか代入できなくなる。
また、関数の型に関して、詳しく型を定義することができる。  
`let combine: (a1:number, a2:number) = > number;`
のように指定することで、数値型の引数２つを取得する関数しかcombineには代入できなくなる。

## コールバック関数

下記のようにコールバック関数cbがvoidであることを示し、戻り値がないと示しても、  
下記のAddAndHandleメソッドのようにreturnを返すことができる。つまり、voidは戻り値を返すことを強制しない型である。  
```
function AddAndHandle(n1:number, n2:number, cb:(num:number) => void){
  const result = n1 + n2;
  cb(result);
}

AddAndHandle(10,20,(result:number) => {
  console.log(result);
  return result;
})
```

## never型
関数が「絶対に戻り値を返さない」型である。
void型と似ているが、void型と違い、関数が”絶対に”型を返さない点で異なる。
