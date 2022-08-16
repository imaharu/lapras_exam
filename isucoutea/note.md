## 高速化記録

### 記入例
Result: 59.733733892440796 sec  初回実行

Result: 58.84676766395569 sec  locations テーブルの name に対して index を張った

計測忘れ  MySQL の設定ファイルで xxx_yyyy の値を N にした。

Result: xx.yyyyyyyyyyyyyy sec  アプリケーションの XX 部分の N+1 を解消した。


### あなたの作業記録

#### 初期値

```
Request:  GET / 7.7204455850005616 sec 
Request:  GET /?page=80000 7.9497054630001 sec 
Request:  POST / 7.618097132000003 sec 
Request:  GET /?page=25&query=平塚市 20.0106070009997 sec (timeout)
Request:  GET /?page=858&query=日本 20.00820201500028 sec (timeout)
Request:  GET / 19.722368630000346 sec 
Request:  POST / 14.132249412999954 sec 
Request:  GET /?query=ミャメビエコフ茶 20.02062541900068 sec (timeout)
Request:  GET /?query=存在しないお茶 20.016748229999394 sec (timeout)
Request:  GET / 20.00727802399979 sec (timeout)
Result: 157.20687530000032 sec
```

#### offset処理をSQLに任せる

```
Request:  GET / 1.0196432299999287 sec 
Request:  GET /?page=80000 2.223798025001088 sec 
Request:  POST / 0.9818122789984045 sec 
Request:  GET /?page=25&query=平塚市 0.8874545959988609 sec 
Request:  GET /?page=858&query=日本 0.9205772730001627 sec 
Request:  GET / 0.900377234998814 sec 
Request:  POST / 0.9349515619996964 sec 
Request:  GET /?query=ミャメビエコフ茶 0.9270249460005289 sec 
Request:  GET /?query=存在しないお茶 0.9146538900004089 sec 
Request:  GET / 0.8519990410004539 sec 
Result: 10.562818407001032 sec
```
