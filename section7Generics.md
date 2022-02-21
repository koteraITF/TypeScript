# TypeScript


ジェネリクス(Generics)とは、引数や返り値などの型を任意に設定できる型指定方法のことを指します。JavaやC#といった別言語でもジェネリクスの機能を使うことができます。  

ジェネリクスは型が違う関数を一つにまとめることができる。  
下記は型が違う二つの関数である。  
```
function method1(value: number): number {
  return value;
}

function method2(value: string): string {
  return value;
}
```

上記の関数をひとつにまとめると、下記関数になる。  
また、console.logでも型別に使い分けができていることがわかる。
```
function method<T>(value: T): T {
  return value;
}

console.log(method<number>(10));
=> 10

console.log(method<string>("バナナ"));
=> バナナ
```
