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

可选值 \`true/false\`&#x20;

是否启用,如为false，则使用系统dns解析

### prefer-h3

true

是否开启DOH的http/3
