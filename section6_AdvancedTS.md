# TypeScript

## 交差型

下記のように、型を　＆　でつなげることで、型定義を合体させることができる。  
```
interface Person {
  name: string;
  age: number;

}

interface Hobby {
  name: string;
  hobby: string;
}

type Sample = Person & Hobby

```

## 型ガード
型ガードは型を絞り込む役割がある。
下記のCombinableはstringとnumberの可能性があるため、下のif文でstringの場合は、引数を全てstringで返し、それ以外の場合は、数値で返している。  
このように、string型かnumber型かを絞り込むときに型ガードを利用できる。  
```
type Combinable = string | number;

function add(a: Combinable, b: Combinable) {
  if(typeof a === 'string' || typeof b === 'string'){
    return a.toString() + b.toString();
  }
  return a + b
}
```

## 型キャスト

下記のようにuserInputElementがinput要素であることを型宣言している。
```
const userInputElement = document.getElementById('hoge') as HTMLInputElement;
const userInputElement = <HTMLInputElement>document.getElementById('hoge');

```

## インデックス型

下記のようにErrorContainerのinterfaceを定義する。  
そして、ErrorContainrのオブジェクトを `email`と`username`に設定した。これはどちらともstringだからokである。  
しかし、これらを`1`や`2`のように定義するとnumberとなるため、エラーとなる。
```
interface ErrorContainer {
  [prop: string]: string;
}

const errorBag: ErrorContainer = {
  email: "正しいメールアドレスではありません",
  username: "ユーザー名に記号を含めることはできません",
  1: "適切ではありません" //1はnumber型であるため[prop: string]に反し、エラー
};
```

