# Steam

Source config: [Steam.yaml](https://github.com/Gitucc/rule/blob/main/source/Steam/Steam.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| Steam | Steam | true | http | domain | yaml | rules |  | [Steam.yaml](https://raw.githubusercontent.com/dler-io/Rules/main/Clash/Provider/Steam.yaml) |  |  |
| Steam_ACL4SSR |  | true | http | domain | yaml | rules |  | [Steam.yaml](https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/Providers/Ruleset/Steam.yaml) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "Steam"
    type: select
    proxies: []
rules:
  - RULE-SET,Steam_Domain,Steam
  - RULE-SET,Steam,Steam,no-resolve # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
  - RULE-SET,Steam_IP,Steam,no-resolve # placeholder: upstream currently has no ipcidr rules; contains 203.0.113.1/32 only
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  Steam_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/Steam/Steam_Domain.mrs }
  Steam: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/Steam/Steam.yaml } # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
  Steam_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/Steam/Steam_IP.mrs } # placeholder: upstream currently has no ipcidr rules; contains 203.0.113.1/32 only
```

## Artifacts

### mrs(ipcidr)

#### Steam_IP.mrs

GitHub: [Steam_IP.mrs](https://github.com/Gitucc/rule/blob/release/Steam/Steam_IP.mrs)
Text: [Steam_IP.txt](https://github.com/Gitucc/rule/blob/release/Steam/Steam_IP.txt)
Placeholder: upstream currently has no ipcidr rules; contains 203.0.113.1/32 only
Sources: [Steam.original.yaml](https://github.com/Gitucc/rule/blob/release/Steam/Steam.original.yaml), [Steam_ACL4SSR.original.yaml](https://github.com/Gitucc/rule/blob/release/Steam/Steam_ACL4SSR.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/Steam/Steam_IP.mrs
```

### mrs(domain)

#### Steam_Domain.mrs

GitHub: [Steam_Domain.mrs](https://github.com/Gitucc/rule/blob/release/Steam/Steam_Domain.mrs)
Text: [Steam_Domain.txt](https://github.com/Gitucc/rule/blob/release/Steam/Steam_Domain.txt)
Sources: [Steam.original.yaml](https://github.com/Gitucc/rule/blob/release/Steam/Steam.original.yaml), [Steam_ACL4SSR.original.yaml](https://github.com/Gitucc/rule/blob/release/Steam/Steam_ACL4SSR.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/Steam/Steam_Domain.mrs
```

### yaml(remaining)

#### Steam.yaml

GitHub: [Steam.yaml](https://github.com/Gitucc/rule/blob/release/Steam/Steam.yaml)
Placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
Sources: [Steam.original.yaml](https://github.com/Gitucc/rule/blob/release/Steam/Steam.original.yaml), [Steam_ACL4SSR.original.yaml](https://github.com/Gitucc/rule/blob/release/Steam/Steam_ACL4SSR.original.yaml)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/Steam/Steam.yaml
```
