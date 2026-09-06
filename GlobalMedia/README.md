# GlobalMedia

Source config: [GlobalMedia.yaml](https://github.com/Gitucc/rule/blob/main/source/GlobalMedia/GlobalMedia.yaml)

## Source Files

| name |description |enabled |type |behavior |format |mihomo |headers |url |path |payload |
| --- |--- |--- |--- |--- |--- |--- |--- |--- |--- |--- |
| YouTube | YouTube 规则（classical yaml） | true | http | classical | yaml | rules |  | [YouTube.yaml](https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/Providers/Ruleset/YouTube.yaml) |  |  |
| YouTubeMusic | YouTube Music 规则（classical yaml） | true | http | classical | yaml | rules |  | [YouTubeMusic.yaml](https://raw.githubusercontent.com/ACL4SSR/ACL4SSR/master/Clash/Providers/Ruleset/YouTubeMusic.yaml) |  |  |
| GlobalMedia | 国际媒体规则（classical txt） | true | http | classical | text | rules |  | [GlobalMedia.list](https://raw.githubusercontent.com/LM-Firefly/Rules/refs/heads/master/GlobalMedia.list) |  |  |

## Mihomo Config

```yaml
proxy-groups:
  - name: "GlobalMedia"
    type: select
    proxies: []
rules:
  - RULE-SET,GlobalMedia_Domain,GlobalMedia
  - RULE-SET,GlobalMedia,GlobalMedia,no-resolve
  - RULE-SET,GlobalMedia_IP,GlobalMedia,no-resolve
rule-anchor:
  github-token-header: &github-token-header { Authorization: ["Bearer <YOUR_GITHUB_TOKEN>"] }
  ip: &ip { type: http, behavior: ipcidr, format: mrs, interval: 86400, header: *github-token-header }
  domain: &domain { type: http, behavior: domain, format: mrs, interval: 86400, header: *github-token-header }
  yaml: &yaml { type: http, behavior: classical, format: yaml, interval: 86400, header: *github-token-header }
rule-providers:
  GlobalMedia_Domain: { <<: *domain, url: https://raw.githubusercontent.com/Gitucc/rule/release/GlobalMedia/GlobalMedia_Domain.mrs }
  GlobalMedia: { <<: *yaml, url: https://raw.githubusercontent.com/Gitucc/rule/release/GlobalMedia/GlobalMedia.yaml }
  GlobalMedia_IP: { <<: *ip, url: https://raw.githubusercontent.com/Gitucc/rule/release/GlobalMedia/GlobalMedia_IP.mrs }
```

## Artifacts

### mrs(ipcidr)

#### GlobalMedia_IP.mrs

GitHub: [GlobalMedia_IP.mrs](https://github.com/Gitucc/rule/blob/release/GlobalMedia/GlobalMedia_IP.mrs)
Text: [GlobalMedia_IP.txt](https://github.com/Gitucc/rule/blob/release/GlobalMedia/GlobalMedia_IP.txt)
Source: [GlobalMedia.original.list](https://github.com/Gitucc/rule/blob/release/GlobalMedia/GlobalMedia.original.list)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/GlobalMedia/GlobalMedia_IP.mrs
```

### mrs(domain)

#### GlobalMedia_Domain.mrs

GitHub: [GlobalMedia_Domain.mrs](https://github.com/Gitucc/rule/blob/release/GlobalMedia/GlobalMedia_Domain.mrs)
Text: [GlobalMedia_Domain.txt](https://github.com/Gitucc/rule/blob/release/GlobalMedia/GlobalMedia_Domain.txt)
Sources: [YouTube.original.yaml](https://github.com/Gitucc/rule/blob/release/GlobalMedia/YouTube.original.yaml), [YouTubeMusic.original.yaml](https://github.com/Gitucc/rule/blob/release/GlobalMedia/YouTubeMusic.original.yaml), [GlobalMedia.original.list](https://github.com/Gitucc/rule/blob/release/GlobalMedia/GlobalMedia.original.list)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/GlobalMedia/GlobalMedia_Domain.mrs
```

### yaml(remaining)

#### GlobalMedia.yaml

GitHub: [GlobalMedia.yaml](https://github.com/Gitucc/rule/blob/release/GlobalMedia/GlobalMedia.yaml)
Sources: [YouTube.original.yaml](https://github.com/Gitucc/rule/blob/release/GlobalMedia/YouTube.original.yaml), [GlobalMedia.original.list](https://github.com/Gitucc/rule/blob/release/GlobalMedia/GlobalMedia.original.list)

```text
https://raw.githubusercontent.com/Gitucc/rule/release/GlobalMedia/GlobalMedia.yaml
```
