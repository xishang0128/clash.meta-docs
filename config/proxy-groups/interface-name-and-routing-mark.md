---
description: 可以为策略组指定出站接口以及出站流量标记
---

# 指定接口以及路由标记

## 配置示例

```
proxy-groups:
  - name: "en1直连"
    type: select
    interface-name: en1
    routing-mark: 19198
    proxies:
      - DIRECT
  - name: "en0直连"
    type: select
    interface-name: en0
    routing-mark: 11451
    proxies:
      - DIRECT
  - name: "直连接口选择"
    type: select
    interface-name: en1
    proxies:
      - "en0直连"
      - "en1直连"
```

