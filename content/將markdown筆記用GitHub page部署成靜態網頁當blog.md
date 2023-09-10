---
title: 將markdown筆記用GitHub page部署成靜態網頁當blog
aliases: 將markdown筆記用GitHub page部署成靜態網頁當blog
draft: false
date: 
tags:
  - tags/obs
  - tags/obs/Setup
  - tags/Github
source: 
created: 2023-08-14 11:52
modified: 2023-08-23 11:57
summary: 
---
type:: #types/🧩_atom 
relative::

---
# 將markdown筆記用GitHub Page部署成靜態網頁當blog
## 1. Why? 為何要將markdown筆記部署成靜態網頁？
### 1.1. 將筆記部署到 GitHub Page 在 PC 不在身邊時，可以使用行動裝置預覽markdown
#### 1.1.1. **為何不直接用github 預覽就好？**
- 因為obsidian有些語法無法在 GitHub 上渲染
#### 1.1.2. **為何不使用 Obsidian Mobile APP？**
- 要編輯時確實直接使用 Obsidian APP 比較方便，但為了避免檔案衝突造成要重新 clone repo 的窘境，多一個方案總是比較安心。
- 如果需求只是瀏覽內容時，使用網頁只要有網路都可以閱讀，更加輕量化，也可以避免不小心用 APP 修改到內容。
### 1.2. 作為作為作品集、個人網站、Blog⋯⋯
#### 1.2.1. 作品集
- 作品集是在讓一個對你陌生的人了解你的最佳途徑，能夠直接的圖顯出個人的專業實務能力
- 個人網站在求職時，能讓對你不熟悉的面試官能有最初步的了解，是個展示個人能力的平台
#### 1.2.2. 個人網站、Blog
- 持續在上面更新技術文章、筆記、個人成長等內容，能夠反應出個人的進步與成長。對自己而言能夠審視；對面試者能夠讓他們了解我們是一個會不斷精進的人才。
- 養成持續產出內容的習慣，在未來不論是求職、升學、自我推薦時，都能有整理過的材料重複利用，避免浪費大量時間整理、蒐集素材。
- 建立個人品牌，網站內容會反映出個人的能力、價值觀、自律性、成長軌跡。
## 2. What? 需要什麼？
- Obsidian
- Go 語言環境
- GitHub 帳號
- Quartz
- Hugo

## 3. Get Start
### 3.1. 安裝 Hugo（quartz 是由 Hugo 驅動的）
- ref.
  [macOS | Hugo Prerequisites](https://gohugo.io/installation/macos/#prerequisites)
1. 建議安裝 Hugo workflow 經常會用到 Git, Go, Dart Sass
	``` command
	brew install sass/sass/sass
	brew install git
	brew install hugo
	```
### 3.2. 安裝 Go 語言環境
- ref.
	- [failed to install Hugo-obsidian · Issue #1 · jackyzha0/hugo-obsidian · GitHub](https://github.com/jackyzha0/hugo-obsidian/issues/1)
1. 安裝 go
	``` command
	brew install go
	```
2. 手動建立 .bash_profile 並在裡面新增下面文字
	```
	export GOPATH=/Users/$USER/go
	export PATH=$GOPATH/bin:$PATH
	```
3. 重新載入session
	```
	source ~/.bash_profile
	```
### 3.3. 安裝 Hugo-obsidian
- ref.
	- [GitHub - jackyzha0/hugo-obsidian: simple GitHub action to parse Markdown Links into a .json file for Hugo](https://github.com/jackyzha0/hugo-obsidian)
1. 安裝
	``` command
	go install github.com/jackyzha0/hugo-obsidian@latest
	```
2. 執行
	```
	hugo-obsidian -input=content -output=data -index=true
	```

### 3.4. 建立自己的 Quartz Repository
- ref. 
	- [Quartz Setup](https://quartz.jzhao.xyz/notes/setup/)
	- [Original Quartz Repository ](https://github.com/jackyzha0/quartz)

> [!NOTE]
> - fork 讓我們可以在自己的空間中去實驗、修改內容，而不影響到最初的 Reopsitory

1. fork Quartz
  ![[將markdown筆記用GitHub page部署成靜態網頁當blog.png|300]]
  ![[將markdown筆記用GitHub page部署成靜態網頁當blog-2.png|400]] 
2. clone repo 到本地
	  ```command
	  git clone https://github.com/YOUR-USERNAME/quartz
	  ```

### 3.5. 本地預覽修改的內容
- ref.
	- [Preview Changes](https://quartz.jzhao.xyz/notes/preview-changes/)
1. 進入 clone 到本地的 Quartz 目錄
	```
	cd <Location-Of-Your-Local-Quartz>
	```
2. Start Local Server
	```
	Make Serve
	```
3. View Your Site In A Browser At [http://Localhost:1313/](http://Localhost:1313/)
   ![[將markdown筆記用GitHub page部署成靜態網頁當blog-4.png]]
### 3.6. 將 Quartz 部署到網路上
- ref.
  - [Deploying Quartz to the Web](https://quartz.jzhao.xyz/notes/hosting/)

1. `Settings > Action > General > Workflow Permissions` 選擇 `Read And Write Permissions`
   ![[將markdown筆記用GitHub page部署成靜態網頁當blog-5.png]]
2. 啟用 GitHub Page，將紅色框框中改成master和root。如果有域名可以自定域名。
   ![[將markdown筆記用GitHub page部署成靜態網頁當blog-7.png]]
3. 

> [!Warning] 
> 沒有設定域名的情況下，repo 名稱需要是 username.github.io，實際使用上才不會有產生的連結沒辦法連上的問題。不然就是要去改 quartz 的程式內容。

### 3.7. 個性化 Quartz
...
### 3.8. 3.8.
...

---
> [!info] Quartz 3 已停用
> - 未來都改成 Quartz 4，所以搖重來一次了
> - [[Quartz4envSetting]]

# 3.8. Ref.
- [Go環境安裝on Mac - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10200457)
- [🪴 Quartz 3.3](https://quartz.jzhao.xyz/)
- [GitHub - jackyzha0/quartz: 🌱 host your own second brain and digital garden for free](https://github.com/jackyzha0/quartz)
- [Publishing your Obsidian Vault Online with Quartz](https://brandonkboswell.com/blog/Publishing-your-Obsidian-Vault-Online-with-Quartz/)
- [macOS | Hugo](https://gohugo.io/installation/macos/)