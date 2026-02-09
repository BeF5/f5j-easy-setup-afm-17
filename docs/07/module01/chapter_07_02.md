# wild-xxx-vsの設定

## wild-poolの設定
本poolでは多数のサービスが動いており、個々の全サービスに一つずつヘルスモニターを設定してもよいのですが、本ガイドでは簡易的にICMPによるヘルスモニターとします。

「Local Traffic」→「Pools」で表示された画面右上の「Create」ボタンを押し、現れた画面で以下のように設定します。
![alt text](image-5.png)

## wild-tcp-vsの設定
「Local Traffic」→「Virtual Servers」で表示された画面右上の「Create」ボタンを押し、現れた画面で以下のように設定します。
![alt text](image-6.png)
～略～
![alt text](image-7.png)

## wild-ftp-vsの設定
同様の方法で、ftp用VSを設定します。
![alt text](image-8.png)
～略～
![alt text](image-9.png)

## wild-dns-vsの設定
同様の方法で、DNS用VSを設定します。
![alt text](image-10.png)
![alt text](image-11.png)