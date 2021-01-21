# SSHサーバーの設定
- CentOSではOpenSSH Serverが稼働している
- MacOSにはSSHクライアントがインストールされている


1. クライアント側（Mac上）で公開鍵と秘密鍵を作成する：`ssh-keygen`

    鍵を作るときのパスフレーズはなくてもOK
  
    ※暗号強度RSA方式　
    id_rsa（秘密鍵）・・・ クライアントPCに配置
    id_rsa.pub （公開鍵）・・・ 接続対象サーバに登録
    
    
  
  
2. リモートへ公開鍵を転送＆登録：
    `ssh-copy-id -i ~/.ssh/id_rsa.pub [リモートユーザー]@[リモートサーバーのホスト名]`
  
    ※今回既にポートの変更を行っていたため上記コマンドに`-p [ポート番号]`を追加でできた





参考にさせていただいたもの
- [Macで公開鍵と秘密鍵を生成する方法](https://qiita.com/wakahara3/items/52094d476774f3a2f619)
- [SSH公開鍵認証で接続するまで](https://qiita.com/kazokmr/items/754169cfa996b24fcbf5)
