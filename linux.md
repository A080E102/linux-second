# lfconfig

```
docker0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
        inet 172.17.0.1  netmask 255.255.0.0  broadcast 172.17.255.255
        ether 02:42:48:9f:d9:02  txqueuelen 0  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.0.2.15  netmask 255.255.255.0  broadcast 10.0.2.255
        inet6 fe80::a00:27ff:fe04:c6c  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:04:0c:6c  txqueuelen 1000  (Ethernet)
        RX packets 12325  bytes 17620090 (16.8 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4524  bytes 274458 (268.0 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 20  bytes 1116 (1.0 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 20  bytes 1116 (1.0 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

# Ping
```
 172.17.0.1
```

# linux實戰作業

```
root@kali:~# pwd
/root
root@kali:~# cd ..
root@kali:/# pwd
/
```
```
root@kali:/# ls
0     dev   initrd.img      lib32   lost+found  opt   run   sys  var
bin   etc   initrd.img.old  lib64   media       proc  sbin  tmp  vmlinuz
boot  home  lib             libx32  mnt         root  srv   usr  vmlinuz.old
```
