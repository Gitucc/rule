# ChinaList

Source config: [ChinaList.yaml](https://github.com/Gitucc/rule/blob/main/source/ChinaList/ChinaList.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| ChinaList | China domain rules | true | http | domain | yaml | rules |  | [direct.txt](https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/direct.txt) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "ChinaList"
    type: select
    proxies: []
rules:
  - RULE-SET,ChinaList_Domain,ChinaList
  - RULE-SET,ChinaList,ChinaList,no-resolve # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
  - RULE-SET,ChinaList_IP,ChinaList,no-resolve # placeholder: upstream currently has no ipcidr rules; contains 203.0.113.1/32 only
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  ChinaList_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/ChinaList/ChinaList_Domain.mrs }
  ChinaList: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/ChinaList/ChinaList.yaml } # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
  ChinaList_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/ChinaList/ChinaList_IP.mrs } # placeholder: upstream currently has no ipcidr rules; contains 203.0.113.1/32 only
```

## Artifacts

### mrs(ipcidr)

#### ChinaList_IP.mrs

GitHub: [ChinaList_IP.mrs](https://github.com/Gitucc/rule/blob/release/ChinaList/ChinaList_IP.mrs)
Text: [ChinaList_IP.txt](https://github.com/Gitucc/rule/blob/release/ChinaList/ChinaList_IP.txt)
Placeholder: upstream currently has no ipcidr rules; contains 203.0.113.1/32 only
Source: [ChinaList.original.txt](https://github.com/Gitucc/rule/blob/release/ChinaList/ChinaList.original.txt)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/ChinaList/ChinaList_IP.mrs
```

### mrs(domain)

#### ChinaList_Domain.mrs

GitHub: [ChinaList_Domain.mrs](https://github.com/Gitucc/rule/blob/release/ChinaList/ChinaList_Domain.mrs)
Text: [ChinaList_Domain.txt](https://github.com/Gitucc/rule/blob/release/ChinaList/ChinaList_Domain.txt)
Source: [ChinaList.original.txt](https://github.com/Gitucc/rule/blob/release/ChinaList/ChinaList.original.txt)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/ChinaList/ChinaList_Domain.mrs
```

### yaml(remaining)

#### ChinaList.yaml

GitHub: [ChinaList.yaml](https://github.com/Gitucc/rule/blob/release/ChinaList/ChinaList.yaml)
Placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
Source: [ChinaList.original.txt](https://github.com/Gitucc/rule/blob/release/ChinaList/ChinaList.original.txt)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/ChinaList/ChinaList.yaml
```
