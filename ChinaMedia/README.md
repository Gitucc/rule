# ChinaMedia

Source config: [ChinaMedia.yaml](https://github.com/Gitucc/rule/blob/main/source/ChinaMedia/ChinaMedia.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| Bilibili | B站规则（classical yaml） | true | http | classical | yaml | rules |  | [Bilibili.yaml](https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/Providers/Ruleset/Bilibili.yaml) |  |  |
| BilibiliBobby | B站规则（classical txt） | true | http | classical | text | rules |  | [BiliBili.list](https://raw.githubusercontent.com/LM-Firefly/Rules/master/Domestic-Services/BiliBili.list) |  |  |
| iQIYI | 爱奇艺规则（classical txt） | true | http | classical | text | rules |  | [iQIYI.list](https://raw.githubusercontent.com/LM-Firefly/Rules/refs/heads/master/Domestic-Services/iQIYI.list) |  |  |
| ChinaMedia | 中国媒体规则（classical yaml） | true | http | classical | yaml | rules |  | [ChinaMedia.yaml](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/refs/heads/master/rule/Clash/ChinaMedia/ChinaMedia.yaml) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "ChinaMedia"
    type: select
    proxies: []
rules:
  - RULE-SET,ChinaMedia_Domain,ChinaMedia
  - RULE-SET,ChinaMedia,ChinaMedia,no-resolve
  - RULE-SET,ChinaMedia_IP,ChinaMedia,no-resolve
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  ChinaMedia_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/ChinaMedia/ChinaMedia_Domain.mrs }
  ChinaMedia: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/ChinaMedia/ChinaMedia.yaml }
  ChinaMedia_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/ChinaMedia/ChinaMedia_IP.mrs }
```

## Artifacts

### mrs(ipcidr)

#### ChinaMedia_IP.mrs

GitHub: [ChinaMedia_IP.mrs](https://github.com/Gitucc/rule/blob/release/ChinaMedia/ChinaMedia_IP.mrs)
Text: [ChinaMedia_IP.txt](https://github.com/Gitucc/rule/blob/release/ChinaMedia/ChinaMedia_IP.txt)
Sources: [BilibiliBobby.original.list](https://github.com/Gitucc/rule/blob/release/ChinaMedia/BilibiliBobby.original.list), [iQIYI.original.list](https://github.com/Gitucc/rule/blob/release/ChinaMedia/iQIYI.original.list), [ChinaMedia.original.yaml](https://github.com/Gitucc/rule/blob/release/ChinaMedia/ChinaMedia.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/ChinaMedia/ChinaMedia_IP.mrs
```

### mrs(domain)

#### ChinaMedia_Domain.mrs

GitHub: [ChinaMedia_Domain.mrs](https://github.com/Gitucc/rule/blob/release/ChinaMedia/ChinaMedia_Domain.mrs)
Text: [ChinaMedia_Domain.txt](https://github.com/Gitucc/rule/blob/release/ChinaMedia/ChinaMedia_Domain.txt)
Sources: [Bilibili.original.yaml](https://github.com/Gitucc/rule/blob/release/ChinaMedia/Bilibili.original.yaml), [BilibiliBobby.original.list](https://github.com/Gitucc/rule/blob/release/ChinaMedia/BilibiliBobby.original.list), [iQIYI.original.list](https://github.com/Gitucc/rule/blob/release/ChinaMedia/iQIYI.original.list), [ChinaMedia.original.yaml](https://github.com/Gitucc/rule/blob/release/ChinaMedia/ChinaMedia.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/ChinaMedia/ChinaMedia_Domain.mrs
```

### yaml(remaining)

#### ChinaMedia.yaml

GitHub: [ChinaMedia.yaml](https://github.com/Gitucc/rule/blob/release/ChinaMedia/ChinaMedia.yaml)
Sources: [BilibiliBobby.original.list](https://github.com/Gitucc/rule/blob/release/ChinaMedia/BilibiliBobby.original.list), [iQIYI.original.list](https://github.com/Gitucc/rule/blob/release/ChinaMedia/iQIYI.original.list), [ChinaMedia.original.yaml](https://github.com/Gitucc/rule/blob/release/ChinaMedia/ChinaMedia.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/ChinaMedia/ChinaMedia.yaml
```
