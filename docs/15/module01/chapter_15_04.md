# Standby機(bigYYY.f5jp.local)の設定

Active機でのVLAN，Self IP，Devicesの設定と同様の設定をStandby機に対しても行います。

## VLANの設定
Standby機に設定されたVLANは以下のようになります。
![alt text](image-14.png)

## Self IPの設定
Standby機に設定されたSelf IPアドレスは以下のようになります。
![alt text](image-15.png)

## NTPの設定
NTP設定を行います。
![alt text](image-16.png)

## Device Managementの設定
次に、「Device Management」→「Devices」で、自分自身：bigYYY.f5jp.local(self)を選択し、Active機同様に、 Device Connectivityの設定を行います。

(1) ConfigSync設定
![alt text](image-17.png)

(2) Network Failover設定
![alt text](image-18.png)

(3) Mirroring設定
![alt text](image-19.png)

## Route Domain関連の設定 
(1) Active機同様に、RD1-Partitionを作ります。
![alt text](image-20.png)

(2) RD1-Partitionに切り替えます。
![alt text](image-22.png)

(3) Active機同様にVLANを作ります。
![alt text](image-21.png)

(4) Active機同様にルートドメイン：RD1を作ります。
![alt text](image-23.png)

(5) Active機同様にRD1のSelf IPを設定します。
![alt text](image-24.png)
