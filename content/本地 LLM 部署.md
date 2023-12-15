---
title: 本地 LLM 部署
aliases:
  - 本地 LLM 部署
  - "Local LLM Application: Ollama"
draft: false
created: 2023-12-15
tags:
  - LLM
  - Ollama
date: 2023-12-15
---
# 前言
不知從何時開始，我沈迷於各種生產力工具、提高生產力的內容，可能是為了緩解我的知識焦慮。
曾經用 OpenAI 搭配插件幫我做筆記跟讀筆記，但因為免費試用到期了，又想要當免費仔，所以想要搞本地LLM但因為拖延症跟對技術的 PTSD，遲遲沒有開始。直到前幾天在推特看到有人分享 Ollama + Obsidian 的玩法，才萌生了來搞一下的念頭。又發現用這個工具技術門檻不高，能搞。
# 安裝步驟
## Step.1 下載安裝 Ollama
- 下載 Ollama 對應系統的，因為我的電腦是 mac 所以使用 macOS 版本
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
## 相關連結
Ollama GitHub：[GitHub - jmorganca/ollama: Get up and running with Llama 2 and other large language models locally](https://github.com/jmorganca/ollama)
Ollama 支援模型：[library](https://ollama.ai/library)
dolphin-mixtral（經調教沒有審查機制的模型）：[Tags · dolphin-mixtral](https://ollama.ai/library/dolphin-mixtral/tags)
# 一些 Ollama 使用
## CLI
- 執行模型（llama2 為例）：`ollama run llama2`
- 更新本地模型：`ollama pull llama2`
- 移除本地模型：`ollama rm llama2`
- 列出本機模型：`ollama list`
- 
# 搭配使用更對味
## Obsidian
### Obsidian Ollama Plugin
- [Obsidian Ollama plugin](https://github.com/hinterdupfinger/obsidian-ollama)
- 安裝完基本上就可以直接使用
- 使用心得待捕
### Obsidian BMO Chatbot Plugin
- [Obsidian BMO Chatbot plugin](https://github.com/longy2k/obsidian-bmo-chatbot)
- 再 OLLAMA REST API URL 貼上`http://127.0.0.1:11435` （如果有改過可能不一樣）
- 繞過 CORS 政策，運行 Ollama 伺服器：`OLLAMA_ORIGINS=* OLLAMA_HOST=127.0.0.1:11435 ollama serve`
- 預設是 chatGPT 模型，所以要在聊天介面輸入指令 `\model [model_name]` 切換成本地的模型
- `\help` 看更多操作（以這則筆記當成參考等）
### Obsidian-ai-research-assistant
- [GitHub - InterwebAlchemy/obsidian-ai-research-assistant: Prompt Engineering Research Tool for AI APIs](https://github.com/InterwebAlchemy/obsidian-ai-research-assistant)
## Logseq
- 
## Raycast
- 
# 其他紀錄
- 除了 Ollama，要自己 host LLM 也可以使用 [LocalAI](https://github.com/mudler/LocalAI)
- 對於 Obsidian 來說有個知名的插件  Copilot 就可以用 LocalAI
- BMO + Ollama 一直說 API key 錯誤，但我也沒找到文件裡面有說到什麼 API Key
# 使用心得
- #todo 
# Ref.
- [现在最火的开源大语言模型当属 mixtral-8x7 了，已经...](https://twitter.com/dotey/status/1735457201395814770)
- [一直感觉很多笔记软件的AI功能设计偏了。。最近用Obsidian+AI插件，打造了...](https://x.com/fuxiangPro/status/1734580043228328198?s=20)
- [写个如何用 Ollama 在 Mac 本地跑 LLM，并且用在 Obsidian 上处理...](https://x.com/op7418/status/1734492326599467291?s=20)
- [GitHub - jmorganca/ollama: Get up and running with Llama 2 and other large language models locally](https://github.com/jmorganca/ollama)
- [GitHub - longy2k/obsidian-bmo-chatbot: Generate and brainstorm ideas while creating your notes using Large Language Models (LLMs) such as OpenAI's "gpt-3.5-turbo" and "gpt-4" for Obsidian.](https://github.com/longy2k/obsidian-bmo-chatbot?tab=readme-ov-file)
- 