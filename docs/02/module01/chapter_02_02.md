# 想定シナリオ

あるテナント用として Route Domain(RD1)を一つ作ります。

このテナントは2つのサーバリソースプールを保持しており、これらをインターネットからのネットワーク攻撃から守りたいという要件があります。

- Web pool: HTTPとHTTPSを提供するサーバ群
- Wild pool: HTTPとHTTPSの他に、Webmin(Port:10000)、FTP、およびDNSサービスを提供

    両サーバリソースプールでは、管理用途としてSSHサービスが動作していますが、メンテナンスを目的として、ある一定時間のみインターネットからのアクセスを許可する設定とします。

    wild-poolにはもう一つの管理用としてWebminが動作していますが、こちらはある特定のIPアドレス(管理者のIPアドレスであると想定)からのアクセスのみ許可する設定とします。

Global、Route Domain、Virtual Serverで取得したログはすべて、図中のSyslogサーバへ送ることとします。

![alt text](image.png)

以降、Global、Route Domain、Virtual Serverの各ポリシーについて説明します。
