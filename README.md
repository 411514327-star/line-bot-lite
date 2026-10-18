# line-bot-lite# # LINE bot 輕量版（和 AI 一起寫程式 W6 回家作業）

讓 LINE bot 用跑在自己電腦上的小模型（Ollama）回答問題。程式是老師提供的 `line_bot_lite.py`，我沒有修改。

## 怎麼裝
- 安裝 Python 3 和 Ollama
- 下載模型：`ollama pull gemma3:1b`（也可以用 `gemma4:e2b`，約 4.6 GB）
- 安裝 cloudflared（只有真的接 LINE 時才需要）

## 怎麼跑
- 模擬模式（不接 LINE），在 Windows PowerShell 輸入：
  - `$env:MODEL="gemma3:1b"`
  - `python line_bot_lite.py --simulate`
- 加上網搜尋：`python line_bot_lite.py --simulate --search`（要先用 `ollama signin` 登入 Ollama 帳號，而且模型要支援工具呼叫）
- 真的接 LINE：`python line_bot_lite.py`（LINE 通行碼和 Channel secret 在程式開起來時才貼，不寫進任何檔案）

## 我改了什麼、跑起來怎樣
- 模型：gemma3:1b
- 電腦：顯示卡5050Laptop GPU／記憶體16GB DDR5
- 速度：一題約 1 秒
- 改了：沒有改程式，直接使用老師提供的版本
- 卡在：加 `--search` 時，gemma3:1b 回應 400：`gemma3:1b does not support tools`，這個模型不支援呼叫工具，所以上網搜尋沒有成功
- 
