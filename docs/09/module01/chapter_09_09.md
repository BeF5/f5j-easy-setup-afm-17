# 外部出力されたSyslogの確認

ここまでの設定で、ロギングを有効にしたルールにヒットする通信が発生すると、Syslogサーバ (10.99.5.219，10.99.5.239) へログが出力される状態になっています。

本ガイドでのSyslog確認方法を示します。

(1) Syslogサーバ：10.99.88.219へSSHでログインします。

    Username： user
    Password: user 

(2) 以下のコマンドを実行します。

```sh
[user@PEOLD-Cent-009 ~]# cd /var/log/AFM
[user@PEOLD-Cent-009 AFM]# tail -f USER_SYSLOG-NG_local7 【※注※】自身の Facility 名のファイル
```

(3) ログ出力を有効にしたポリシーを適用したVirtual Serverにアクセスし、ログが出力されていることを確認します。

以下は、サンプルログです。

```sh
Mar 15 12:24:32 10.99.5.207 1 2015-03-14T20:24:34-07:00 big207.f5jp.local tmm 14807 23003137
[F5@12276 acl_policy_name="" acl_policy_type="Enforced" acl_rule_name="Global-Reject-ALL"
action="Reject" hostname="big207.f5jp.local" bigip_mgmt_ip="10.99.88.207" context_name=""
context_type="Global" date_time="Mar 14 2015 20:24:33" dest_ip="224.0.0.251" dst_geo="No-lookup"
dest_port="5353" device_product="Advanced Firewall Module" device_vendor="F5" device_version=""
drop_reason="Policy" errdefs_msgno="23003137" errdefs_msg_name="Network Event"
flow_id="0000000000000000" ip_protocol="UDP" severity="8" partition_name="Common" route_domain="0"
sa_translation_pool="" sa_translation_type="" source_ip="10.99.5.239" src_geo="No-lookup"
source_port="5353" translated_dest_ip="" translated_dest_port="" translated_ip_protocol=""
translated_route_domain="" translated_source_ip="" translated_source_port="" translated_vlan=""
vlan="/Common/Ovserve"] 224.0.0.251,10.99.5.239,5353,5353
```