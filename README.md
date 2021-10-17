# Google Cloud Text-to-Speech API

Google 雲平台推出的，提供多語言多語音模型的文字轉語音服務

![「檢查專案中的潛在問題」GitHub Actions 作業流程狀態標章](https://github.com/libre-knowledge/google-cloud-tts-api/actions/workflows/check-potential-problems.yml/badge.svg "本專案使用 GitHub Actions 自動化檢查專案中的潛在問題") [![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white "本專案使用 pre-commit 檢查專案中的潛在問題")](https://github.com/pre-commit/pre-commit) [![REUSE 規範遵從狀態標章](https://api.reuse.software/badge/github.com/libre-knowledge/google-cloud-tts-api "本專案遵從 REUSE 規範降低軟體授權合規成本")](https://api.reuse.software/info/github.com/libre-knowledge/google-cloud-tts-api)

## 擷取 API 演示網頁的語音音訊

以下說明如何手動擷取演示網頁所載入的轉換結果音訊

1. 訪問 [實際運用 Text-to-Speech \| 示範 \| Text-to-Speech：自然流暢的語音合成服務  \|  Cloud Text-to-Speech API  \|  Google Cloud](https://cloud.google.com/text-to-speech#put-text-to-speech-into-action#section-2) 網址輸入您要轉成語音的文字資料以及轉換參數
1. 開啟瀏覽器的開發者控制台，切換到「網路」分頁
1. 點擊「SPEAK IT」按鈕並完成可能會有的機器人防護驗證挑戰
1.尋找網址開頭是 <https://cxl-services.appspot.com/proxy?url=https://texttospeech.googleapis.com/...> 的 API 呼叫，透過開發者控制台可能會有的下載回應功能將回應下載或複製下來，應可得到如隨附的 JSON 格式資料：

    ```json
    {
    "audioContent": "UklGRgKCEgBXQVZFZm10IBAAAAABAAEAwF0AAIC7AAACABAAZGF0...
    ```

    將除 `audioContent` 鍵之值以外的內容移除，然後保存為 _自訂檔名_.base64

1. 開啟一文字終端並切換工作目錄到 _自訂檔名_.base64 所在目錄，執行 `base64 -d result.base64 > result.wav` 命令將 base64 編碼的音訊資料解編碼，產出之 result.wav 即為轉換結果之音訊

## 參考資料

* [Text-to-Speech：自然流暢的語音合成服務  |  Cloud Text-to-Speech API  |  Google Cloud](https://cloud.google.com/text-to-speech)  
  官方網站

---

本主題為[自由知識協作平台](https://libre-knowledge.github.io/)的一部分，除部份特別標註之經合理使用(fair use)原則使用的內容外允許公眾於授權範圍內自由使用

如有任何問題，歡迎於本主題的[議題追蹤系統](https://github.com/libre-knowledge/google-cloud-tts-api/issues)創建新議題反饋
