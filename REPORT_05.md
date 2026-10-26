# 第5回　Webエンジニアリング演習　レポート
## 学籍番号
(4724122)
##　TODO配列のコード
(TODO配列コード
　const todos = [
    { id: 1, title: "型を復習する", completed: true },
    { id: 2, title: "配列を学ぶ", completed: false },
    { id: 3, title: "レポートを書く", completed: true },
    { id: 4, title: "課題に挑戦する", completed: true},
    { id: 5, title: "第5回の内容を見直す", completed: false}
　];

for (const todo of todos) {
    const status = todo.completed ? "完了" : "未完了";
    console.log(`${todo.id}: ${todo.title} [${status}]`);
}

確認結果
1: 型を復習する [完了]
2: 配列を学ぶ [未完了]
3: レポートを書く [完了]
4: 課題に挑戦する [完了]
5: 第5回の内容を見直す [未完了])


##　TODOを更新した条件
(TODOを更新した条件のコード
for (const todo of todos) {
    if (todo.completed === false) {
        todo.completed = true;
        console.log(`更新後: ${todo.title} [完了]`);
    }
}

確認結果
更新後: 配列を学ぶ [完了]
更新後: 第5回の内容を見直す [完了])


## 完了件数の更新前後の実行結果
(コード
const completedBefore = todos.filter((todo) => todo.completed).length;
更新した条件のコード
const completedAfter = todos.filter((todo) => todo.completed).length;
console.log(`完了件数: 更新前 ${completedBefore}件 -> 更新後 ${completedAfter}件`);

完了件数の更新前後の実行結果
完了件数: 更新前 3件 -> 更新後 5件)
