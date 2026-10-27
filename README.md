# 🎯 目標理財規劃師

以 PV、FV、PMT 為核心的目標導向理財試算網站：設定目標後，自動反推每月需存金額、所需報酬率與年數，並提供情境分析與建議。純靜態、零依賴。

## 專案結構（index.html 位於最上層）
```
├── index.html
├── _headers
├── wrangler.toml
├── LICENSE
└── README.md
```

## 部署到 Cloudflare Pages
**直接上傳：** Workers & Pages → Create → Pages → Upload assets → 拖曳整個資料夾 → Deploy

**GitHub 連動：** 把資料夾內容推上 GitHub，Cloudflare 選 Connect to Git，設定：
- Framework preset：None
- Build command：留空
- Build output directory：留空（或填 `/`）

## 公式（每月複利、期末投入）
- FV = PV·g + PMT·(g−1)/r
- PMT = (目標 − PV·g)·r / (g−1)
- PV = (目標 − PMT·(g−1)/r) / g

r = 年報酬率 ÷ 12，g = (1+r)ⁿ，n = 年數 × 12

## 免責聲明
僅供試算與教育用途，報酬率為假設值，不構成投資建議。
