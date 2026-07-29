# AudioGo

Windows 桌面修音工具，提供音訊載入、波形檢視、播放，以及取樣類型轉換、
高通濾波與響度處理。

## 下載

前往右側 [Releases](../../releases) 頁面下載，建議選擇標記為 **Latest** 的版本。

| 版本 | 說明 |
|------|------|
| **v0.2.0** | v0.2 Processing 正式版。轉換取樣類型（聲道／取樣率／位深／dither）、高通濾波（200 Hz / 4 階）、響度工具組（音量調整 ±1／±3 dB、小聲補強、自動響度最大化 Ctrl+M）、區段選取處理、Undo/Redo、A/B 比較、16-bit 量化＋TPDF dither |
| v0.2.0-dev.6 | v0.2.0 的最後一個開發預覽 |
| v0.2.0-dev.4 | Audition 風格 UX（two-cursor、Loop 播放、自動捲動）、選單列整併、最近開啟檔案、存檔／另存新檔、release 附 build provenance 與 SHA-256 checksum |
| v0.2.0-dev.3 | 修正中文／日文路徑閃退、區段選取處理、zoom in 選取高亮修正 |
| v0.2.0-dev.2 | About 對話框（含系統需求）、CI tag-only 發版機制、artifact 加版號 |
| v0.2.0-dev.1 | 一鍵優化（DSP 壓縮 + LUFS 正規化）、A/B 比對、版號顯示於標題列（已知問題：中文路徑閃退） |

> `-dev.N` 為開發預覽版，功能可能變動；一般使用請選正式版。

## 系統需求

- Windows 7 / 8 / 10 / 11（64-bit）
- 無需安裝，解壓縮後直接執行 `audiogo.exe`

## 使用方式

1. 下載並解壓縮 `AudioGo-win64-v<版本>.zip`
2. 執行資料夾內的 `audiogo.exe`
3. 拖放音訊檔案（WAV、MP3、FLAC）至視窗，或使用選單「檔案 → 開啟」
4. 在波形上拖曳可框選區段；處理操作若有選取範圍則只作用於該範圍，否則作用於整個檔案
5. 從「處理」選單套用處理，或使用快捷鍵：

   | 按鍵 | 功能 |
   |------|------|
   | Ctrl+M | 自動響度最大化（一鍵推至交付響度） |
   | `+` / `−` | 音量增加／減少 1 dB（Ctrl 加按為 3 dB） |
   | `/` | 小聲補強 1 dB（Ctrl 加按為 3 dB） |
   | H | 套用高通濾波（200 Hz） |
   | F11 | 轉換取樣類型 |
   | B | 原始／處理結果比較切換 |
   | Ctrl+Z | 復原 |

6. 滿意後用 Ctrl+S 儲存，或 Ctrl+Shift+S 另存為 WAV

完整快捷鍵與功能說明見
[原始碼 repo 的 README](https://github.com/LinChihShan/AudioGo#readme)。

## 檔案完整性

每個版本皆附 `.sha256` 檔案，可用 PowerShell 核對：

```powershell
Get-FileHash -Path AudioGo-win64-v0.2.0.zip -Algorithm SHA256
```

ZIP 內另含 `BUILD-METADATA.txt`，記錄版本、來源 commit 與建置時間。

## 回饋

使用時遇到問題或有改善建議，請直接聯絡開發團隊。
