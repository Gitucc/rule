# TelegramSG

Source config: [TelegramSG.yaml](https://github.com/Gitucc/rule/blob/main/source/TelegramSG/TelegramSG.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| TelegramSG | TelegramSG | true | http | classical | yaml | rules |  | [TelegramSG.yaml](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Clash/TelegramSG/TelegramSG.yaml) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "TelegramSG"
    type: select
    proxies: []
rules:
  - RULE-SET,TelegramSG_IP,TelegramSG,no-resolve
  - RULE-SET,TelegramSG_Domain,TelegramSG # placeholder: upstream currently has no domain rules; contains blackhole.invalid only
  - RULE-SET,TelegramSG,TelegramSG,no-resolve # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  TelegramSG_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/TelegramSG/TelegramSG_IP.mrs }
  TelegramSG_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/TelegramSG/TelegramSG_Domain.mrs } # placeholder: upstream currently has no domain rules; contains blackhole.invalid only
  TelegramSG: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/TelegramSG/TelegramSG.yaml } # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
```

## Artifacts

### mrs(ipcidr)

#### TelegramSG_IP.mrs

GitHub: [TelegramSG_IP.mrs](https://github.com/Gitucc/rule/blob/release/TelegramSG/TelegramSG_IP.mrs)
Text: [TelegramSG_IP.txt](https://github.com/Gitucc/rule/blob/release/TelegramSG/TelegramSG_IP.txt)
Source: [TelegramSG.original.yaml](https://github.com/Gitucc/rule/blob/release/TelegramSG/TelegramSG.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/TelegramSG/TelegramSG_IP.mrs
```

### mrs(domain)

#### TelegramSG_Domain.mrs

GitHub: [TelegramSG_Domain.mrs](https://github.com/Gitucc/rule/blob/release/TelegramSG/TelegramSG_Domain.mrs)
Text: [TelegramSG_Domain.txt](https://github.com/Gitucc/rule/blob/release/TelegramSG/TelegramSG_Domain.txt)
Placeholder: upstream currently has no domain rules; contains blackhole.invalid only
Source: [TelegramSG.original.yaml](https://github.com/Gitucc/rule/blob/release/TelegramSG/TelegramSG.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/TelegramSG/TelegramSG_Domain.mrs
```

### yaml(remaining)

#### TelegramSG.yaml

GitHub: [TelegramSG.yaml](https://github.com/Gitucc/rule/blob/release/TelegramSG/TelegramSG.yaml)
Placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
Source: [TelegramSG.original.yaml](https://github.com/Gitucc/rule/blob/release/TelegramSG/TelegramSG.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/TelegramSG/TelegramSG.yaml
```
