共有ワールド修正版

[最新版ZIPをダウンロード](https://github.com/33333-33333/33333/raw/refs/heads/master/releases/rakugaki-multiplayer-fixed.zip)

**フォルダをWebサーバーへ置くだけではマルチプレイは動きません。** Node.js 22以降でserver.cjsを1プロセス常駐させ、公開URLからHTTPとWebSocketを転送してください。導入手順はZIP内の **START_HERE.html** をブラウザで開いて読めます。

この修正版は通常URLで必ず共有サーバーへ接続します。接続失敗時に単独ワールドへ切り替えません。2タブで同じワールドIDと出撃状態になること、切断後も同じワールドへ戻ることを検証し、23テストが成功しました。県庁オーラの暗めの色と指令UIの修正も含みます。

公開先の /~333/japan/ に対応しています。展開したアプリのフォルダで、Linux等のシェルなら次のように起動します。

```sh
node --version
npm ci --ignore-scripts
HOST=127.0.0.1 PORT=3000 BASE_PATH=/~333/japan DATA_DIR="$HOME/rakugaki-data" COOKIE_SECURE=1 npm start
```

そのうえで公開Webサーバーから127.0.0.1:3000へのHTTP/WebSocket転送を設定します。SSHでプログラムを起動できても、公開URLが自動でNode.jsへ切り替わるわけではありません。Nginx・Apacheの設定例とWindowsでの起動例はSTART_HERE.htmlに記載しています。

この更新では公開サーバー自体の設定変更は行っていません。公開先のapi/healthにbuild: 2026-10-28-shared-1が表示され、ゲームを2タブ開いて左上のワールドIDが一致することを確認してください。

チェックサムは同名の.sha256ファイルを参照してください。
