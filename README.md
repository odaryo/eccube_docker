# EC-CUBE 4.0

+ 本ドキュメントはEC-CUBEの開発者を主要な対象者としております。  
+ パッケージ版は正式リリース後に[EC-CUBEオフィシャルサイト](http://www.ec-cube.net)で配布します。  
+ カスタマイズやEC-CUBEの利用、仕様に関しては[開発コミュニティ](http://xoops.ec-cube.net)をご利用ください。  
+ 本体開発にあたって不明点などあれば[Issue](https://github.com/EC-CUBE/ec-cube/wiki/Issues%E3%81%AE%E5%88%A9%E7%94%A8%E6%96%B9%E6%B3%95)をご利用下さい。

## インストール

### EC-CUBE 4.0のインストール方法

開発ドキュメントの [インストール方法](http://doc4.ec-cube.net/quickstart_install) の手順に従ってインストールしてください。

### CSS の編集・ビルド方法

[Sass](http://sass-lang.com) を使用して記述されています。
Sass のソースコードは `html/template/{admin,default}/assets/scss` にあります。
前提として [https://nodejs.org/ja/] より、 Node.js をインストールしておいてください。

以下のコマンドでビルドすることで、 `html/template/{admin,default}/assets/css` に CSS ファイルが出力されます。

```shell
npm install # 初回のみ
npm run build # Sass のビルド
```

### 動作確認環境

* Apache/2.4.x (mod_rewrite / mod_ssl 必須)
* PHP7.1.20
* PostgreSQL 9.2.1   
* ブラウザー：Google Chrome  

詳しくは開発ドキュメントの [システム要件](http://doc4.ec-cube.net/quickstart_requirement) をご確認ください。

## ドキュメント

### [EC-CUBE 4.0 開発ドキュメント@doc4.ec-cube.net](http://doc4.ec-cube.net/)


EC-CUBE 4.0 の仕様や手順、開発Tipsに関するドキュメントを掲載しています。  
修正や追記、新規ドキュメントの作成をいただく場合、以下のレポジトリからPullRequestをお送りください。  
[https://github.com/EC-CUBE/ec-cube.github.io](https://github.com/EC-CUBE/ec-cube.github.io)


### コピーライトポリシーへの同意

コードの提供・追加、修正・変更その他「EC-CUBE」への開発の御協力（Issue投稿、PullRequest投稿など、GitHub上での活動）を行っていただく場合には、
[EC-CUBEのコピーライトポリシー](https://github.com/EC-CUBE/ec-cube/wiki/EC-CUBE%E3%81%AE%E3%82%B3%E3%83%94%E3%83%BC%E3%83%A9%E3%82%A4%E3%83%88%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BC)をご理解いただき、ご了承いただく必要がございます。
Issueの投稿やPullRequestを送信する際は、EC-CUBEのコピーライトポリシーに同意したものとみなします。
