# Custom Mihomo/Clash Ruleset

## 📌 已包含规则集

| 文件名       | 描述                                      |
|------------|-----------------------------------------|
| ai.yaml    | AI 服务（ChatGPT、Claude、Perplexity、Cohere、Gemini） |
| github.yaml| GitHub 及相关域名                           |
| nf.yaml    | Netflix                                     |
| youtube.yaml| YouTube                                   |
| x.yaml     | Twitter / X                                |
| disney.yaml| Disney+                                    |

---

## 🚀 使用方法

在 Mihomo 配置中添加 `rule-providers`：

```yaml
rule-providers:
  ai:
    type: http
    behavior: domain
    path: ./ruleset/ai.yaml
    url: https://raw.githubusercontent.com/johnwalke/ruleset/main/ai.yaml

  github:
    type: http
    behavior: domain
    path: ./ruleset/github.yaml
    url: https://raw.githubusercontent.com/johnwalke/ruleset/main/github.yaml

  nf:
    type: http
    behavior: domain
    path: ./ruleset/nf.yaml
    url: https://raw.githubusercontent.com/johnwalke/ruleset/main/nf.yaml

  youtube:
    type: http
    behavior: domain
    path: ./ruleset/youtube.yaml
    url: https://raw.githubusercontent.com/johnwalke/ruleset/main/youtube.yaml

  x:
    type: http
    behavior: domain
    path: ./ruleset/x.yaml
    url: https://raw.githubusercontent.com/johnwalke/ruleset/main/x.yaml

  disney:
    type: http
    behavior: domain
    path: ./ruleset/disney.yaml
    url: https://raw.githubusercontent.com/johnwalke/ruleset/main/disney.yaml
```

然后在 `rules:` 中调用：

```yaml
rules:
  - RULE-SET,ai,AI
  - RULE-SET,github,GitHub
  - RULE-SET,nf,Netflix
  - RULE-SET,youtube,YouTube
  - RULE-SET,x,Twitter
  - RULE-SET,disney,Disney+
  - RULE-SET,applications,全球直连
  - DOMAIN,clash.razord.top,全球直连
  - DOMAIN,yacd.haishan.me,全球直连
  - RULE-SET,private,全球直连
  - RULE-SET,icloud,全球直连
  - RULE-SET,apple,全球直连
  - RULE-SET,direct,全球直连
  - RULE-SET,lancidr,全球直连
  - RULE-SET,cncidr,全球直连
  - RULE-SET,google,节点选择
  - RULE-SET,gfw,节点选择
  - RULE-SET,greatfire,节点选择
  - RULE-SET,proxy,节点选择
  - RULE-SET,telegramcidr,节点选择
  - GEOIP,LAN,全球直连
  - GEOIP,CN,全球直连
  - MATCH,节点选择
```

---

## 📌 使用说明
1. 将整个 `ruleset` 文件夹上传到 GitHub 仓库。  
2. 修改 Mihomo 配置中的 `url` 为你的 GitHub raw 链接。  
3. 每个规则集可以独立分流，也可以结合 proxy-groups 使用。  
4. 更新规则集时，Mihomo 会根据 `interval` 自动拉取最新版本。
