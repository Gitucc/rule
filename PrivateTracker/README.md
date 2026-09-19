# PrivateTracker

Source config: [PrivateTracker.yaml](https://github.com/Gitucc/rule/blob/main/source/PrivateTracker/PrivateTracker.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| PrivateTracker | 私有Tracker规则（classical yaml） | true | http | classical | yaml | rules |  | [PrivateTracker.yaml](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Clash/PrivateTracker/PrivateTracker.yaml) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "PrivateTracker"
    type: select
    proxies: []
rules:
  - RULE-SET,PrivateTracker_Domain,PrivateTracker
  - RULE-SET,PrivateTracker,PrivateTracker,no-resolve
  - RULE-SET,PrivateTracker_IP,PrivateTracker,no-resolve
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  PrivateTracker_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/PrivateTracker/PrivateTracker_Domain.mrs }
  PrivateTracker: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/PrivateTracker/PrivateTracker.yaml }
  PrivateTracker_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/PrivateTracker/PrivateTracker_IP.mrs }
```

## Artifacts

### mrs(ipcidr)

#### PrivateTracker_IP.mrs

GitHub: [PrivateTracker_IP.mrs](https://github.com/Gitucc/rule/blob/release/PrivateTracker/PrivateTracker_IP.mrs)
Text: [PrivateTracker_IP.txt](https://github.com/Gitucc/rule/blob/release/PrivateTracker/PrivateTracker_IP.txt)
Source: [PrivateTracker.original.yaml](https://github.com/Gitucc/rule/blob/release/PrivateTracker/PrivateTracker.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/PrivateTracker/PrivateTracker_IP.mrs
```

### mrs(domain)

#### PrivateTracker_Domain.mrs

GitHub: [PrivateTracker_Domain.mrs](https://github.com/Gitucc/rule/blob/release/PrivateTracker/PrivateTracker_Domain.mrs)
Text: [PrivateTracker_Domain.txt](https://github.com/Gitucc/rule/blob/release/PrivateTracker/PrivateTracker_Domain.txt)
Source: [PrivateTracker.original.yaml](https://github.com/Gitucc/rule/blob/release/PrivateTracker/PrivateTracker.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/PrivateTracker/PrivateTracker_Domain.mrs
```

### yaml(remaining)

#### PrivateTracker.yaml

GitHub: [PrivateTracker.yaml](https://github.com/Gitucc/rule/blob/release/PrivateTracker/PrivateTracker.yaml)
Source: [PrivateTracker.original.yaml](https://github.com/Gitucc/rule/blob/release/PrivateTracker/PrivateTracker.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/PrivateTracker/PrivateTracker.yaml
```
