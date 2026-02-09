# ルーティングの設定

## デフォルトゲートウェイの設定
「Network」 → 「Routes」で表示された画面の右上にある「Add」ボタンを押し、現れた画面で以下のように設定します。
![alt text](image-5.png)

## DMZサーバへのルーティング設定
BIG-IPからDMZサーバ：10.99.100.0/24へ到達するためのルーティングも同様に設定します。
![alt text](image-6.png)

## ［参考］ Pingによる疎通確認
ルーティング設定が正しいことを確認するために、Pingによる疎通確認を行いたい場合があります。

その場合、コンソール接続またはSSHにてBIG-IPへログインします。  
(デフォルトのユーザ名/パスワードは、"root/default"です。)

1. tmshを実行します。

2. RD1-Partitionへディレクトリを変更します。

3. 疎通確認したい宛先へPingを実行します。

```tmsh
[root@bigXXX:Active:In Sync] config #tmsh ①   
root@(bigXXX)(cfg-sync Standalone)(Active)(/Common)(tmos)# cd /RD1-Partition/ ②   
root@(bigXXX)(cfg-sync Standalone)(Active)(/RD1-Partition)(tmos)# ping 10.99.1.254 ③   
PING 10.99.1.254 (10.99.1.254) 56(84) bytes of data.  
64 bytes from 10.99.1.254: icmp_seq=1 ttl=64 time=3.20 ms  
64 bytes from 10.99.1.254: icmp_seq=2 ttl=64 time=1.57 ms
```