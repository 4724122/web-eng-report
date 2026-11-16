# 第8回　Webエンジニアリング演習　レポート
## 学籍番号
(4724122)
## コンポーネント構成
(TodoItem.tsxとTodoList.tsxという二つの子コンポーネントとデータを組み合わせて一覧画面を表示するApp.tsx(親コンポーネント)を作成してTODO一覧ページを作成した。TodoItem.tsxは1件のTODOを受け取って期限が記載されているもののみを表示すると同時に期限が切れているTODOは赤い文字で表示するコンポーネントである。またTodoList.tsxは複数のTodoItemを配列として受け取って表示するコンポーネントである。



TodoItem.tsxのコード　→　
import type { Todo } from "../types";

type TodoItemProps = {
    todo: Todo;
};

export function TodoItem({ todo }: TodoItemProps) {
    const today = new Date();
    return (
        <li>
            {todo.dueDate? (
                new Date(todo.dueDate) < today ? (
                    <span style={{color: "red"}}> <strong>{todo.title}</strong>期限: {todo.dueDate}</span>
                ):(
                    <span> <strong>{todo.title}</strong>期限: {todo.dueDate}</span>
                ) ) : null}

        </li>
    );
}



TodoList.tsxのコード　→

import type { Todo } from "../types";
import { TodoItem } from "./TodoItem";

type TodoListProps = {
    todos: Todo[];
};

export function TodoList({ todos }: TodoListProps) {
    return (
      <ul>
        {todos.map((todo: Todo) => (
            <TodoItem key={todo.id} todo={todo} />
            ))}
      </ul>
    );

}



App.tsxのコード　→
import { todos } from "./data";
import { TodoList } from "./components/TodoList";

export default function App() {
  return (
    <main>
      <h1>React TODO</h1>
      <TodoList todos={todos} />
    </main>
  );
}

)
## `TodoItem`のProps型
(`TodoItem`のProps型　→
type TodoItemProps = {
    todo: Todo;
};
)
## 期限あり・なしの画面確認結果
(data.tsの中身　→　
import type { Todo } from "./types";

export const todos: Todo[] = [
    { id: 1, title: "Reactを学ぶ", completed: true, dueDate: "2026-12-12" },
    { id: 2, title: "Propsを確認する", completed: false, dueDate: "2026-09-11" },
    { id: 3, title: "Stateを更新する", completed: false },
];

確認結果　→
3つのTODOの内、idが1と2のTODOが表示され、idが2のTODOは赤い文字で表示された。
)