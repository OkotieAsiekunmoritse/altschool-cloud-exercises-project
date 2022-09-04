# MORE IMPORTANT LINUX COMMANDS #
**1. Cal** <br>
This command is used to display a calendar on the system, showcasing the specified month or year

```
vagrant@ubuntu-focal:~$ cal
    August 2022
Su Mo Tu We Th Fr Sa
    1  2  3  4  5  6
 7  8  9 10 11 12 13
14 15 16 17 18 19 20
21 22 23 24 25 26 27
28 29 30 31
```
```
![cal](https://user-images.githubusercontent.com/108562214/188336533-45997c17-7003-4db7-b9a3-ae47b4672c0f.png)


```

**2. cat /proc/cpuinfo**<br>
This command is used to display all information,and every other command and utility gets its output from this file.

```
vagrant@ubuntu-focal:~$ cat /proc/cpuinfo
processor       : 0
vendor_id       : GenuineIntel
cpu family      : 6
model           : 78
model name      : Intel(R) Core(TM) i3-6006U CPU @ 2.00GHz
stepping        : 3
cpu MHz         : 1991.998
cache size      : 3072 KB
physical id     : 0
siblings        : 2
core id         : 0
cpu cores       : 2
apicid          : 0
initial apicid  : 0
fpu             : yes
fpu_exception   : yes
cpuid level     : 22
wp              : yes
flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx rdtscp lm constant_tsc rep_good nopl xtopology nonstop_tsc cpuid tsc_known_freq pni pclmulqdq ssse3 cx16 pcid sse4_1 sse4_2 x2apic movbe popcnt aes xsave avx rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single pti fsgsbase avx2 invpcid rdseed clflushopt md_clear flush_l1d
bugs            : cpu_meltdown spectre_v1 spectre_v2 spec_store_bypass l1tf mds swapgs itlb_multihit srbds mmio_stale_data
bogomips        : 3983.99
clflush size    : 64
cache_alignment : 64
address sizes   : 39 bits physical, 48 bits virtual
power management:

processor       : 1
vendor_id       : GenuineIntel
cpu family      : 6
model           : 78
model name      : Intel(R) Core(TM) i3-6006U CPU @ 2.00GHz
stepping        : 3
cpu MHz         : 1991.998
cache size      : 3072 KB
physical id     : 0
siblings        : 2
core id         : 1
cpu cores       : 2
apicid          : 1
initial apicid  : 1
fpu             : yes
fpu_exception   : yes
cpuid level     : 22
wp              : yes
flags           : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx rdtscp lm constant_tsc rep_good nopl xtopology nonstop_tsc cpuid tsc_known_freq pni pclmulqdq ssse3 cx16 pcid sse4_1 sse4_2 x2apic movbe popcnt aes xsave avx rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single pti fsgsbase avx2 invpcid rdseed clflushopt md_clear flush_l1d
bugs            : cpu_meltdown spectre_v1 spectre_v2 spec_store_bypass l1tf mds swapgs itlb_multihit srbds mmio_stale_data
bogomips        : 3983.99
clflush size    : 64
cache_alignment : 64
address sizes   : 39 bits physical, 48 bits virtual
power management:
```
```
![catproccpuinfo](https://user-images.githubusercontent.com/108562214/186907210-7911b0dd-98b8-4db7-b36d-75a63ee103a7.png)
```

**3. dig**<br>
This command can be for querying DNS nameservers for information about host, mail exchanges, nameservers, and related information. It can be used from any Linux(Unix) or Macintosh operatins system. The most typical use of dig is to simply query a single host.
From the example below, I used the dig domain
```
vagrant@ubuntu-focal:~$ dig domain

; <<>> DiG 9.16.1-Ubuntu <<>> domain
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: SERVFAIL, id: 34011
;; flags: qr rd ra; QUERY: 1, ANSWER: 0, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;domain.                                IN      A

;; Query time: 4 msec
;; SERVER: 127.0.0.53#53(127.0.0.53)
;; WHEN: Fri Aug 26 21:03:12 WAT 2022
;; MSG SIZE  rcvd: 35
```

```
![dig domain](https://user-images.githubusercontent.com/108562214/186907129-9d606b86-3f55-40e3-8aea-08e56fbb84a1.png)

```

