# EC-CUBEの開発環境構築

## 想定環境

* EC-CUBE 4.0.3
* Apache 2.4.x
* PHP 7.3
* MySQL 8.0

## インストール

Dockerを利用してインストールを行う  
本家ドキュメントのインストール手順を参考

### 事前準備

* docker for windowsのインストール
    * 割愛
* node.jsのインストール
    * scssのコンパイルに使用する
    * ターミナルから```$ node -v```と打ってエラーとなればインストールされていない。
    * [こちら](https://nodejs.org/ja/)からダウンロード&インストール
        * LTS版をインストール

### 手順

初回ビルド時は小一時間かかります。

1. ワークスペースへ移動
1. Gitからダウンロード  
```$ git clone https://github.com/odaryo/eccube_docker.git .```
1. docker起動  

```
$ cd smart_order_catalog
# .envファイルを作成
$ cp .env.dist .env
$ docker-compose up -d --build

# EC-CUBEのビルド
$ docker-compose exec app /bin/bash
$ composer install --no-scripts --no-autoloader --no-dev
$ composer dumpautoload -o --apcu --no-dev
$ composer run-script installer-scripts && composer run-script auto-scripts 
$ bin/console eccube:install
  # 設定はDatabase Url以外はそのままでEnterキーを押していけばOK
    下記の表示が出たら、DB情報を入力してEnter
  Database Url [sqlite:///var/eccube.db]:
   > mysql://root:root@db:3306/eccube_db
   
$ exit
```

- ```... exceeded the timeout of 60 seconds.``` のようなエラーが出た場合は、タイムアウト時間の増加処理が必要です。  
下記ファイルの172行目あたりを修正してください。  
```/src/Eccube/Command/InstallerCommand.php```

```
- $process = new Process('bin/console ' . $command);
+ $process = new Process('bin/console ' . $command, null, null, null,6000);
```

- アクセスURLは```http://localhost:8080```
- 管理画面は```http://localhost:8080/admin```

### 2回目以降の起動手順

2回目以降は下記コマンドで起動します。

```
$ docker-compose up -d
```

### scssコンパイルの方法

windows側から行います  
※node.jsをインストールしておいてください

- 初回のみ  
 warningが出るのは無視

```
$ npm install
```

- コンパイル

```
$ npm run dev
```

## DBへのアクセス情報

* host: localhost
* port: 3307
* user: root
* password: root
* database: eccube_db

## cssのビルド

```
$ yarn dev
```


## ドキュメント

* [EC-CUBE 4.0 開発ドキュメント@doc4.ec-cube.net](http://doc4.ec-cube.net/)


