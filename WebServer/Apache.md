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

1.Apacheインストール：`yum -y install httpd php php-mbstring`  
2.Apache設定  
※サーバー名は指定せず使用(#は取らない）  
※SetEnvIfの"I(アイ）"を"l（エル）"とタイポしていた（エラーの確認に`service httpd configtest`)   
※Apacheの再起動は`apachectl restart`  
