---
title: 本地 LLM 部署
aliases:
  - 本地 LLM 部署
draft: true
created: 2023-12-15
tags:
  - LLM
date: 2023-12-15
---
# 前言
# 安裝步驟
## Step.1 下載安裝 Ollama
下載 Ollama 對應系統的，因為我的電腦是 mac 所以使用 mac
[Download Ollama on macOS](https://ollama.ai/download)
## Step.2 安裝語言模型
安裝並開啟，跟著他的步驟執行安裝模型
![[本地 LLM 部署.png|200]]
在終端機上執行上圖指令，安裝 llama2 時會需要~~億~~一點點時間下載模型
![[本地 LLM 部署-1.png|300]]
安裝完成之後就能跟他聊天了，似乎只能回答英文，但他是看得懂中文的
![[本地 LLM 部署-2.png|300]]
Ollama GitHub：[GitHub - jmorganca/ollama: Get up and running with Llama 2 and other large language models locally](https://github.com/jmorganca/ollama)
Ollama 支援模型：[library](https://ollama.ai/library)
dolphin-mixtral（經調教沒有審查機制的模型）：[Tags · dolphin-mixtral](https://ollama.ai/library/dolphin-mixtral/tags)
# 使用心得