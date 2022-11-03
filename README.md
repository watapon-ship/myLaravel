●参考
https://codelikes.com/github-ssh-connection/
https://qiita.com/MachonglishproK/items/42a8380240629297743a

●動かし方
cd C:\work\laravel9_mylist

#クリーンアップ
$ docker-compose down --rmi all --volumes --remove-orphans
$ docker-compose down --volumes
$ docker-compose down --volumes --rmi all
$ docker-compose up -d --build

ビルド
$ docker-compose up -d

コンテナ確認
$ docker-compose ps
$ docker container ls

コンテナを停止
$ docker-compose stop

コンテナを開始
$ docker-compose start

コンテナを終了
$ docker-compose down


イメージを削除する場合
docker image rm a624d888d69f

IPを確認
docker-machine ip


●環境構築
cd C:\work\laravel9_mylist

①仮想環境を作る

# docker起動
$ docker-compose up -d 

# phpコンテナに入ります
$ docker-compose exec workspace bash

# 下記で環境を確認
composer -V
php -m

# Laravelプロジェクト作成
$ composer create-project "laravel/laravel=9" app-web
$ composer create-project "laravel/laravel=9" app-bacth
$ composer create-project "laravel/laravel=9" app-api

# storageのパーミッションを追加
chmod 777 -R /var/www/html/app-web/storage/
chmod 777 -R /var/www/html/app-bacth/storage/
chmod 777 -R /var/www/html/app-api/storage/


# DB1のバージョン
C:\dockertest\laraveltest>docker-compose exec db mysql -V
mysql  Ver 8.0.23 for Linux on x86_64 (MySQL Community Server - GPL)


# DBマイグレーション
php artisan migrate

③git環境を作成
・key作成
ssh-keygen -t ecdsa -b 521 -C “your_email@example.com

・C:\Users\ユーザー名\.ssh\id_ecdsa.pubの中身をGithubに登録
　・「Settings」→ SSH　and GPG keys → New SSH Kwy
　　・pubファイルの中身をコピペして画面に設定する




==試そうとしたがやめた==========================================-

# vue.js
docker-compose exec workspace bash
composer require laravel/ui:1.*

# Vue.jsで構築するためのファイル等を生成します。
php artisan ui vue

# mpmを追加
curl -sL https://deb.nodesource.com/setup_6.x | bash - && \ 
apt-get install -y nodejs

# package.jsonの内容に依存したパッケージをインストールし、コンパイルします。(npmがない)
npm install && npm run dev

================================================================-


