# resume

職務経歴書を書くのが面倒臭すぎる+どう頑張っても絶対に読みづらいものにしかならないのでjsonとgit管理+検索機能を盛り込んでやろうと思った  
当初yamlでやろうと思っていたけどVueでやるのにyamlはめんどいと思ったのでjsonにした

## Install
```
docker build -t resume . 
docker run --name resume -it -p 8080:8080 -v $PWD:/app resume
docker start resume
```

## Feature

 - 絞り込み検索ができる
 - ソート機能はちゃんと作っていない
 - 絞り込み検索に使うフォームは印刷時には表示されない

## まだやってないこと

 - 各経歴のテーブルが改ページを跨ぐときの調整
 - ソート（果たして必要かどうかも悩んでいる）