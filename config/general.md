---
description: 全局配置定义了 代理端口、允许局域网、运行模式、日志级别、外部控制器、外部用户界面、身份验证和实验性功能等
---

# 全局配置

## 代理端口

端口是计算机或路由交换机内部的一部分,计算机按照INTERNET传输层 TCP/IP 协议进行通信,不同的协议对应不同的端口

```
port: 7890
# http(s) 代理端口

socks-port: 7891
# soack5 代理端口

mixed-port: 7892
# 混合代理端口 http(s)+socks5
```

{% hint style="info" %}
redir和tproxy端口仅限Linux以及MacOS适用 (Android设备属于Linux设备)
{% endhint %}

```
redir-port: 7893
# redirect 透明代理端口,仅能代理TCP流量

tproxy－port: 7894
# tproxy 透明代理端口,可以代理TCP以及UDP流量
```

## 允许局域网

## 运行模式

## 日志级别

## IPV6

## 外部控制器

## 外部用户界面

## 出站接口

## 路由标记

## TLS

## 实验性
