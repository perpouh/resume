# resume

職務経歴書を書くのが面倒臭すぎる+どう頑張っても絶対に読みづらいものにしかならないのでjsonとgit管理+検索機能を盛り込んでやろうと思った  
当初yamlでやろうと思っていたけどVueでやるのにyamlはめんどいと思ったのでjsonにした

## Install
```
docker build -t resume . 
docker run --name resume -it -p 8080:8080 -v $PWD:/app resume
docker start resume
```

## Usage

上のコマンドでインストール（？）した場合、 `docker ps` でコンテナに入って `yarn serve` すると `localhost:8080` で表示できます。

.github/workflowを使いたい場合（GithubPagesで表示したい場合）、デプロイキーの設定が必要になります。  
参考: [Create SSH Deploy Key](https://github.com/perpouh/actions-gh-pages#%EF%B8%8F-create-ssh-deploy-key)

## Feature

 - 絞り込み検索ができる
 - ソート機能はちゃんと作っていない
 - 絞り込み検索に使うフォームは印刷時には表示されない

## まだやってないこと

 - 各経歴のテーブルが改ページを跨ぐときの調整
 - ソート（果たして必要かどうかも悩んでいる）

 ## ライセンス

MIT

どうぞご自由に使ってください。resume.jsonを書き換えれば動くはずです。  
jsonの項目は

 - summary:プロジェクト概要
 - phase_in_charge:担当フェーズ
 - business_content:業務内容（リスト）
 - achievement:実績、取り組み
 - development_environment:環境、言語とかFWとかMWとかOSとか

となっています。no項目はv-bind:keyのために作ったけどちゃんと振らなくても動くようです。よくわからない、v-bind:key

## Contributing

歓迎します。特にscreenの方のCSSとか。

## 免責事項

Chrome以外で動作確認していません。