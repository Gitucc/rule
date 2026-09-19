# TelegramNL

Source config: [TelegramNL.yaml](https://github.com/Gitucc/rule/blob/main/source/TelegramNL/TelegramNL.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| TelegramNL | TelegramNL | true | http | classical | yaml | rules |  | [TelegramNL.yaml](https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/Clash/TelegramNL/TelegramNL.yaml) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "TelegramNL"
    type: select
    proxies: []
rules:
  - RULE-SET,TelegramNL_IP,TelegramNL,no-resolve
  - RULE-SET,TelegramNL_Domain,TelegramNL # placeholder: upstream currently has no domain rules; contains blackhole.invalid only
  - RULE-SET,TelegramNL,TelegramNL,no-resolve # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  TelegramNL_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/TelegramNL/TelegramNL_IP.mrs }
  TelegramNL_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/TelegramNL/TelegramNL_Domain.mrs } # placeholder: upstream currently has no domain rules; contains blackhole.invalid only
  TelegramNL: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/TelegramNL/TelegramNL.yaml } # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
```

## Artifacts

### mrs(ipcidr)

#### TelegramNL_IP.mrs

GitHub: [TelegramNL_IP.mrs](https://github.com/Gitucc/rule/blob/release/TelegramNL/TelegramNL_IP.mrs)
Text: [TelegramNL_IP.txt](https://github.com/Gitucc/rule/blob/release/TelegramNL/TelegramNL_IP.txt)
Source: [TelegramNL.original.yaml](https://github.com/Gitucc/rule/blob/release/TelegramNL/TelegramNL.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/TelegramNL/TelegramNL_IP.mrs
```

### mrs(domain)

#### TelegramNL_Domain.mrs

GitHub: [TelegramNL_Domain.mrs](https://github.com/Gitucc/rule/blob/release/TelegramNL/TelegramNL_Domain.mrs)
Text: [TelegramNL_Domain.txt](https://github.com/Gitucc/rule/blob/release/TelegramNL/TelegramNL_Domain.txt)
Placeholder: upstream currently has no domain rules; contains blackhole.invalid only
Source: [TelegramNL.original.yaml](https://github.com/Gitucc/rule/blob/release/TelegramNL/TelegramNL.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/TelegramNL/TelegramNL_Domain.mrs
```

### yaml(remaining)

#### TelegramNL.yaml

GitHub: [TelegramNL.yaml](https://github.com/Gitucc/rule/blob/release/TelegramNL/TelegramNL.yaml)
Placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
Source: [TelegramNL.original.yaml](https://github.com/Gitucc/rule/blob/release/TelegramNL/TelegramNL.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/TelegramNL/TelegramNL.yaml
```
