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

