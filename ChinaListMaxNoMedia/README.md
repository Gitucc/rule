# ChinaListMaxNoMedia

Source config: [ChinaListMaxNoMedia.yaml](https://github.com/Gitucc/rule/blob/main/source/ChinaListMaxNoMedia/ChinaListMaxNoMedia.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| ChinaList |  | true | http | domain | yaml | rules |  | [direct.txt](https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/direct.txt) |  |  |
| ChinaMaxNoMedia |  | true | http | classical | yaml | rules |  | [ChinaMaxNoMedia_Classical.yaml](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/refs/heads/master/rule/Clash/ChinaMaxNoMedia/ChinaMaxNoMedia_Classical.yaml) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "ChinaListMaxNoMedia"
    type: select
    proxies: []
rules:
  - RULE-SET,ChinaListMaxNoMedia_Domain,ChinaListMaxNoMedia
  - RULE-SET,ChinaListMaxNoMedia,ChinaListMaxNoMedia,no-resolve
  - RULE-SET,ChinaListMaxNoMedia_IP,ChinaListMaxNoMedia,no-resolve
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  ChinaListMaxNoMedia_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia_Domain.mrs }
  ChinaListMaxNoMedia: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia.yaml }
  ChinaListMaxNoMedia_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia_IP.mrs }
```

## Artifacts

### mrs(ipcidr)

#### ChinaListMaxNoMedia_IP.mrs

GitHub: [ChinaListMaxNoMedia_IP.mrs](https://github.com/Gitucc/rule/blob/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia_IP.mrs)
Text: [ChinaListMaxNoMedia_IP.txt](https://github.com/Gitucc/rule/blob/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia_IP.txt)
Source: [ChinaMaxNoMedia.original.yaml](https://github.com/Gitucc/rule/blob/release/ChinaListMaxNoMedia/ChinaMaxNoMedia.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia_IP.mrs
```

### mrs(domain)

#### ChinaListMaxNoMedia_Domain.mrs

GitHub: [ChinaListMaxNoMedia_Domain.mrs](https://github.com/Gitucc/rule/blob/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia_Domain.mrs)
Text: [ChinaListMaxNoMedia_Domain.txt](https://github.com/Gitucc/rule/blob/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia_Domain.txt)
Sources: [ChinaList.original.txt](https://github.com/Gitucc/rule/blob/release/ChinaListMaxNoMedia/ChinaList.original.txt), [ChinaMaxNoMedia.original.yaml](https://github.com/Gitucc/rule/blob/release/ChinaListMaxNoMedia/ChinaMaxNoMedia.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia_Domain.mrs
```

### yaml(remaining)

#### ChinaListMaxNoMedia.yaml

GitHub: [ChinaListMaxNoMedia.yaml](https://github.com/Gitucc/rule/blob/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia.yaml)
Source: [ChinaMaxNoMedia.original.yaml](https://github.com/Gitucc/rule/blob/release/ChinaListMaxNoMedia/ChinaMaxNoMedia.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/ChinaListMaxNoMedia/ChinaListMaxNoMedia.yaml
```
