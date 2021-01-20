# システム時刻を自動的に合わせる
> NTPサーバーを構築して、サーバーのシステム時刻を日本標準時間に自動的に合わせる
- 使用サーバー：chrony

- さくらインターネットではNTPサーバーを無償提供している（インストールしたら既にあった）
- `$ chronyc sources`でサーバーを確認（NTPサーバー名の前に＊がついていたら時刻同期中）

[公式参考](https://manual.sakura.ad.jp/cloud/support/ntp.html)