**4. w**<br>
This commands is a built-in tool that allows administrators to view information about users that are currently logged in. This includes their username, where they are logged in from, and what they are currently doing.
```
vagrant@ubuntu-focal:~$ w
 21:04:08 up  5:26,  1 user,  load average: 0.00, 0.02, 0.00
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
vagrant  pts/0    10.0.2.2         17:07    0.00s  0.26s  0.00s w
```
```
![w png](https://user-images.githubusercontent.com/108562214/186907339-3d257610-4d35-4c21-b5c5-d30c65aec7d2.png)
```

**5. netstat**<br>
The command  network statistics ( netstat ) command is a networking tool used for troubleshooting and configuration, that can also serve as a monitoring tool for connections over the network. Both incoming and outgoing connections, routing tables, port listening, and usage statistics are common uses for the command.

```
vagrant@ubuntu-focal:~$ netstat
Active Internet connections (w/o servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State
tcp        0    112 ubuntu-focal:ssh        _gateway:52990          ESTABLISHED
Active UNIX domain sockets (w/o servers)
Proto RefCnt Flags       Type       State         I-Node   Path
unix  3      [ ]         DGRAM                    13996    /run/systemd/notify
unix  2      [ ]         DGRAM                    31965    /run/user/1000/systemd/notify
unix  2      [ ]         DGRAM                    14013    /run/systemd/journal/syslog
unix  8      [ ]         DGRAM                    14023    /run/systemd/journal/dev-log
unix  8      [ ]         DGRAM                    14027    /run/systemd/journal/socket
unix  2      [ ]         DGRAM                    21156
unix  3      [ ]         STREAM     CONNECTED     21831    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     22596    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     18299    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     32067
unix  3      [ ]         STREAM     CONNECTED     32068
unix  3      [ ]         STREAM     CONNECTED     21166
unix  2      [ ]         STREAM     CONNECTED     31794
unix  3      [ ]         STREAM     CONNECTED     22962
unix  3      [ ]         STREAM     CONNECTED     19387    /run/systemd/journal/stdout
unix  2      [ ]         DGRAM                    31811
unix  3      [ ]         STREAM     CONNECTED     22963
unix  3      [ ]         STREAM     CONNECTED     21479    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     22958
unix  3      [ ]         STREAM     CONNECTED     22595
unix  3      [ ]         STREAM     CONNECTED     19303
unix  3      [ ]         STREAM     CONNECTED     31937    /run/systemd/journal/stdout
unix  2      [ ]         DGRAM                    13243
unix  3      [ ]         STREAM     CONNECTED     21789    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     21475    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     14818
unix  3      [ ]         STREAM     CONNECTED     22022    /run/dbus/system_bus_socket
unix  3      [ ]         DGRAM                    14830
unix  3      [ ]         STREAM     CONNECTED     18371
unix  3      [ ]         STREAM     CONNECTED     18577
unix  3      [ ]         STREAM     CONNECTED     22021
unix  3      [ ]         STREAM     CONNECTED     18005    /run/systemd/journal/stdout
unix  2      [ ]         DGRAM                    14827
unix  3      [ ]         STREAM     CONNECTED     31933
unix  2      [ ]         DGRAM                    21995
unix  3      [ ]         STREAM     CONNECTED     21474    /run/dbus/system_bus_socket
unix  2      [ ]         DGRAM                    18090
unix  3      [ ]         STREAM     CONNECTED     21473    /run/dbus/system_bus_socket
unix  3      [ ]         DGRAM                    18476
unix  3      [ ]         STREAM     CONNECTED     20680
unix  3      [ ]         STREAM     CONNECTED     22685
unix  3      [ ]         STREAM     CONNECTED     18803
unix  3      [ ]         DGRAM                    14829
unix  3      [ ]         STREAM     CONNECTED     18940
unix  2      [ ]         DGRAM                    18472
unix  3      [ ]         STREAM     CONNECTED     19386
unix  3      [ ]         DGRAM                    18478
unix  3      [ ]         STREAM     CONNECTED     18578    /run/systemd/journal/stdout
unix  2      [ ]         DGRAM                    21065
unix  3      [ ]         DGRAM                    18477
unix  3      [ ]         STREAM     CONNECTED     22954
unix  3      [ ]         STREAM     CONNECTED     15542    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     19153
unix  3      [ ]         STREAM     CONNECTED     18369
unix  3      [ ]         DGRAM                    18479
unix  3      [ ]         STREAM     CONNECTED     18470
unix  2      [ ]         DGRAM                    14300
unix  3      [ ]         STREAM     CONNECTED     18802
unix  3      [ ]         STREAM     CONNECTED     31579    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     21478    /run/dbus/system_bus_socket
unix  2      [ ]         DGRAM                    31943
unix  3      [ ]         STREAM     CONNECTED     23699
unix  3      [ ]         STREAM     CONNECTED     19796    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     21471
unix  3      [ ]         DGRAM                    31966
unix  3      [ ]         STREAM     CONNECTED     21477    /run/dbus/system_bus_socket
unix  2      [ ]         DGRAM                    19311
unix  3      [ ]         STREAM     CONNECTED     31969
unix  3      [ ]         STREAM     CONNECTED     18372    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     20584
unix  2      [ ]         DGRAM                    21468
unix  3      [ ]         STREAM     CONNECTED     19313
unix  3      [ ]         STREAM     CONNECTED     21793
unix  3      [ ]         STREAM     CONNECTED     19304    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     21472
unix  2      [ ]         DGRAM                    31956
unix  3      [ ]         STREAM     CONNECTED     21792
unix  3      [ ]         STREAM     CONNECTED     21828    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     23703    /run/dbus/system_bus_socket
unix  3      [ ]         DGRAM                    31967
unix  3      [ ]         STREAM     CONNECTED     19808    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     19646
unix  3      [ ]         STREAM     CONNECTED     19812
unix  3      [ ]         STREAM     CONNECTED     22848    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     16067
unix  3      [ ]         DGRAM                    13997
unix  3      [ ]         STREAM     CONNECTED     21488    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     21476    /run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     19647    /run/systemd/journal/stdout
unix  3      [ ]         STREAM     CONNECTED     16545    /run/systemd/journal/stdout
unix  3      [ ]         DGRAM                    13998
unix  3      [ ]         STREAM     CONNECTED     22847
unix  2      [ ]         DGRAM                    20834
unix  3      [ ]         STREAM     CONNECTED     19795
unix  3      [ ]         STREAM     CONNECTED     21765
unix  3      [ ]         STREAM     CONNECTED     20681    /run/systemd/journal/stdout

```
```
![netstat](https://user-images.githubusercontent.com/108562214/186907438-d2099bad-4bfd-4492-abc7-4b42129efe17.png)
```

