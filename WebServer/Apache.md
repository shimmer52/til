# Webサーバー構築/Apache
**Apacheとは**  
> 世界的に最も普及しているWebサーバ（HTTPサーバ）ソフトウェアの一つ。Apache Software Foundation（Apacheソフトウェア財団）が開発しており、オープンソースソフトウェアとして公開している。

***

[CentOSで自宅サーバー構築](https://centossrv.com/apache.shtml)より  
``` 
- CGIは任意のディレクトリで実行できるようにする  
- SSIは拡張子がshtmlの場合のみ実行できるようにする  
- .htaccessを使用できるようにする  
- PHPを使用できるようにする  
```
※SSI：Server Side Includes[（参考）](https://designsupply-web.com/media/knowledgeside/3370/)　　

ウェブサーバー内で実行することができる機能。例えば、変数の値を出力したり、Linuxのコマンドを実行したり、外部ファイルをインクルードしたりすることができる。　


※CGI：Common Gateway Interface[（参考）](infraexpert.com/study/tcpip16.5.html)  
クライアント側のWebブラウザの要求に応じてWebサーバが外部プログラムを呼び出して、その実行結果がHTTPを介してクライアントのWebブラウザに送信される仕組みのこと。  
  
  
  
***

1.Apacheインストール：`yum -y install httpd php php-mbstring`  
※このとき標準で入るのはPHP5.4だった→7に入れ直し[(参考)](https://www.rem-system.com/centos-httpd-php73/)  
  
2.Apache設定  
※サーバー名は指定せず使用(#は取らない）  
※SetEnvIfの"I(アイ）"を"l（エル）"とタイポしていた（エラーの確認に`service httpd configtest`)   
※Apacheの再起動は`apachectl restart`  

3.サーバー証明書の発行  
**Certbot**  
取得に使ったコマンドは  
``` ertbot certonly --webroot -w ドキュメントルート -m メールアドレス -d Webサーバー名 --agree-tos ```  
ドキュメントルートは/var/www/html（任意のものでOK）  
Webサーバー名を指定しなければならないため、ドメインを取得しDNSサーバーに登録した（Freenom：無料）  
TSLのバージョンによりSSL Server testの判定がBだったためssh_config内で設定し直し：[参考](https://blog.apar.jp/web/10025/)
