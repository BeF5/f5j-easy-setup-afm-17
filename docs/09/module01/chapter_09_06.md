# wild-ftp-vs用のACL設定

本VSでも、通信ログを取得することのみを目的としたルールを適用します。

ここでも、VSへ直接ルールを設定してみます。

(1) 「Local Traffic」→「Virtual Servers」→「Virtual Sever list」で表示された該当VSをクリックし、「Security」タブ→ 「Policies」をクリックすると、以下の画面が表示されます。「Add」ボタンを押します。
![alt text](image-46.png)

(2) 以下のように設定します。
![alt text](image-47.png)

(3) 以下の状態になります。これでwild-ftp-vs用のACLは完成です。
![alt text](image-48.png)