**6. lspci**<br>
The command lspci (list PCI) Linux command displays information about each PCI bus on a system. This includes information about the devices connected to the PCI subsystem.
The example below is lspci-tv,where t displays the as a tree diagram, and v displays a verbose version of the output.
```
vagrant@ubuntu-focal:~$ lspci -tv
-[0000:00]-+-00.0  Intel Corporation 440FX - 82441FX PMC [Natoma]
           +-01.0  Intel Corporation 82371SB PIIX3 ISA [Natoma/Triton II]
           +-01.1  Intel Corporation 82371AB/EB/MB PIIX4 IDE
           +-02.0  InnoTek Systemberatung GmbH VirtualBox Graphics Adapter
           +-03.0  Intel Corporation 82540EM Gigabit Ethernet Controller
           +-04.0  InnoTek Systemberatung GmbH VirtualBox Guest Service
           +-05.0  Intel Corporation 82801AA AC'97 Audio Controller
           +-07.0  Intel Corporation 82371AB/EB/MB PIIX4 ACPI
           +-08.0  Intel Corporation 82540EM Gigabit Ethernet Controller
           \-14.0  Broadcom / LSI 53c1030 PCI-X Fusion-MPT Dual Ultra320 SCSI``

```

```
![lspci-tv](https://user-images.githubusercontent.com/108562214/186907546-4d25dd1b-b4a7-445c-972a-01b01392ad0b.png)
```

