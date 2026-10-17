# AppleCN

Source config: [AppleCN.yaml](https://github.com/Gitucc/rule/blob/main/source/AppleCN/AppleCN.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| AppleCN | Apple CN | true | http | domain | yaml | rules |  | [apple.txt](https://raw.githubusercontent.com/Loyalsoldier/clash-rules/release/apple.txt) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "AppleCN"
    type: select
    proxies: []
rules:
  - RULE-SET,AppleCN_Domain,AppleCN
  - RULE-SET,AppleCN,AppleCN,no-resolve # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
  - RULE-SET,AppleCN_IP,AppleCN,no-resolve # placeholder: upstream currently has no ipcidr rules; contains 203.0.113.1/32 only
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  AppleCN_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/AppleCN/AppleCN_Domain.mrs }
  AppleCN: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/AppleCN/AppleCN.yaml } # placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
  AppleCN_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/AppleCN/AppleCN_IP.mrs } # placeholder: upstream currently has no ipcidr rules; contains 203.0.113.1/32 only
```

## Artifacts

### mrs(ipcidr)

#### AppleCN_IP.mrs

GitHub: [AppleCN_IP.mrs](https://github.com/Gitucc/rule/blob/release/AppleCN/AppleCN_IP.mrs)
Text: [AppleCN_IP.txt](https://github.com/Gitucc/rule/blob/release/AppleCN/AppleCN_IP.txt)
Placeholder: upstream currently has no ipcidr rules; contains 203.0.113.1/32 only
Source: [AppleCN.original.txt](https://github.com/Gitucc/rule/blob/release/AppleCN/AppleCN.original.txt)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/AppleCN/AppleCN_IP.mrs
```

### mrs(domain)

#### AppleCN_Domain.mrs

GitHub: [AppleCN_Domain.mrs](https://github.com/Gitucc/rule/blob/release/AppleCN/AppleCN_Domain.mrs)
Text: [AppleCN_Domain.txt](https://github.com/Gitucc/rule/blob/release/AppleCN/AppleCN_Domain.txt)
Source: [AppleCN.original.txt](https://github.com/Gitucc/rule/blob/release/AppleCN/AppleCN.original.txt)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/AppleCN/AppleCN_Domain.mrs
```

### yaml(remaining)

#### AppleCN.yaml

GitHub: [AppleCN.yaml](https://github.com/Gitucc/rule/blob/release/AppleCN/AppleCN.yaml)
Placeholder: upstream currently has no remaining rules; contains DOMAIN,blackhole.invalid only
Source: [AppleCN.original.txt](https://github.com/Gitucc/rule/blob/release/AppleCN/AppleCN.original.txt)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/AppleCN/AppleCN.yaml
```
