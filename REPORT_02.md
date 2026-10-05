# 第2回　Webエンジニアリング演習　レポート
## 学籍番号
(4724122)
## コンフリクトが発生した理由
(practice/conflict-aとpractice/conflict-bの2つのブランチから同じファイル(README.md)の同じ行を変更したため、２つのブランチで行った変更が衝突したから。)
## 解決方法
(git pull --no-rebase origin mainで表示された競合記号をすべて削除し、２つの内容を1つにまとめた1行に編集した。その後git status→git add→git commit→git pushの順で実行し、競合が解消されたことを確認してからプルリクエストをmainへマージした。)
## 履歴
@4724122 ➜ /workspaces/web-eng-report (practice/conflict-b) $ git log --oneline --graph --all
*   1177421 (HEAD -> practice/conflict-b, origin/practice/conflict-b) Resolve README conflict
|\  
| *   f2fef97 (origin/main, origin/HEAD) Merge pull request #2 from 4724122/practice/conflict-a
| |\  
| | * afeda09 (origin/practice/conflict-a, practice/conflict-a) Update goal in conflict A
| |/  
* / 2f916ce Update goal in conflict B
|/  
*   a6947de (main) Merge pull request #1 from 4724122/feature/add-readme
|\  
| * 308699f (origin/feature/add-readme) Add README
|/  
* 7e64752 Add REPORT_01.md
* a31a582 Add index.html
* 88ed422 Add devcontainer configuration for Web Engineering
* e3ff472 Initial commit