**7. Ip**<br>
The ip command is a powerful tool for configuring network interfaces that any Linux system administrator should know. It is used to bring interfaces up or down, assign and remove addresses and routes, manage ARP cache, and much more.
The example below, diplays ip a, which displays and modies IP addresses.
```
vagrant@ubuntu-focal:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 02:75:e5:48:55:48 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic enp0s3
       valid_lft 66429sec preferred_lft 66429sec
    inet6 fe80::75:e5ff:fe48:5548/64 scope link
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:97:df:b0 brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.4/24 brd 192.168.56.255 scope global dynamic enp0s8
       valid_lft 428sec preferred_lft 428sec
    inet6 fe80::a00:27ff:fe97:dfb0/64 scope link
       valid_lft forever preferred_lft forever

```

```
![ip  a](https://user-images.githubusercontent.com/108562214/186907688-46265e3b-82be-423b-8064-fd6a6c477679.png)

```

**8. last**<br>
The last command displays information about the last logged-in users. It is  quite convenient and handy when we need to track login activities or investigate a possible security breach. The last command will, by default, take the system log file /var/log/wtmp as the data source to generate reports.
```
vagrant@ubuntu-focal:~$ last
vagrant  pts/0        10.0.2.2         Fri Aug 26 17:07   still logged in
vagrant  pts/0        10.0.2.2         Fri Aug 26 15:39 - 16:44  (01:04)
reboot   system boot  5.4.0-124-generi Fri Aug 26 15:38   still running
vagrant  pts/0        10.0.2.2         Fri Aug 26 05:04 - 06:07  (01:03)
reboot   system boot  5.4.0-124-generi Fri Aug 26 05:02   still running
vagrant  pts/0        10.0.2.2         Thu Aug 25 19:53 - crash  (09:08)
reboot   system boot  5.4.0-124-generi Thu Aug 25 19:51   still running
vagrant  pts/0        10.0.2.2         Thu Aug 25 18:53 - 19:13  (00:19)
reboot   system boot  5.4.0-124-generi Thu Aug 25 18:51 - 19:14  (00:22)
vagrant  pts/0        10.0.2.2         Thu Aug 25 06:56 - crash  (11:55)
reboot   system boot  5.4.0-124-generi Thu Aug 25 06:36 - 19:14  (12:37)
vagrant  pts/0        10.0.2.2         Thu Aug 25 06:21 - 06:34  (00:13)
reboot   system boot  5.4.0-124-generi Thu Aug 25 06:17 - 06:34  (00:17)
vagrant  pts/0        10.0.2.2         Thu Aug 25 06:00 - 06:13  (00:13)
reboot   system boot  5.4.0-124-generi Thu Aug 25 05:57 - 06:15  (00:17)
reboot   system boot  5.4.0-124-generi Thu Aug 25 05:52 - 05:56  (00:03)
vagrant  pts/0        10.0.2.2         Thu Aug 25 05:46 - 05:48  (00:01)
vagrant  pts/0        10.0.2.2         Thu Aug 25 05:31 - 05:40  (00:08)
reboot   system boot  5.4.0-124-generi Thu Aug 25 05:30 - 05:49  (00:19)
vagrant  pts/0        10.0.2.2         Thu Aug 25 05:06 - 05:22  (00:15)
reboot   system boot  5.4.0-124-generi Thu Aug 25 05:00 - 05:23  (00:23)

wtmp begins Thu Aug 25 05:00:46 2022
```
```
![last png](https://user-images.githubusercontent.com/108562214/186876531-b889c500-b1c6-4d3a-a8a1-fe8c633da023.png)
```

**9. id**<br>
This command is used to find out user and group names and numeric ID's (UID or group ID) of the current user or any other user in the server. This command is useful to find out the user name and real user id, and also find out the specific Users UID.
```
vagrant@ubuntu-focal:~$ id
uid=1000(vagrant) gid=1000(vagrant) groups=1000(vagrant)
```
```
![id png](https://user-images.githubusercontent.com/108562214/186877144-62dad0d0-eb75-4126-8d39-298890d5a28b.png)
```

**10. hostname**<br>
A hostname command is used to view a computer's hostname and domain name (DNS) (Domain Name Service), and to display or set a computer's hostname or domain name. It is a unique name that gets assigned to a computer in a network in order to uniquely identify that computer in that specific network.
The example below display displays hostname -I.
```
vagrant@ubuntu-focal:~$ hostname -I
10.0.2.15 192.168.56.4
```
```
![hostname- I](https://user-images.githubusercontent.com/108562214/186878964-f3235648-097b-4428-80bc-1e8fd3971da6.png)
```
