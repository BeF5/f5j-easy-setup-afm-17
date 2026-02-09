# ステージング用ポリシーの設定

ステージング用ポリシーの設定方法を示します。

(1) 「Security」→「Network Firewall」→「Policies」で表示された画面の右上にある「Create」ボタンを押すと、以下の画面が表示されます。「Name」だけ入力して「Finished」ボタンを押します。
![alt text](image.png)

(2) 作成したPolicyをクリックします。
![alt text](image-1.png)

(3) 「Add」ボタンを押します。
![alt text](image-2.png)

(4) HTTPS(443)の許可設定以下のように設定します。
![alt text](image-3.png)

(5) 全拒否ルールの設定今一度、「Add」ボタンを押して、以下のように設定します。
![alt text](image-4.png)

(6) 以下の状態になります。
![alt text](image-5.png)

(7) VSへのPolicy割当て 

「Local Traffic」→「Virtual Servers」→「Virtual Sever list」で表示されたweb-vsをクリックし、「Security」タブ→ 「Policies」をクリックし、現れた画面で以下のように設定します。
![alt text](image-6.png)
