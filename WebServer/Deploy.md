# Webサーバーにデプロイ
---  
  
##  gitで管理していたソースを利用してデプロイを行った  
  
- ドキュメントルート上にプロジェクトディレクトリ作成  
  
- プロジェクトディレクトリにてComposerをインストール  
  
[参考](https://ajike.github.io/CakePHP%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%8B%E3%82%89%E5%88%9D%E6%9C%9F%E8%A1%A8%E7%A4%BA%E3%81%BE%E3%81%A7/)  
  
  
- ソースを引っ張ってくる  

ドキュメントルート上で`git clone`  
Vendorディレクトリはcloneされないので`composer install`を行う。  
[参考](https://qiita.com/eno1122/items/3173d7fd29cf596a97e6)  
  
※その後git管理はせず、ターミナル上でファイルの書き換えを行っていった  
  
- プロジェクトディレクトリにアクセスをして動作確認（まだDB接続されていない）  
  
- DB接続するためにConfig>app.php>Detasourcesのusername,password,databaseを指定する  
  
  ※DBは事前にインストール済み（MariaDB)。PhpMyAdmin上でデータベースを事前に作成。
  
- `httpd.conf`にてドキュメントルートを指定。`アプリ名.conf`を作成し、Aliasを指定。  
  
  [参考](https://ogeji.hatenablog.com/entry/2014/09/09/155747)  
  
- `php.ini`でのtimezone指定、`.htaccess`に追記  
  
  [参考](https://gritt.jp/blog/sakura-vps-cakephp-install)
  
- Migrationファイルを使用するため、`bootstrap.php`にpluginを記述  
  
---
  
### その他覚書
- mv を利用するとファイル、ディレクトリ名を変更できる
- 
