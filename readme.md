参考了`https://www.lijingquan.net/index.php/2016/09/26/oray-phstick-root-password/`

# 通过SSH直接访问花生棒

某些时候需要通过SSH直接访问花生壳，下面给出折腾的步骤。

## 1. 扫描花生棒的IP地址

能直接用路由器的查看功能当然最好，不然就只能进行扫描了。
Windows下扫描工具很多，随便找一个教程。*nix下用nmap。

安装nmap:
+ mac
`brew install nmap`

+ ubuntu/debian
`sudo apt-get install nmap`

+ centos/red hat
`sudo yum install nmap`

假设花生壳所在的路由器IP地址是192.168.1.1，

```bash
nmap 192.168.1.0/24
```
只需要一小下就扫完了，根据IP地址一个一个推断，也可以直接测试`ssh` **44022端口**。

++ 2. SSH连接

假设IP是192.168.1.111

```bash
ssh root@192.168.1.111 -p 44022
```
默认密码是**xxoo**

++ 3. 能干啥

+ 比如，可以`ifconfig`查看MAC地址。如果隔了一个路由器，电脑直接扫描是看不到的，`arp`命令也不行。

+ 探索下人家的系统，不过我觉得没啥意义，黑客除外

+ 我也不知道了，那是人家的工厂模式，不知道改了会不会导致特定情况下失灵
