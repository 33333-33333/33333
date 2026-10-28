ヘッダー表示の修正版

[差し替え用ZIP（index.htmlのみ）](https://github.com/33333-33333/33333/raw/refs/heads/master/releases/rakugaki-header-update.zip)

「×1はリアルタイム進行」を削除し、ヘッダー左に「333の部屋に戻る」ボタンを追加しました。リンク先は https://2012r2.nishi.boats/~333/ です。PC・スマホの6種類の画面幅で位置とリンクを確認しています。

今回はZIP内のindex.htmlだけを既存ファイルに差し替え、ブラウザを強制再読み込みしてください。Nodeの再起動やデータの変更は不要です。[変更詳細](HEADER_UPDATE.md)

---

Node.js 18.20.8互換版：システム更新不要

[最新版ZIPをダウンロード](https://github.com/33333-33333/33333/raw/refs/heads/master/releases/rakugaki-header-full.zip)

**フォルダをWebサーバーへ置くだけではマルチプレイは動きません。** 既存のNode.js v18.20.8でserver.cjsを1プロセス常駐させ、公開URLからHTTPとWebSocketを転送してください。導入手順はZIP内の **START_HERE.html** をブラウザで開いて読めます。

**Node.js v18.20.8のままで23テストとブラウザの2タブ共有を検証済みです。サーバー全体のNode.js更新やsudoインストールは不要です。**

この修正版は通常URLで必ず共有サーバーへ接続します。接続失敗時に単独ワールドへ切り替えません。2タブで同じワールドIDと出撃状態になること、切断後も同じワールドへ戻ることを検証し、23テストが成功しました。県庁オーラの暗めの色と指令UIの修正も含みます。

公開先の /~333/japan/ に対応しています。展開したアプリのフォルダで、Linux等のシェルなら次のように起動します。

```sh
node --version
npm ci --ignore-scripts
HOST=127.0.0.1 PORT=3000 BASE_PATH=/~333/japan DATA_DIR="$HOME/rakugaki-data" COOKIE_SECURE=1 npm start
```

公開Webサーバーから127.0.0.1:3000へのHTTP/WebSocket転送も必要です。権限が分からない場合は設定を変更せず、管理者に確認してください。SSHでプログラムを起動できても、公開URLが自動でNode.jsへ切り替わるわけではありません。Nginx・Apacheの設定例とWindowsでの起動例はSTART_HERE.htmlに記載しています。

この更新では公開サーバー自体の設定変更は行っていません。公開先のapi/healthにbuild: 2026-10-28-node18-1が表示され、ゲームを2タブ開いて左上のワールドIDが一致することを確認してください。

チェックサムは同名の.sha256ファイルを参照してください。

管理者への確認例：

> 自分のNode.jsアプリを1プロセス常駐させ、/~333/japan/ から 127.0.0.1:3000 へHTTPとWebSocketを転送できますか？利用可能なポートやユーザー用の設定方法があれば教えてください。Node.js本体の更新は不要です。
