# 語音刷卡記帳 (Voice Card Expense Tracker)

> **線上版網址 (GitHub Pages)**：https://major617056.github.io/voice-card-expense-tracker/  
> **手機直接修改程式碼 (點右上角鉛筆圖示)**：https://github.com/Major617056/voice-card-expense-tracker/edit/main/index.html  
> **Google 雲端硬碟 `Anti` 備份資料夾**：https://drive.google.com/drive/folders/1n22f75s24aiSG-Q-V4OnUmkElkj4shZi

---

## 📱 如何在手機上自行修改與更新本專案？

本專案採用 **單一獨立 HTML 檔案 (`index.html`)** 架構設計，所有介面（HTML + Tailwind CSS）與功能邏輯（JavaScript）皆集中在同一檔案內，免安裝開發環境，直接在手機上即可修改：

### 方式 1：使用手機瀏覽器或 GitHub App 直接修改（最推薦，自動更新線上版）
1. 在手機瀏覽器或 **GitHub App** 開啟 [`index.html`](https://github.com/Major617056/voice-card-expense-tracker/blob/main/index.html)。
2. 點擊右上角的 **「鉛筆圖示 (Edit)」** 進入編輯模式。
3. 修改文字、配色或程式碼後，點擊右上角 **「Commit changes」** 儲存。
4. 等待約 30～60 秒，GitHub Pages 線上版（https://major617056.github.io/voice-card-expense-tracker/）重新整理即自動生效！

### 方式 2：從 Google 雲端硬碟 `Anti` 資料夾修改
- 所有專案原始碼、歷史版本（v1 ~ v8）與完整對話紀錄皆已備份於 Google 雲端硬碟 `Anti` 資料夾中。
- 在手機上可使用 **Runestone / Koder (iOS)** 或 **Acode / QuickEdit (Android)** 直接開啟雲端硬碟中的 `index.html` 或 `語音刷卡記帳.html` 編輯。

---

## 🗺️ `index.html` 程式碼區塊導覽（手機修改快速對照表）

| 行號範圍 | 功能區塊說明 | 常見修改項目 |
| :--- | :--- | :--- |
| **第 1 ~ 40 行** | 網頁標題 (`<title>`) 與字體引入 | 修改網頁標題名稱 |
| **第 41 ~ 135 行** | `<style>` 自訂外觀與動畫樣式 | 修改米白背景色 (`#F6F4EF`)、翡翠綠主色 (`#059669`)、錄音脈衝動畫 |
| **第 136 ~ 380 行** | 頂部導覽列 + 「語音輸入記帳」主畫面 HTML | 修改大型圓形麥克風按鈕文字、表單欄位名稱 |
| **第 381 ~ 655 行** | 「消費明細與雲端管理」分頁 HTML | 修改統計卡片、Google Drive 自動備份區、Gmail 刷卡通知對帳區塊 |
| **第 658 ~ 685 行** | 刪除確認彈跳視窗 (`deleteConfirmModal`) | 修改刪除前的提示文字與按鈕樣式 |
| **第 688 ~ 712 行** | `STORAGE_KEY` 與 `INITIAL_RECORDS` 預設範例資料 | 修改初次開啟時的預設示範消費紀錄 |
| **第 816 ~ 920 行** | `parseChineseNumber` & `parseSpokenExpense` 語音解析 | 調整語音口語斷詞關鍵字與中文數字轉換規則 |
| **第 950 ~ 1140 行** | `startRealVoiceCapture` 真實麥克風持續語音辨識 | 調整說話停頓自動結束秒數（預設 `SILENCE_TIMEOUT_MS = 3000` 即 3 秒） |
| **第 1224 ~ 1300 行** | `deleteRecord` & 10 秒復原 (`Undo`) 機制 | 調整刪除確認視窗與 10 秒復原倒數邏輯 |
| **第 1485 ~ 1630 行** | Google Apps Script (GAS) 雲端同步與 Gmail 掃描腳本範本 | 修改自動備份資料夾名稱（預設 `Anti/語音刷卡記帳_自動備份`） |
| **第 1740 ~ 1955 行** | `reconcileGmailTransactions` & `parseBankNotificationText` | 新增或調整各家銀行刷卡通知信/簡訊的解析規則 |
| **第 1959 ~ 2080 行** | `performCloudBackup` & 每日自動任務排程 | 修改每日自動雲端備份與每日自動掃描 Gmail 的觸發設定 |
