# Gost加密隧道挖矿中转方案搭建

## GOST加密隧道介绍：

GOST是一款用GO语言实现的安全隧道软件，gost安全隧道使用的是 http+tls 的协议，将流量加密成普通网页的流量进行访问，让流量特征监控失效。

Gost 隧道需要两端，即服务端与客户端才能组成一条加密隧道， 所以需要一台境外服务器做服务端，同时在你的本地也需要一台客户端（可以是矿机本身，也可以是任意一台能运行 Gost 的机器，包括Docker容器）服务端和客户端互相加密通讯，就能够组成一条加密隧道。

GOST TCP加密隧道设置：

gost-windows-amd64.exe -L=tcp://:12345/eth.f2pool.com:6688 -F=relay+tls://zhangsan:abcd1234@服务端IP:36543
以上转发地址，从服务器转发到鱼池的TCP端口，软件设置stratum+TCP。

GOST SSL加密隧道设置：

gost-windows-amd64.exe -L=tcp://:12345/ethssl-asia.f2pool.com:6698 -F=relay+tls://zhangsan:abcd1234@服务端IP:36543
以上转发地址，从服务器转发到鱼池的SSL端口，软件设置stratum+SSL。

**详细的Gost加密隧道挖矿中转方案搭建教程请点击
[Gost加密隧道中转方案](https://www.xsdnmg.tk/2022/04/06/03/).**

**温馨提示：**
Gost V3正式版本即将发布，待发布后会更新文档，同时增加如何使用Grafana来呈现Gost监控指标数据，以实现服务运行和wa kuang数据的可视化展示。
