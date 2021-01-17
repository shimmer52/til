## Web APIを叩く
動画学習（しまぶーのIT大学/JavaScript入門 #8)

- APIを呼び出す関数を作る
- window.fetchをするとPromiseというオブジェクトが返ってくる
- asyncファンクションとすると中身が非同期関数に→awaitという式が使える
- async awaitでfetchを使うとResponseオブジェクトが返ってくる（成功/失敗、データの中身など）→使いやすく変換
- responseオブジェクトが持っているjsonというメソッド（ここにもawaitをつける）

``` async fucntion callApi() {
      const res = await fetch("https://jsonplaceholder.typicode.com/users");
      const users = await res.json();
    }; ```
    
    
### APIを叩くときは`async await`が主流

- そのほかにも**fetchを.then**でつなぐ書き方（見づらい、エラー処理の書き方の方がエラー処理も書きやすい）

- fetchを使わない**XMLHttpRequest()**昔の使い方。進捗がわかるのでファイルのアップロード自作などでは使える
