# web-vsのACL設定

パーティションをRD1-Partitionに変更します。
![alt text](image-16.png)

## Rule Listの作成

ここでは、Rule listを使ってみます。

(1) まず、ルールの入れものをつくります。

「Security」→「Network Firewall」→「Rule Lists」で表示された画面の右上にある「Create」ボタンを押すと、以下の画面が現れます。 Nameだけ入力して「Finished」ボタンを押します。
![alt text](image-17.png)

(2) 作成したweb_listをクリックします。
![alt text](image-18.png)

(3) 「Add」ボタンを押します。
![alt text](image-19.png)

(4) HTTP(80)用ルール以下のように設定します。
![alt text](image-20.png)

(5) HTTPS(443)用ルール再度「Add」ボタンを押し、以下のように設定します。
![alt text](image-21.png)

(6) Proxy(Squid)経由のIPアドレス(10.99.4.228)を拒否するルール

通信テストで、拒否ルールが正常に動作していることを確認しやすいように、本ガイドではその対象を10.99.4.228 としました。再度「Add」ボタンを押し、以下のように設定します。
![alt text](image-22.png)

(7) ルールは上から評価されるので、このように拒否ルールが一番下にあると、HTTP(80)、HTTPS(443)は通過してしまいます。そこで、ルールの順番を変更します。

「Reorder」ボタンを押します。
![alt text](image-23.png)

(8) 各ルールの先頭にマウスを移動すると、カーソルが手のマークに変わります。

拒否ルールをドラッグして、一番上に移動し、「Update」ボタンを押します。
![alt text](image-24.png)

(9) 拒否ルールが一番上に移動します。
![alt text](image-25.png)

## ACLの適用
Rule Listを使って作成したACLを、web-vsへ適用します。

(1) 「Local Traffic」→「Virtual Servers」→「Virtual Sever list」で表示された該当VS(web-vs)をクリックし、 「Security」タブ→「Policies」をクリックすると、以下の画面が表示されます。「Add」ボタンを押します。
![alt text](image-26.png)

(2) 以下のように設定します。
![alt text](image-27.png)

(3) 以下の状態になります。
![alt text](image-28.png)

(4) 全拒否ルールの追加デフォルトでは、ルールにヒットしなかったパケットはAcceptとなっています。

このままでは、全てのパケットが通過してしまうので、最後に全拒否ルールを入れます。

再度、「Add」ボタンを押し、現れた画面で以下のように設定します。
![alt text](image-29.png)

(5) 以下の状態になります。これでweb-vs用のACLは完成です。
![alt text](image-30.png)