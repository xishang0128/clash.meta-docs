---
description: clash的dns模块配置
---

# DNS

## 示例

以下的拆分说明皆是 dns: 下的配置项

```
dns:
  enable: true
  prefer-h3: true
  listen: 0.0.0.0:1053
  ipv6: true
  default-nameserver:
    - 114.114.114.114
    - 8.8.8.8
    - tls://1.12.12.12:853
    - tls://223.5.5.5:853
  enhanced-mode: fake-ip
  fake-ip-range: 198.18.0.1/16
  fake-ip-filter:
    - '*.lan'
    - localhost.ptlogin2.qq.com
  nameserver-policy:
    'www.baidu.com': '114.114.114.114'
    '+.internal.crop.com': '10.0.0.1'
  nameserver:
    - https://doh.pub/dns-query
    - https://dns.alidns.com/dns-query
  fallback:
    - tcp://1.1.1.1
    - 'tcp://1.1.1.1#
  proxy-server-nameserver:
    - https://doh.pub/dns-query
  fallback-filter:
    geoip: true
    geoip-code: CN
    geosite:
      - gfw
    ipcidr:
      - 240.0.0.0/4
    domain:
      - '+.google.com'
      - '+.facebook.com'
      - '+.youtube.com'
```

### enable

可选值 `true/false`

是否启用,如为false，则使用系统dns解析

### prefer-h3

可选值 `true/false`

是否开启DOH的http/3

### listen

dns服务监听

### enhanced-mode

可选值 `fake-ip / redir-host`

clash的dns处理模式

### fake-ip-range

格式为 `ip/掩码`

fakeip下的IP段设置, tun网卡的默认ip也使用此值

### fake-ip-filter

fakeip过滤,以下地址不会下发fakeip映射用于连接

### use-hosts

可选值 `true/false`

是否查询系统hosts

### default-nameserver

默认dns

用于解析 `nameserver/fallback/proxy-server-nameserver` 的域名

必须为ip,可为加密dns

```
default-nameserver:
  - 114.114.114.114
  - 8.8.8.8
  - tls://223.5.5.5:853
  - https://223.5.5.5/dns-query
```

