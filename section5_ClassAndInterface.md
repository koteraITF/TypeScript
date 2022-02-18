## クラス

下記コマンドの this.nameはクラスのフィールドのnameを参照している。  
コンストラクタはクラスの初期の引数を設定することができる。  
そして、クラスをnewすることでインスタンスを作成し、インスタンス.メソッド名でメソッドを実行している.  
```
class Department {
  name: string;

  constructor(n: string) {
    this.name = n;
  }
  describe() {
    console.log(this.name);
  }
}

const accounting = new Department("Accounting");
accounting.describe(); // Accounting
```

## thisについて
下記コマンドのthisはインスタンス自身を表している。例えば、accountingインスタンスの場合は、thisはaccountingを表している。  
つまり、accountingの場合は、this.name=Accountingとなる。
```
class Department {
  name: string;

  constructor(n: string) {
    this.name = n;
  }
  describe() {
    console.log(this.name);
  }
}

const accounting = new Department("Accounting");
accounting.describe(); // Accounting
```

## TypeScriptのアクセス修飾子
TSのprivateはクラス内でのみアクセスできる。  
readonlyは読み取り専用で変更ができない。(Javaでいうfinal)  

## 継承
下記のようにITがDepartmentクラスを継承した際には、super()とかくことで、親クラスのコンストラクタを呼び出すことができる。
```
class IT extends Department {
  constructor(id: string) {   //ITクラスのコンストラクタ
    super()                   //Departmentクラスのコンストラクタ
    }
}
```

## getter setter
Javaと同じように、Typescriptにもgetterとsetterが存在する。これはprivate変数で隠された変数を外部で利用するためである。(カプセル化)  
getterは下記のように利用する。
```
private sample: string;

get method(){
  return this.sample
}
```

## static
Javaと同じように、Typescriptにもstaticが存在する。  
staticとはnewでインスタンス化しなくても、利用できるクラスである.  
例えば、TypeScriptで`Math.PI`と入力すると円周率が表示されるが、これはMathクラスそのものを利用しているので、staticである。  

## シングルトン,抽象クラス
一つのインスタンスしか作らないクラスはシングルトンという.  
抽象クラスはインスタンス化はできず、他のクラスで継承することしかできないクラス.  
上記はjavaと同じように使える。  

## インタフェース

インタフェースはオブジェクトに必要な要素を記述するものである。  
例えば、下記のPersonインタフェースの場合、nameとageがそれぞれ（正しい型で）利用されなければならない。  
Personの型を利用する場合は宣言も必要

```
interface Person {
  name: string;
  age: number;

  greet(phrase: string): void;
}

let user1: Person;　//Personインタフェース型を利用する宣言

user1 = {　　　　　　　　　//Personインタフェースに基づきオブジェクトを作成。
  name: "yamada",
  age: 3,
  greet:(phrase: string) {
    console.log("test");
  },
}

```

## typeとinterface

typeとは型を定義するものであり、下記のように、インタフェースと同じように利用できる。  
また、typeの方がunion型などを利用でき、汎用性が高いが、
インタフェースのほうがオブジェクトを定義する意図を示すことができるため、オブジェクトの型を作るときはインタフェースのほうが望ましい。  
また、下記のようにインタフェースのプロパティの後ろに？をつけることで、そのプロパティを実施を任意にさせることができる。
```
interface Person {
  name: string;
  age: number;
  hobby?: string

}

type Person {
  name: string;
  age: number;

}

```
また、Javaと同様に、Personインタフェースに基づくHumanクラスを下記のように作成できる。
```
interface Person {
  name: string;
  age: number;

}

class Human implements Person {
  name: "akira",
  age: 3
}

```

## 読み取り専用インタフェース、継承インタフェース

インタフェースには、下記コマンドex1のように、プロパティの前にreadonlyをつけると読み取り専用のプロパティにできる。
readonlyにすると、name変数は再定義できなくなる。(javaでいうfinal)  
また、ex2)のようにPersonインタフェースを継承したSampleインタフェースを利用できる。  
インタフェースを継承するとはたまげたなぁ...  

```
ex1)

interface Person {
  readonly name: string;
  age: number;

}

type Person {
  name: string;
  age: number;

}

ex2)

interface Sample extends Person {
 address: string;
 }

```

## 関数インタフェース

下記のように関数のインタフェースも作成できる。  
```
interface Add {
  (a: number, b: number): number;
}

```


