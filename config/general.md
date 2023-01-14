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
# socks5 代理端口

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

允许其他设备经过clash的代理端口访问互联网

```
allow-lan: true
# 可选值 true/false

bind-address: "*"
# 绑定IP,仅允许某个IP访问代理端口
# "*" 绑定所有IP地址,默认值,不填写此项则绑定全部
# 192.168.31.31:  绑定单个IPV4地址
# "[aaaa::a8aa:ff:fe09:57d8]":  绑定单个IPV6地址

authentication:
  - "user1:pass1"
  - "user2:pass2"
# http(s) 和 socks5 代理的用户验证
```

## 运行模式

```
mode: rule
# rule(规则) / global(全局) / direct(直连)
# 此项拥有默认值,默认为规则模式
```

## 日志级别

clash内核输出日志的等级,仅在控制台和控制页面输出

```
log－level: info
# 各个等级
# silent  静默,不输出
# error 仅输出发生错误至无法使用的日志
# warning 输出发生错误但不影响运行的日志,以及error级别内容
# info 输出一般运行的内容,以及error和warning级别的日志
# debug 尽可能的输出运行中所有的信息
```

## IPV6

```
ipv6: true
# 可选值 true/false
# 是否允许内核接受ipv6流量
```

## 外部控制(API)

外部控制器可以使用RESTful API来控制你的clash

```
external-controller: 127.0.0.1:9090 
# API 监听,你可以将127.0.0.1修改为0.0.0.0来监听所有IP

secret: ""
# API 的密码
```

## 外部用户界面

可以将静态网页资源(比如clash-dashboard)运行在clash API,路径为 API地址/ui

```
external-ui: ./dashboard
# 可以为绝对路径,或者clash工作目录的相对路径
```

## 出站接口

```
interface-name: en0
# clash的流量出站接口
```

## 路由标记

为Linux下的出站连接提供默认流量标记

```
routing-mark: 6666
```

## TLS

## 实验性
