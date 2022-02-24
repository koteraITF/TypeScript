# TypeScript

ReactでPropsを受け取る場合は、Propsを受け取る側に、Propsのinterfaceを設定しなければならない。  
また、`<TodoListProps>`のように、関数にPropsのinterfaceを渡す必要がある。  
```
interface TodoListProps{
    items: {id: string; text: string}[],
} ////Props設定

export const TodoList: React.FC<TodoListProps> = (props) => {

  return (
    <ul>
      {props.items.map((todo) => (
        <li key={todo.id}>{todo.text}</li>
      ))}
    </ul>
  );
};

```
