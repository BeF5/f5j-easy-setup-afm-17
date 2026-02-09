# 基本設定

## 管理ポートへのGUIアクセス
管理用PCから、設定したBIG-IPの管理IPアドレスへ、HTTPSでアクセスします。

【※注※】https://10.99.88.XXX

デフォルトの証明書は、正式に取得した証明書ではないため、以下のような画面が現れますが、「続行する」を選択してください。
![alt text](image.png)

(1) ログイン画面が現れますので、以下のデフォルトのIDとPasswordでログインしてください。
- ID：admin
- Password：admin

![alt text](image-1.png)

 (2) 「Next」ボタンを押します。
![alt text](image-2.png)

(3) ライセンス画面が出ます。「Next」ボタンを押します。
![alt text](image-3.png)

(4) プロビジョニング画面がでますので、「AFM」にチェックを入れます。
![alt text](image-4.png)

(5) SSL証明書の確認がなされますが、デフォルトのまま、「Next」ボタンを押します。
![alt text](image-5.png)

(6) ホスト名、タイムゾーン、Root/Adminそれぞれのパスワードを設定します。「Next」ボタンを押します。
![alt text](image-6.png)

設定したパスワードでログインを試みるよう、ログアウト→ログインするように指示があります。「OK」ボタンを押します。

![alt text](image-7.png)


(7) Username ＝ Adminと、設定したパスワードで再度ログインします。
![alt text](image-8.png)


(8) この後、Standard Network Configurationの「Next」を押すことでウィザード形式にて冗長化も含めた設定が可能ですが、ここではスタンドアローン構成にするため、Advanced Network Configurationの「Finished」ボタンを押します。
![alt text](image-9.png)

```{toctree}
:maxdepth: 1
:glob:
module01/**
```
