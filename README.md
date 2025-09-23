# Custom Mihomo/Clash Ruleset

## 📌 已包含规则集
- `ads.yaml` 广告拦截
- `cn.yaml` 国内直连
- `ai.yaml` AI (ChatGPT / Claude / Perplexity)
- `github.yaml` GitHub
- `nf.yaml` Netflix
- `youtube.yaml` YouTube
- `x.yaml` X (Twitter)

## 🚀 使用方法
在 Mihomo 配置中添加：

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
```

然后在 `rules:` 里调用：
```yaml
rules:
  - RULE-SET,ai,AI
  - RULE-SET,github,GitHub
  - RULE-SET,nf,Netflix
  - RULE-SET,youtube,YouTube
  - RULE-SET,x,Twitter
```
