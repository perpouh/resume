# resume

職務経歴書を書くのが面倒臭すぎる+どう頑張っても絶対に読みづらいものにしかならないのでyamlとgit管理+検索機能を盛り込んでやろうと思った

## Project setup
```
docker build -t resume . 
docker run --name resume -it -p 8080:8080 -v $PWD:/app resume
docker start resume
```