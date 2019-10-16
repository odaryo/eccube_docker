# EC-CUBEの開発環境構築

## 想定環境

* EC-CUBE 4.0.3
* Apache 2.4.x
* PHP 7.3
* MySQL 8.0

## インストール

本家ドキュメントのインストール手順を参考に、1コマンドで環境が揃うよう改造する

### 手順

初回ビルド時は小一時間かかります。(15分～)


1. ワークスペースへ移動
1. Gitからダウンロード  
```$ git clone https://bmc-it.backlog.jp/git/SMHT/smart_order_catalog.git .```
1. docker起動

```
$ cd smart_order_catalog
$ docker-compose up -d --build

※ 2回目以降は
$ docker-compose up -d
```

## ドキュメント

* [EC-CUBE 4.0 開発ドキュメント@doc4.ec-cube.net](http://doc4.ec-cube.net/)


