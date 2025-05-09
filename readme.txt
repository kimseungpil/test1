welcome to korea.
i like people.
you luck.


工藤　宏和
小林　澄久
阿部　匡弘

松原　翔
本城　星弥
大塚　侑哉
丸山　朋哉
野元　峰明
三宅　博昭



藤原　正章

https://dong-it-engineer.tistory.com/55

[Linux] Failed to start LSB: Bring up/down networking
출처: https://dong-it-engineer.tistory.com/55 [IT기술정보올리는곳:티스토리]

대부분의 경우 설정파일에 이상이 있으며, 특히 구성상 모순적인 설정이 들어가 있는지 확인해야한다.
(e.g. IP를 수동으로 넣었으나, dhcp로 지정한 경우)
출처: https://dong-it-engineer.tistory.com/55 [IT기술정보올리는곳:티스토리]


systemctl stop NetworkManager
systemctl disable NetworkManager
systemctl start network.service

[root@HE-ALL-SRV ~]# systemctl start network.service
Job for network.service failed because the control process exited with error code. See "systemctl status network.service" and "journalctl -xe" for details.
[root@HE-ALL-SRV ~]# 


[root@HE-ALL-SRV ~]# journalctl -xe
 4月 28 10:30:34 HE-ALL-SRV scsrvc[3907]: McAfee Solidifier[3907]: McAfee Solidifier detected modification of '/etc/resolv.conf.save' by program /
 4月 28 10:30:34 HE-ALL-SRV scsrvc[3907]: McAfee Solidifier[3907]: McAfee Solidifier detected modification of '/etc/resolv.conf' by program /etc/s
 4月 28 10:30:34 HE-ALL-SRV NET[12479]: /etc/sysconfig/network-scripts/ifup-post : updated /etc/resolv.conf
 4月 28 10:30:34 HE-ALL-SRV network[11998]: [  OK  ]
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: network.service: control process exited, code=exited status=1
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: Failed to start LSB: Bring up/down networking.
-- Subject: Unit network.service has failed
-- Defined-By: systemd
-- Support: http://lists.freedesktop.org/mailman/listinfo/systemd-devel
-- 
-- Unit network.service has failed.
-- 
-- The result is failed.
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: Unit network.service entered failed state.
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: network.service failed.
 4月 28 10:30:34 HE-ALL-SRV polkitd[3280]: Unregistered Authentication Agent for unix-process:11991:212156 (system bus name :1.239, object path /o
 4月 28 10:30:50 HE-ALL-SRV nautilus-deskto[6263]: g_simple_action_set_enabled: assertion 'G_IS_SIMPLE_ACTION (simple)' failed
 4月 28 10:31:11 HE-ALL-SRV nautilus-deskto[6263]: g_simple_action_set_enabled: assertion 'G_IS_SIMPLE_ACTION (simple)' failed
lines 1995-2021/2021 (END)
 4月 28 10:30:34 HE-ALL-SRV scsrvc[3907]: McAfee Solidifier[3907]: McAfee Solidifier detected modification of '/etc/resolv.conf.save' by program /
 4月 28 10:30:34 HE-ALL-SRV scsrvc[3907]: McAfee Solidifier[3907]: McAfee Solidifier detected modification of '/etc/resolv.conf' by program /etc/s
 4月 28 10:30:34 HE-ALL-SRV NET[12479]: /etc/sysconfig/network-scripts/ifup-post : updated /etc/resolv.conf
 4月 28 10:30:34 HE-ALL-SRV network[11998]: [  OK  ]
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: network.service: control process exited, code=exited status=1
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: Failed to start LSB: Bring up/down networking.
-- Subject: Unit network.service has failed
-- Defined-By: systemd
-- Support: http://lists.freedesktop.org/mailman/listinfo/systemd-devel
-- 
-- Unit network.service has failed.
-- 
-- The result is failed.
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: Unit network.service entered failed state.
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: network.service failed.
 4月 28 10:30:34 HE-ALL-SRV polkitd[3280]: Unregistered Authentication Agent for unix-process:11991:212156 (system bus name :1.239, object path /o
 4月 28 10:30:50 HE-ALL-SRV nautilus-deskto[6263]: g_simple_action_set_enabled: assertion 'G_IS_SIMPLE_ACTION (simple)' failed
 4月 28 10:31:11 HE-ALL-SRV nautilus-deskto[6263]: g_simple_action_set_enabled: assertion 'G_IS_SIMPLE_ACTION (simple)' failed
~
lines 1995-2021/2021 (END)
 4月 28 10:30:34 HE-ALL-SRV scsrvc[3907]: McAfee Solidifier[3907]: McAfee Solidifier detected modification of '/etc/resolv.conf.save' by program /
 4月 28 10:30:34 HE-ALL-SRV scsrvc[3907]: McAfee Solidifier[3907]: McAfee Solidifier detected modification of '/etc/resolv.conf' by program /etc/s
 4月 28 10:30:34 HE-ALL-SRV NET[12479]: /etc/sysconfig/network-scripts/ifup-post : updated /etc/resolv.conf
 4月 28 10:30:34 HE-ALL-SRV network[11998]: [  OK  ]
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV network[11998]: RTNETLINK answers: File exists
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: network.service: control process exited, code=exited status=1
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: Failed to start LSB: Bring up/down networking.
-- Subject: Unit network.service has failed
-- Defined-By: systemd
-- Support: http://lists.freedesktop.org/mailman/listinfo/systemd-devel
-- 
-- Unit network.service has failed.
-- 
-- The result is failed.
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: Unit network.service entered failed state.
 4月 28 10:30:34 HE-ALL-SRV systemd[1]: network.service failed.
 4月 28 10:30:34 HE-ALL-SRV polkitd[3280]: Unregistered Authentication Agent for unix-process:11991:212156 (system bus name :1.239, object path /o
 4月 28 10:30:50 HE-ALL-SRV nautilus-deskto[6263]: g_simple_action_set_enabled: assertion 'G_IS_SIMPLE_ACTION (simple)' failed
 4月 28 10:31:11 HE-ALL-SRV nautilus-deskto[6263]: g_simple_action_set_enabled: assertion 'G_IS_SIMPLE_ACTION (simple)' failed
~
~
[root@HE-ALL-SRV MZ0000Z0000001]# systemctl status network.service
● network.service - LSB: Bring up/down networking
   Loaded: loaded (/etc/rc.d/init.d/network; bad; vendor preset: disabled)
   Active: failed (Result: exit-code) since 月 2025-04-28 11:14:18 JST; 2min 52s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 19745 ExecStart=/etc/rc.d/init.d/network start (code=exited, status=1/FAILURE)

 4月 28 11:14:18 HE-ALL-SRV network[19745]: RTNETLINK answers: File exists
 4月 28 11:14:18 HE-ALL-SRV network[19745]: RTNETLINK answers: File exists
 4月 28 11:14:18 HE-ALL-SRV network[19745]: RTNETLINK answers: File exists
 4月 28 11:14:18 HE-ALL-SRV network[19745]: RTNETLINK answers: File exists
 4月 28 11:14:18 HE-ALL-SRV network[19745]: RTNETLINK answers: File exists
 4月 28 11:14:18 HE-ALL-SRV network[19745]: RTNETLINK answers: File exists
 4月 28 11:14:18 HE-ALL-SRV systemd[1]: network.service: control process exited, code=exited status=1
 4月 28 11:14:18 HE-ALL-SRV systemd[1]: Failed to start LSB: Bring up/down networking.
 4月 28 11:14:18 HE-ALL-SRV systemd[1]: Unit network.service entered failed state.
 4月 28 11:14:18 HE-ALL-SRV systemd[1]: network.service failed.
[root@HE-ALL-SRV MZ0000Z0000001]# 
[root@HE-ALL-SRV MZ0000Z0000001]# s



nmcli connection
$ nmcli connection modify enp0s3 connection.autoconnect no
$ systemctl restart network.service

$ service network restart





# service NetworkManager stop
# chkconfig NetworkManager off

# /etc/init.d/network restart
Restarting network (via systemctl):                        [  OK  ]

ip addr add 192.168.1.4/24 dev venet0
ip route add default via 192.168.1.1

# LANG=C ifup venet0
Error: no device found for connection 'System venet0'.

# ifup venet0
エラー: 接続 'System venet0'用のデバイスが見つかりません.

[root@HE-ALL-SRV MZ0000Z0000000]# systemctl status network.service
● network.service - LSB: Bring up/down networking
   Loaded: loaded (/etc/rc.d/init.d/network; bad; vendor preset: disabled)
   Active: failed (Result: exit-code) since 月 2025-04-28 09:57:29 JST; 19min ago
     Docs: man:systemd-sysv-generator(8)
  Process: 3935 ExecStart=/etc/rc.d/init.d/network start (code=exited, status=1/FAILURE)

 4月 28 09:57:27 HE-ALL-SRV network[3935]: インターフェース enp0s9 を活性化中:  INFO      : [ipv6_wai… state
 4月 28 09:57:27 HE-ALL-SRV ipv6_wait_tentative[4218]: Waiting for interface enp0s9 IPv6 address(es) t...ate
 4月 28 09:57:28 HE-ALL-SRV network[3935]: INFO      : [ipv6_wait_tentative] Waiting for interface en...tate
 4月 28 09:57:28 HE-ALL-SRV ipv6_wait_tentative[4249]: Waiting for interface enp0s9 IPv6 address(es) t...ate
 4月 28 09:57:29 HE-ALL-SRV NET[4291]: /etc/sysconfig/network-scripts/ifup-post : updated /etc/resolv.conf
 4月 28 09:57:29 HE-ALL-SRV network[3935]: [  OK  ]
 4月 28 09:57:29 HE-ALL-SRV systemd[1]: network.service: control process exited, code=exited status=1
 4月 28 09:57:29 HE-ALL-SRV systemd[1]: Failed to start LSB: Bring up/down networking.
 4月 28 09:57:29 HE-ALL-SRV systemd[1]: Unit network.service entered failed state.
 4月 28 09:57:29 HE-ALL-SRV systemd[1]: network.service failed.
Hint: Some lines were ellipsized, use -l to show in full.
[root@HE-ALL-SRV MZ0000Z0000000]# 



















[root@HE-ALL-SRV ~]# systemctl status network.service -l
● network.service - LSB: Bring up/down networking
   Loaded: loaded (/etc/rc.d/init.d/network; bad; vendor preset: disabled)
   Active: failed (Result: exit-code) since 木 2025-05-08 19:49:30 JST; 1min 25s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 3535 ExecStart=/etc/rc.d/init.d/network start (code=exited, status=1/FAILURE)

 5月 08 19:49:29 HE-ALL-SRV ipv6_wait_tentative[4265]: Waiting for interface enp0s8 IPv6 address(es) to leave the 'tentative' state
 5月 08 19:49:30 HE-ALL-SRV NET[4303]: /etc/sysconfig/network-scripts/ifup-post : updated /etc/resolv.conf
 5月 08 19:49:30 HE-ALL-SRV network[3535]: [  OK  ]
 5月 08 19:49:30 HE-ALL-SRV network[3535]: インターフェース enp0s9 を活性化中:  ERROR     : [/etc/sysconfig/network-scripts/ifup-eth] Error, some other host (0A:00:27:00:00:11) already uses address 10.161.204.246.
 5月 08 19:49:30 HE-ALL-SRV /etc/sysconfig/network-scripts/ifup-eth[4343]: Error, some other host (0A:00:27:00:00:11) already uses address 10.161.204.246.
 5月 08 19:49:30 HE-ALL-SRV network[3535]: [失敗]
 5月 08 19:49:30 HE-ALL-SRV systemd[1]: network.service: control process exited, code=exited status=1
 5月 08 19:49:30 HE-ALL-SRV systemd[1]: Failed to start LSB: Bring up/down networking.
 5月 08 19:49:30 HE-ALL-SRV systemd[1]: Unit network.service entered failed state.
 5月 08 19:49:30 HE-ALL-SRV systemd[1]: network.service failed.
[root@HE-ALL-SRV ~]# 
[root@HE-ALL-SRV ~]# 
[root@HE-ALL-SRV ~]# systemctl status NetworkManeger
Unit NetworkManeger.service could not be found.
[root@HE-ALL-SRV ~]# systemctl status NetworkManager
● NetworkManager.service - Network Manager
   Loaded: loaded (/usr/lib/systemd/system/NetworkManager.service; disabled; vendor preset: enabled)
   Active: inactive (dead)
     Docs: man:NetworkManager(8)
[root@HE-ALL-SRV ~]# 
[root@HE-ALL-SRV ~]# 
[root@HE-ALL-SRV ~]# 
[r




----




PS C:\Users\smng>
PS C:\Users\smng> ipconfig /all

Windows IP 構成

   ホスト名. . . . . . . . . . . . . . .: DESKTOP-C3DRR4I
   プライマリ DNS サフィックス . . . . .:
   ノード タイプ . . . . . . . . . . . .: ハイブリッド
   IP ルーティング有効 . . . . . . . . .: いいえ
   WINS プロキシ有効 . . . . . . . . . .: いいえ

イーサネット アダプター vbox0:

   接続固有の DNS サフィックス . . . . .:
   説明. . . . . . . . . . . . . . . . .: VirtualBox Host-Only Ethernet Adapter
   物理アドレス. . . . . . . . . . . . .: 0A-00-27-00-00-11
   DHCP 有効 . . . . . . . . . . . . . .: いいえ
   自動構成有効. . . . . . . . . . . . .: はい
   リンクローカル IPv6 アドレス. . . . .: fe80::c152:dc1a:a4c3:8fea%17(優先)
   IPv4 アドレス . . . . . . . . . . . .: 10.161.204.246(優先)
   サブネット マスク . . . . . . . . . .: 255.255.255.0
   デフォルト ゲートウェイ . . . . . . .:
   DHCPv6 IAID . . . . . . . . . . . . .: 688521255
   DHCPv6 クライアント DUID. . . . . . .: 00-01-00-01-2F-9D-DF-77-64-4E-D7-24-18-A7
   DNS サーバー. . . . . . . . . . . . .: fec0:0:0:ffff::1%1
                                          fec0:0:0:ffff::2%1
                                          fec0:0:0:ffff::3%1
   NetBIOS over TCP/IP . . . . . . . . .: 有効

Wireless LAN adapter Wi-Fi:

   メディアの状態. . . . . . . . . . . .: メディアは接続されていません
   接続固有の DNS サフィックス . . . . .:
   説明. . . . . . . . . . . . . . . . .: Realtek 8852CE WiFi 6E PCI-E NIC
   物理アドレス. . . . . . . . . . . . .: 40-1A-58-78-44-D0
   DHCP 有効 . . . . . . . . . . . . . .: はい
   自動構成有効. . . . . . . . . . . . .: はい

Wireless LAN adapter ローカル エリア接続* 1:

   メディアの状態. . . . . . . . . . . .: メディアは接続されていません
   接続固有の DNS サフィックス . . . . .:
   説明. . . . . . . . . . . . . . . . .: Microsoft Wi-Fi Direct Virtual Adapter
   物理アドレス. . . . . . . . . . . . .: 42-1A-58-78-44-D0
   DHCP 有効 . . . . . . . . . . . . . .: はい
   自動構成有効. . . . . . . . . . . . .: はい

Wireless LAN adapter ローカル エリア接続* 2:

   メディアの状態. . . . . . . . . . . .: メディアは接続されていません
   接続固有の DNS サフィックス . . . . .:
   説明. . . . . . . . . . . . . . . . .: Microsoft Wi-Fi Direct Virtual Adapter #2
   物理アドレス. . . . . . . . . . . . .: C2-1A-58-78-44-D0
   DHCP 有効 . . . . . . . . . . . . . .: はい
   自動構成有効. . . . . . . . . . . . .: はい

イーサネット アダプター イーサネット:

   接続固有の DNS サフィックス . . . . .:
   説明. . . . . . . . . . . . . . . . .: Realtek PCIe GbE Family Controller
   物理アドレス. . . . . . . . . . . . .: 64-4E-D7-24-18-A7
   DHCP 有効 . . . . . . . . . . . . . .: はい
   自動構成有効. . . . . . . . . . . . .: はい
   IPv6 アドレス . . . . . . . . . . . .: fd00::8000:2049:0:b531(優先)
   リンクローカル IPv6 アドレス. . . . .: fe80::bad0:a90e:a289:3adf%10(優先)
   デフォルト ゲートウェイ . . . . . . .:
   DNS サーバー. . . . . . . . . . . . .: fec0:0:0:ffff::1%1
                                          fec0:0:0:ffff::2%1
                                          fec0:0:0:ffff::3%1
   NetBIOS over TCP/IP . . . . . . . . .: 無効

イーサネット アダプター Bluetooth ネットワーク接続:

   メディアの状態. . . . . . . . . . . .: メディアは接続されていません
   接続固有の DNS サフィックス . . . . .:
   説明. . . . . . . . . . . . . . . . .: Bluetooth Device (Personal Area Network)
   物理アドレス. . . . . . . . . . . . .: 40-1A-58-78-44-D1
   DHCP 有効 . . . . . . . . . . . . . .: はい
   自動構成有効. . . . . . . . . . . . .: はい
PS C:\Users\smng>

