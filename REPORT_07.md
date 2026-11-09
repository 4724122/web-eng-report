# 第７回　Webエンジニアリング演習　レポート
## 学籍番号
(4724122)
## 2画面の見出しと本文
(コード
#compareの表示内容　→
 if (page === "#compare") {
        app.innerHTML = `
          <h1>画面生成方式の比較</h1>
          <p>この文章はTypeScriptから追加した。</p>
        `;
} 
    


#detailの表示内容　→　
else if (page === "#detail"){
      app.innerHTML = `
        <h1>画面生成方式の詳細</h1>
        <p>ハッシュで新しいHTMLを取得せず画面切り替えできる。</p>
      `;
})
## クリック後のURLとNetworkの確認
(最初のURL
https://jubilant-invention-v6j6pxx99vqgfr9-3000.app.github.dev/csr/


比較をクリックした後のURL
https://jubilant-invention-v6j6pxx99vqgfr9-3000.app.github.dev/csr/#compare


詳細をクリックした後のURL
https://jubilant-invention-v6j6pxx99vqgfr9-3000.app.github.dev/csr/#detail



Networkの確認　→
比較と詳細をクリックしてもNetworkのリストに新しいHTMLなどの行が追加されていないことが確認できた。)
## 画面を切り替える処理の要点
(画面を切り替える処理の要点　→
addEventListener()というメソッドを使用し、このメソッドの第一引数に”hashchange”を渡すことでURLの＃以降の部分が変更されたタイミングを検知することができる。また第二引数に() => {}という形で処理を記述することでハッシュが変更されるたびに{}の中に書いた処理内容が実行される。さらにlocation.hashで現在のURLの＃以降を取得することで＃以降の値の違いによって表示内容を指定することができる。



コード　→
const app = document.querySelector("#app");

if (app === null) {
    throw new Error("#appが見つからない");
}

app.innerHTML = `
  <h1>画面生成方式</h1>
`;

window.addEventListener("hashchange", () => {
    const page = location.hash;
    if (page === "#compare") {
        app.innerHTML = `
          <h1>画面生成方式の比較</h1>
          <p>この文章はTypeScriptから追加した。</p>
        `;
    } else if (page === "#detail"){
      app.innerHTML = `
        <h1>画面生成方式の詳細</h1>
        <p>ハッシュで新しいHTMLを取得せず画面切り替えできる。</p>
      `;
    }
});
)