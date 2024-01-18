---
title: 用 Mac Automator 建立快速動作將檔案轉成 PDF
aliases:
  - Mac Automator-Convert to PDF
draft: false
created: 2024-01-17
tags:
  - Mac
  - Automator
  - 拖延
  - procrastination
date: 2024-01-18
---
## 前言
拖延！沒錯又是拖延！在我準備開始做考古題之前，我想，不如就先把所有考古題載下來準備好吧！但我發現許多檔案不是 PDF 使用起來有些麻煩，因為之後還想要把它印出來，一個個轉檔又太麻煩，就在想應該有更快速的方法。結果我就花了一下午搞這個，什麼鬼考古都沒做到⋯⋯。為了讓我的拖延不只是拖延，我必須把它寫成一篇文章分享。
## 預期成效
我希望：
- 操作體驗接近原生系統
- 不需要開新應用程式去做這件事（網頁、其他離線轉檔工具、編輯器）
因此想到可以使用 Automator 這個內建工具去建立快速動作（quick action），後續詳述操作細節。
## 步驟
1. 安裝 Libreoffice：因為要使用到這個開源軟體的 cli 操作文件功能
	``` cli
	brew install libreoffice
	```
2. Automator 建立新動作
   ![[Mac Automator-Convert to PDF.png]]
3. 插入程式碼
	``` shell
	# For one or multiple selected document(s) (e.g. .doc/x, .rtf, etc.) in the Finder, convert to PDF
	# in the original file location. One can explicitly set parentdir to the full POSIX path
	# of the intended PDF output directory, rather than the original file location.
	
	function app_test {
		# test if the application is installed and return 1 if false condition
		[[ -e /Applications/LibreOffice.app ]] && return 0 || return 1
	}
	
	# test for application installation. Warn user if it is not found, and exit Service workflow.
	[[ app_test -eq 0 ]] || ( /usr/bin/osascript -e 'display dialog \"LibreOffice is not installed.\"';exit 1 )
	
	for f in "$@"
	do
		# if the file is zero length or non-existent then ignore
	   [[ -s $f ]] || continue
	
		# The output directory is original file location
		parentdir="$(dirname "${f}")"
	   /Applications/LibreOffice.app/Contents/MacOS/soffice --headless --convert-to pdf:draw_pdf_Export --outdir "${parentdir}" "${f}"
	
	done
	exit 0
	```
	1. 儲存並新增動作名稱


## Demo
![[Mac Automator-Convert to PDF-1.png]]
## Ref.
- [如何在 macOS 上一键批量把 PPT 和 Word 文件转成 PDF - 少数派](https://sspai.com/post/44140)
- [MacOS环境在终端使用Libreoffice的soffice命令](https://shaichunfeng.com/post/2021/06/11/make-soffice-of-libreoffice-work-on-macos/)
- [macOS 命令行批量 .doc / .ppt 转 .pdf - 知乎](https://zhuanlan.zhihu.com/p/561923128)
- [Mac下实现批量Word或PPT转PDF - 知乎](https://zhuanlan.zhihu.com/p/391820589)
- [Libreoffice命令行实现office转pdf(Windows、Linux)\_libreoffice-convert-CSDN博客](https://blog.csdn.net/CheneyKing/article/details/122323156)
- [Quick actions convert to DOC/DOCX to a PD… - Apple Community](https://discussions.apple.com/thread/251424342?sortBy=best)