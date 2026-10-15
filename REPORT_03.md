# 第3回　Webエンジニアリング演習　レポート
## 学籍番号
(4724122)
## イメージとコンテナの違い
(イメージは作業のやり方が書かれた設計図であるDockerfileをbuilコマンドを実行することで作られるものであり、コードの実行に必要なものをまとめたパッケージのことを指す。またイメージは読み取り専用である。コンテナはイメージをrunという実行を行うコマンドで起動された実行中の環境のことである。)
## Dockerfileの各行の役割
(FROMは土台となるイメージを指定しているものである。COPYはホストのファイルをイメージにコピーするものである。今回の授業では土台としてnginxを指定し、親のコンテナにあるindex.htmlを子コンテナにコピーした。)
## 動作確認
(変更後の見出し→<h1>Docker Composeで配信中</h1>
docker compose psの結果
@4724122 ➜ /workspaces/web-eng-docker (main) $ docker compose ps
NAME                   IMAGE                COMMAND                  SERVICE   CREATED          STATUS          PORTS
web-eng-docker-web-1   web-eng-docker-web   "/docker-entrypoint.…"   web       10 seconds ago   Up 10 seconds   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp)
