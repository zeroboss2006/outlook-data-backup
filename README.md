# 📦 Outlook 資料檔備份與還原教學 (.pst/.ost)

適用版本：Outlook 2010、2013、2016、2019、Outlook for Microsoft 365

本篇教學說明如何備份及轉移 Microsoft Outlook 的郵件資料檔（.pst），以利系統重灌、轉移電腦或建立定期備份機制。

---

## 📍 預設儲存路徑

| 檔案類型 | 預設路徑 |
|----------|-------------------------------|
| `.pst` 個人資料夾檔 | `C:\Users\<使用者名稱>\Documents\Outlook Files` |
| `.ost` 離線快取檔（無法備份） | `C:\Users\<使用者名稱>\AppData\Local\Microsoft\Outlook` |

> 💡 提示：`AppData` 是隱藏資料夾，請至檔案總管中開啟「顯示隱藏的項目」。

---

## 🔍 如何找到 Outlook 資料檔案位置

### 步驟：

1. 開啟 Outlook。
2. 點選 `檔案` > `帳戶設定` > `帳戶設定`。
3. 切換到 `資料檔案` 分頁。
4. 選取其中一筆帳戶後，點選「**開啟檔案位置**」。

系統將會開啟包含 `.pst` 或 `.ost` 檔案的資料夾。

---

## 💾 備份 .pst 檔案

### 🧪 建議備份的內容：

| 類型 | 是否可備份 | 說明 |
|------|------------|------|
| `.pst` | ✅ 可備份 | 本機郵件、行事曆、聯絡人 |
| `.ost` | ⛔ 不建議 | 為雲端帳號的離線快取，可重建 |

### 🔧 備份批次檔範例：

```bat
@echo off
set BACKUP_DIR=D:\Backup\Outlook
mkdir "%BACKUP_DIR%" 2>nul
copy "%USERPROFILE%\Documents\Outlook Files\*.pst" "%BACKUP_DIR%"
echo 備份完成！
pause
```

### 📥 匯入 .pst 到新電腦
將 .pst 檔案複製到新電腦的 Documents\Outlook Files 資料夾。

開啟 Outlook。

點選 檔案 > 開啟與匯出 > 匯入/匯出。

選擇「從另一個程式或檔案匯入」。

選擇「Outlook 資料檔 (.pst)」。

選擇要匯入的 .pst 檔案位置。

設定是否允許重複項目、目標資料夾等選項。

點擊【完成】，資料將會匯入 Outlook。

### 🛑 注意事項
匯入前請關閉 Outlook，再操作檔案複製或匯入。

.ost 不建議備份，為快取檔案，重設帳號即可自動重建。

建議定期備份 .pst，避免資料遺失。

可使用 scanpst.exe 嘗試修復損毀的 .pst。

### 📚 參考資料
Microsoft Support: Transfer Outlook Data Files
