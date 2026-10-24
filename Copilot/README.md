# Copilot

Source config: [Copilot.yaml](https://github.com/Gitucc/rule/blob/main/source/Copilot/Copilot.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| Copilot | Microsoft Copilot rules from ios_rule_script | true | http | classical | yaml | rules |  | [Copilot.yaml](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Clash/Copilot/Copilot.yaml) |  |  |
| CopilotInline |  | true | inline | domain | text | rules |  |  |  | [CopilotInline.original.txt](https://github.com/Gitucc/rule/blob/release/Copilot/CopilotInline.original.txt) |

## Mihomo Config

```yaml
proxy-groups:
  - name: "Copilot"
    type: select
    proxies: []
rules:
  - RULE-SET,Copilot_Domain,Copilot
  - RULE-SET,Copilot,Copilot,no-resolve
  - RULE-SET,Copilot_IP,Copilot,no-resolve
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  Copilot_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/Copilot/Copilot_Domain.mrs }
  Copilot: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/Copilot/Copilot.yaml }
  Copilot_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/Copilot/Copilot_IP.mrs }
```

## Artifacts

### mrs(ipcidr)

#### Copilot_IP.mrs

GitHub: [Copilot_IP.mrs](https://github.com/Gitucc/rule/blob/release/Copilot/Copilot_IP.mrs)
Text: [Copilot_IP.txt](https://github.com/Gitucc/rule/blob/release/Copilot/Copilot_IP.txt)
Source: [Copilot.original.yaml](https://github.com/Gitucc/rule/blob/release/Copilot/Copilot.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/Copilot/Copilot_IP.mrs
```

### mrs(domain)

#### Copilot_Domain.mrs

GitHub: [Copilot_Domain.mrs](https://github.com/Gitucc/rule/blob/release/Copilot/Copilot_Domain.mrs)
Text: [Copilot_Domain.txt](https://github.com/Gitucc/rule/blob/release/Copilot/Copilot_Domain.txt)
Sources: [Copilot.original.yaml](https://github.com/Gitucc/rule/blob/release/Copilot/Copilot.original.yaml), [CopilotInline.original.txt](https://github.com/Gitucc/rule/blob/release/Copilot/CopilotInline.original.txt)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/Copilot/Copilot_Domain.mrs
```

### yaml(remaining)

#### Copilot.yaml

GitHub: [Copilot.yaml](https://github.com/Gitucc/rule/blob/release/Copilot/Copilot.yaml)
Source: [Copilot.original.yaml](https://github.com/Gitucc/rule/blob/release/Copilot/Copilot.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/Copilot/Copilot.yaml
```
