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
