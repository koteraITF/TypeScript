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
