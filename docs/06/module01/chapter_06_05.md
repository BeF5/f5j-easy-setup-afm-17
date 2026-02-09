# ログ出力先：Facilityの変更

Syslogの出力は、デフォルトのFacilityはLocal0となっています。

本ガイドの構成ではSyslogサーバは１台を共有するため、全員が同じFacilityに出力するとログを確認しづらくなるので、個々にFacilityを分けることにしています。

以下のステップで、SyslogのFacilityを変更してください。

1. BIG-IPに対して、TeraTermを使ってSSHでログイン。

2. 以下のコマンドを実行して、Facilityを確認。

```tmsh
# tmsh
# list sys log-config destination remote-syslog HSL-Format all-properties
sys log-config destination remote-syslog HSL-Format {
app-service none
default-facility local0
default-severity info
description none
format rfc5424
remote-high-speed-log HSL-Destination
}
```

3. 以下のコマンドを実行して、Facilityを変更。

```tmsh
# modify sys log-config destination remote-syslog HSL-Format { default-facility【※注※】}
```
(【※注意※】下線部のFacilityを各自に割当てられた値”localx”に変更)

4. もう一度以下のコマンドを実行して、変更できたことを確認。

```tmsh
# list sys log-config destination remote-syslog HSL-Format all-properties
sys log-config destination remote-syslog HSL-Format {
app-service none
default-facility local7 ←例：Facilityを local7に変更した場合
default-severity info
description none
format rfc5424
remote-high-speed-log HSL-Destination
}
```