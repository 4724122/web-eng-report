# 第4回　Webエンジニアリング演習　レポート
##　学籍番号
(4724122)
##　`const`と`let`の宣言・再代入に使用したコード
(const courseName = "Web Engineering";
let retryCount = 1;

courseName = "Other Course";
retryCount = 2;)
##　VScodeと`pnpm run check`に表示されたエラー番号・メッセージ
(
表示されたエラー番号・メッセージ
@4724122 ➜ /workspaces/web-eng-typescript (main) $ pnpm run check
$ tsc --noEmit src/index.ts
src/index.ts:4:1 - error TS2588: Cannot assign to 'courseName' because it is a constant.

4 courseName = "Other Course";
  ~~~~~~~~~~


Found 1 error in src/index.ts:4

[ELIFECYCLE] Command failed with exit code 2.)

## 修正後の実行結果と`const`・`let`の違いの説明
(
修正後のコード
const courseName = "Web Engineering";
let retryCount = 1;

retryCount = 2;

console.log(retryCount)


修正後の実行結果
@4724122 ➜ /workspaces/web-eng-typescript (main) $ pnpm run check
$ tsc --noEmit src/index.ts
@4724122 ➜ /workspaces/web-eng-typescript (main) $ pnpm run start
$ tsx src/index.ts
2


`const`と`let`の違いの説明
`const`は再代入できないものを宣言したいときに使うコマンドで、constで宣言した数字や文字列などは後から変えることができない。
`let`は再代入が必要な時に使うコマンドで、letで宣言した数字や文字列などを後から再代入という形で変えることができる。)