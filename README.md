# resume

職務経歴書を書くのが面倒臭すぎる+どう頑張っても絶対に読みづらいものにしかならないのでjsonとgit管理+検索機能を盛り込んでやろうと思った  
当初yamlでやろうと思っていたけどVueでやるのにyamlはめんどいと思ったのでjsonにした

## セットアップ
```
docker build -t resume . 
docker run --name resume -it -p 8080:8080 -v $PWD:/app resume
docker start resume
```