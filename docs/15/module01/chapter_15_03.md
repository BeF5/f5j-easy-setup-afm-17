# Active機(bigXXX.f5jp.local)の設定

## HA VLANの設定
「Network」→「VLANs」で表示された画面の右上にある「Create」ボタンを押し、HA用VLANを設定します。
![alt text](image-6.png)

## HA VLANのSelf IP設定
「Network」→「Self IPs」で表示された画面の右上にある「Create」ボタンを押し、HA用VLANのIPを設定します。
![alt text](image-7.png)

(1) 一覧は以下のような状態になります。
![alt text](image-8.png)

## Device Managementの設定
次に、「Device Management」→「Devices」で、自分自身：bigXXX.f5jp.local(self)を選択します。
![alt text](image-9.png)

(1) 「Device Connectivity」プルダウンメニューから「ConfigSync」を選択し、HA VLANに指定したIPアドレスを選択し「Update」を押します。
![alt text](image-10.png)

(2) 「Device Connectivity」プルダウンメニューから「Network Failover」を選択し、「Add」ボタンを押します。
![alt text](image-11.png)

(3) HA VLANに設定したIPアドレスを選択します。
![alt text](image-12.png)

(4) 「Device Connectivity」プルダウンメニューから「Mirroring」を選択し、HA VLANに指定したIPアドレスをプライマリに指定します。任意ですが、ここではSecondaryとして、Observe VLANに指定したIPアドレスを選択しています。選択後、「Update」を押します。
![alt text](image-13.png)
