修正版ゲームのダウンロード

[修正版ZIPをダウンロード](https://github.com/33333-33333/33333/raw/refs/heads/master/releases/rakugaki-dark-aura.zip)

県庁オーラは県の色の明るさ70%。PCは右クリック・右ドラッグのラジアル操作、スマホは指令モードとラジアル操作を使用します。脆弱性対策と処理の簡素化も含みます。

ZIPを展開し、Node.js 22以降で `npm ci --ignore-scripts`、`npm test`、`npm start` を実行してください。運用設定・検証結果・制約はZIP内のREADMEと各変更説明を参照してください。

同梱のSHA-256ファイルでZIPの一致を確認できます。本番サーバーへのデプロイは行っていません。
