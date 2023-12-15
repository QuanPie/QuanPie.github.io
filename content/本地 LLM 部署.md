---
title: 本地 LLM 部署
aliases:
  - 本地 LLM 部署
draft: false
created: 2023-12-15
tags:
  - LLM
date: 2023-12-15
---
# 前言
不知從何時開始，我沈迷於各種生產力工具、提高生產力的內容，可能是為了緩解我的知識焦慮。
曾經用 OpenAI 搭配插件幫我做筆記跟讀筆記，但因為免費試用到期了，又想要當免費仔，所以想要搞本地LLM但因為拖延症跟對技術的 PTSD，遲遲沒有開始。直到前幾天在推特看到有人分享 Ollama + Obsidian 的玩法，才萌生了來搞一下的念頭。又發現用這個工具技術門檻不高，能搞。
# 安裝步驟
## Step.1 下載安裝 Ollama
- 下載 Ollama 對應系統的，因為我的電腦是 mac 所以使用 mac
- [Download Ollama on macOS](https://ollama.ai/download)
## Step.2 安裝語言模型
- 安裝並開啟，跟著他的步驟執行安裝模型
	- ![[本地 LLM 部署.png|200]]
- 在終端機上執行上圖指令，安裝 llama2 時會需要~~億~~一點點時間下載模型
	- ![[本地 LLM 部署-1.png|300]]
- 安裝完成之後就能跟他聊天了，似乎只能回答英文，但他是看得懂中文的
	- ![[本地 LLM 部署-2.png|300]]
- 似乎是可以回答中文的，但是翻譯能力沒有很好，回答問題也會優先用英文回答
	- ![[本地 LLM 部署-3.png|300]]
# 搭配使用更對味
## Obsidian
- [Obsidian BMO Chatbot plugin](https://github.com/longy2k/obsidian-bmo-chatbot)
- [Obsidian Ollama plugin](https://github.com/hinterdupfinger/obsidian-ollama)
## Logseq
## Raycast
# 使用心得

# Ref.
Ollama GitHub：[GitHub - jmorganca/ollama: Get up and running with Llama 2 and other large language models locally](https://github.com/jmorganca/ollama)
Ollama 支援模型：[library](https://ollama.ai/library)
dolphin-mixtral（經調教沒有審查機制的模型）：[Tags · dolphin-mixtral](https://ollama.ai/library/dolphin-mixtral/tags)