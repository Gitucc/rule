# TelegramUS

Source config: [TelegramUS.yaml](https://github.com/Gitucc/rule/blob/main/source/TelegramUS/TelegramUS.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| TelegramUS | TelegramUS | true | http | classical | yaml | rules |  | [TelegramUS.yaml](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Clash/TelegramUS/TelegramUS.yaml) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "TelegramUS"
    type: select
    proxies: []
rules:
  - RULE-SET,TelegramUS_IP,TelegramUS,no-resolve
  - RULE-SET,TelegramUS_Domain,TelegramUS # placeholder: upstream currently has no domain rules; contains blackhole.invalid only
  - RULE-SET,TelegramUS,TelegramUS,no-resolve # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  TelegramUS_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/TelegramUS/TelegramUS_IP.mrs }
  TelegramUS_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/TelegramUS/TelegramUS_Domain.mrs } # placeholder: upstream currently has no domain rules; contains blackhole.invalid only
  TelegramUS: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/TelegramUS/TelegramUS.yaml } # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
```

## Artifacts

### mrs(ipcidr)

#### TelegramUS_IP.mrs

GitHub: [TelegramUS_IP.mrs](https://github.com/Gitucc/rule/blob/release/TelegramUS/TelegramUS_IP.mrs)
Text: [TelegramUS_IP.txt](https://github.com/Gitucc/rule/blob/release/TelegramUS/TelegramUS_IP.txt)
Source: [TelegramUS.original.yaml](https://github.com/Gitucc/rule/blob/release/TelegramUS/TelegramUS.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/TelegramUS/TelegramUS_IP.mrs
```

### mrs(domain)

#### TelegramUS_Domain.mrs

GitHub: [TelegramUS_Domain.mrs](https://github.com/Gitucc/rule/blob/release/TelegramUS/TelegramUS_Domain.mrs)
Text: [TelegramUS_Domain.txt](https://github.com/Gitucc/rule/blob/release/TelegramUS/TelegramUS_Domain.txt)
Placeholder: upstream currently has no domain rules; contains blackhole.invalid only
Source: [TelegramUS.original.yaml](https://github.com/Gitucc/rule/blob/release/TelegramUS/TelegramUS.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/TelegramUS/TelegramUS_Domain.mrs
```

### yaml(remaining)

#### TelegramUS.yaml

GitHub: [TelegramUS.yaml](https://github.com/Gitucc/rule/blob/release/TelegramUS/TelegramUS.yaml)
Placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
Source: [TelegramUS.original.yaml](https://github.com/Gitucc/rule/blob/release/TelegramUS/TelegramUS.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/TelegramUS/TelegramUS.yaml
```
