# 第6回 Webエンジニアリング演習 レポート
## 学籍番号
(4724122)
## `Todo`型の定義
(コード
export type Todo = {
    id: number;
    title: string;
    completed: boolean;
    dueDate?: string;
};
)
## 未完了件数を返す関数の引数と戻り値の型
(関数の引数はなし、戻り値の型はnumber
関数のコード
export async function findTodo(): Promise<number> {
    const currentTodos = await fetchTodos();
    const incompletedTodos = currentTodos.filter(
        (todo) => !todo.completed,
    );
    return incompletedTodos.length;
}
)
## 未完了件数の実行結果
(コード「todo-service.ts」
import type { Todo } from "./types.js";

const todos: Todo[] = [
    { id: 1, title: "型を定義する", completed: true},
    { id: 2, title: "関数を作る", completed: false},
];

export async function fetchTodos(): Promise<Todo[]> {
    await new Promise((resolve) => setTimeout(resolve, 500));
    return todos;
}

export async function findTodo(): Promise<number> {
    const currentTodos = await fetchTodos();
    const incompletedTodos = currentTodos.filter(
        (todo) => !todo.completed,
    );
    return incompletedTodos.length;
}

コード「index.ts」
import { fetchTodos, findTodo } from "./todo-service.js";

const loaded = await fetchTodos();
console.log(loaded);

const found = await findTodo();
console.log(`未完了件数： ${found}`);

実行結果
@4724122 ➜ /workspaces/web-eng-typescript (class-06-functions) $ pnpm run start
$ tsx src/index.ts
[
  { id: 1, title: '型を定義する', completed: true },
  { id: 2, title: '関数を作る', completed: false }
]
未完了件数： 1
)

