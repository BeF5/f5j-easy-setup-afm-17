# IPインテリジェンスの動作確認

ネットワーク図中の Proxy：54.235.78.122 から、IP Intelligence設定を行ったVSへアクセスして、Proxy検知しているかを確認します。

(1) 10.99.88.227へ、SSHでログインします。  
(このサーバに、54.235.78.122のアドレスをセカンダリとして設定しています。) 

(2) Curlを使って、Virtual ServerにHTTP/HTTPSでアクセスします。

```sh
# curl --interface 54.235.78.122 http://10.99.1.AAA/
# curl –k --interface 54.235.78.122 https://10.99.1.AAA/ 
# curl --interface 54.235.78.122 http://10.99.1.BBB/ 
# curl –k --interface 54.235.78.122 https://10.99.1.BBB/
```

(3) IP Intelligenceのログの確認

「Security」→「Event Logs」→「Network」→「IP Intelligence」で、Proxyを検知できていることを確認します。
