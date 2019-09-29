一键脚本安装shadowsocks/shadowsocksR/V2Ray + 开启bbr
---

一键脚本搭建shadowsocks/shadowsocksR/V2Ray + 设置开启自启动 + 升级内核&开启bbr加速。

## 支持系统
CentOS 6+

Debian 7+

Ubuntu 12+

## 使用教程



一键搭建ss/ssr：

下载:
```
git https://github.com/isleifeng/ss-fly
```
安装
```
ss-fly/ss-fly.sh -i password port
```
password 连接密码
port 连接端口

## 命令
```
启动：/etc/init.d/ss-fly start
停止：/etc/init.d/ss-fly stop
重启：/etc/init.d/ss-fly restart
状态：/etc/init.d/ss-fly status
查看ss链接：ss-fly/ss-fly.sh -sslink
修改配置文件：vim /etc/shadowsocks.json
卸载: ss-fly/ss-fly.sh -uninstall
```


## 开启bbr加速

```
ss-fly/ss-fly.sh -bbr
```

装完后需要重启系统，输入y即可立即重启，或者之后输入reboot命令重启。

判断BBR加速有没有开启成功。输入以下命令：

sysctl net.ipv4.tcp_available_congestion_control

如果返回值为：
```
net.ipv4.tcp_available_congestion_control = bbr cubic reno
```
后面有bbr，则说明已经开启成功了。
