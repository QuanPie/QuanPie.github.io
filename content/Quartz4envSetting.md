---
title: Quartz4 環境設置
aliases:
  - Quartz4 環境設置
  - Quartz4envSetting
draft: false
date: 2023-09-10
tags:
  - GitHub
  - Obsidian
  - Setup
  - Evnironment
source: 
created: 2023-08-23 12:06
summary: 
modified: 2023-10-19 21:52
---
## 1. 安裝部署

**step.1**

- 確保安裝了至少 node v18.14 ([Node.js](https://nodejs.org/))
- 安裝並跟隨步驟做好初步設定

``` shell
git clone https://github.com/jackyzha0/quartz.git
cd quartz
npm i
npx quartz create
```

**step.2**

-  本地測試 (http://localhost:8080/)

```shell
npx quartz build --serve
```

**step.3**

- 用 cloudflare 連結 github repo 部署（[Hosting](https://quartz.jzhao.xyz/hosting#cloudflare-pages)）

**step.4**

- Account Home, select **Workers & Pages** > **Create application** > **Pages** > **Connect to Git**.

**step.5**

- 選擇要部署的那個新增的 GitHub repository，然後 created

**step.6**

- **Set up builds and deployments** 階段填入表格內容

|Configuration option|Value|
|---|---|
|Production branch|`v4`|
|Framework preset|`None`|
|Build command|`npx quartz build`|
|Build output directory|`public`|

**step.7**

- Save and deploy，等待部署完成



## 2. Metadata
- a.k.a. **Frontmatter**

``` metadata
---
title: Example 
Titledraft: False
tags: 
	- Example-Tag
---
The Rest Of Your Content Lives Here. You Can Use **Markdown** Here :)
```

- `Title`: 頁面標題。如果沒有 Quartz 會用當名代替
- `Aliases`: 筆記別稱，會用 list 顯示
- `Draft`: 是否公開發布筆記。設定 [Pages Private](https://quartz.jzhao.xyz/features/private-pages) 
- `Date`: 筆記發布日期。格式 `YYYY-MM-DD` 
## 3. ⚠️ 遇到的問題及解決辦法

- `npx ERR:???忘了複製`
- `Please upgrade your git client`
- 解決方法：重裝 git 後重新 clone repo

``` shell
brew install git
```

- 在 `~/.bashrc` 或 `~/.bash_profile` 文件中添加以下行，確保使用 Homebrew 安裝的 Git 取代 macOS 自帶的 Git：

``` shell
export PATH="/usr/local/bin:$PATH"
```

# Ref.
- [Welcome to Quartz 4](https://quartz.jzhao.xyz/)
- [Migrating from Quartz 3](https://quartz.jzhao.xyz/migrating-from-Quartz-3)