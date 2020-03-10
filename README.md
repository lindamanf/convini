# 初回デプロイ方法
1. git コマンドで当リポジトリを clone する
```
$ git clone https://github.com/lindamanf/convini.git
```
2. deploy.sh を実行
```
$ cd convini
$ ./deploy.sh
```
3. MySQLコンテナにDjangoのモデルを反映
```
$ docker-compose run web ./manage.py makemigrations
$ docker-compose run web ./manage.py migrate
```
4. ブラウザからAccess!
```
http://127.0.0.1:8000/admin
```

# 管理サイトのスーパーユーザー作成
1. web serverコンテナへ入る
```
$ docker exec -it convini.web bash
2. 8080ポートでアクセスできるようにコマンドを実行
```
/code# ./manage.py createsuperuser
```
あとはダイアログにしたがって回答するのみ。

# Debug モードの利用方法
1. web serverコンテナへ入る
```
$ docker exec -it convini.web bash
```
2. 8080ポートでアクセスできるようにコマンドを実行
```
/code# ./manage.py runserver 0.0.0.0:8080
```
3. ブラウザからAccess!
```
http://127.0.0.1:8080
```