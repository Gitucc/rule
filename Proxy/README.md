# Proxy

Source config: [Proxy.yaml](https://github.com/Gitucc/rule/blob/main/source/Proxy/Proxy.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| BlackList | BlackList 规则 | true | http | classical | text | rules |  | [BlackList.list](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/source/rule/BlackList/BlackList.list) |  |  |
| Proxy | Proxy 规则提供者 | true | http | classical | yaml | rules |  | [Proxy.yaml](https://raw.githubusercontent.com/dler-io/Rules/main/Clash/Provider/Proxy.yaml) |  |  |
| ProxyDomain | Proxy 域名规则 | true | http | domain | text | rules |  | [Proxy.list](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/source/rule/Proxy/Proxy.list) |  |  |
| GFWList | GFW 列表 | true | http | domain | yaml | rules |  | [gfw.txt](https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/gfw.txt) |  |  |
| GreatFireList | 大陆防火墙列表 | true | http | domain | yaml | rules |  | [greatfire.txt](https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/greatfire.txt) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "Proxy"
    type: select
    proxies: []
rules:
  - RULE-SET,Proxy_Domain,Proxy
  - RULE-SET,Proxy,Proxy,no-resolve
  - RULE-SET,Proxy_IP,Proxy,no-resolve
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  Proxy_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/Proxy/Proxy_Domain.mrs }
  Proxy: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/Proxy/Proxy.yaml }
  Proxy_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/Proxy/Proxy_IP.mrs }
```

## Artifacts

### mrs(ipcidr)

#### Proxy_IP.mrs

GitHub: [Proxy_IP.mrs](https://github.com/Gitucc/rule/blob/release/Proxy/Proxy_IP.mrs)
Text: [Proxy_IP.txt](https://github.com/Gitucc/rule/blob/release/Proxy/Proxy_IP.txt)
Source: [Proxy.original.yaml](https://github.com/Gitucc/rule/blob/release/Proxy/Proxy.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/Proxy/Proxy_IP.mrs
```

### mrs(domain)

#### Proxy_Domain.mrs

GitHub: [Proxy_Domain.mrs](https://github.com/Gitucc/rule/blob/release/Proxy/Proxy_Domain.mrs)
Text: [Proxy_Domain.txt](https://github.com/Gitucc/rule/blob/release/Proxy/Proxy_Domain.txt)
Sources: [BlackList.original.list](https://github.com/Gitucc/rule/blob/release/Proxy/BlackList.original.list), [Proxy.original.yaml](https://github.com/Gitucc/rule/blob/release/Proxy/Proxy.original.yaml), [ProxyDomain.original.list](https://github.com/Gitucc/rule/blob/release/Proxy/ProxyDomain.original.list), [GFWList.original.txt](https://github.com/Gitucc/rule/blob/release/Proxy/GFWList.original.txt), [GreatFireList.original.txt](https://github.com/Gitucc/rule/blob/release/Proxy/GreatFireList.original.txt)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/Proxy/Proxy_Domain.mrs
```

### yaml(remaining)

#### Proxy.yaml

GitHub: [Proxy.yaml](https://github.com/Gitucc/rule/blob/release/Proxy/Proxy.yaml)
Sources: [BlackList.original.list](https://github.com/Gitucc/rule/blob/release/Proxy/BlackList.original.list), [Proxy.original.yaml](https://github.com/Gitucc/rule/blob/release/Proxy/Proxy.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/Proxy/Proxy.yaml
```
