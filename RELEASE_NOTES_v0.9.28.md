# JackSetting v0.9.28 — Full / Clean 正式簽章候選版

- **狀態：正式 APK 已由 Private 專案簽章完成，尚未上傳本公開 Repository 的 GitHub Release。**
- 建置日期：2026-11-10
- 版本：`0.9.28`，Android `versionCode = 92`，升級自 `0.9.27 / 91`
- 正式簽章憑證 SHA-256：`586C2DA17B0E167F32CC40437D0A8A868D47FA47F12CB631C5A0B1565CB0307A`
- Build CI：`https://github.com/JackTzeng/JackSetting/actions/runs/42757467608`（Private，只有開發者可查看）
- 公開正式 Release 目前**尚未建立**；不應向一般使用者宣稱可下載或已完成實機更新驗收。

## 正式 APK 與 SHA-256

| 版本 | APK 檔名 | Android 套件 ID | SHA-256 |
|---|---|---|---|
| Full | `JackSetting-v0.9.28-release.apk` | `com.jacktzeng.jacksetting` | `b53e505f34b4bf7ac7440b3b4320d6cdf9143a6c64ef690bcc3de4d95f33c767` |
| Clean | `JackSetting-v0.9.28-clean-release.apk` | `com.jacktzeng.jacksetting.clean` | `5c9d396da3256ba8f2e9e786c934df72316927c6d4c44ebe3906596ec3d27216` |

CI 已對兩個 APK 的固定正式簽章、套件名稱、版本碼及版本名稱完成驗證，並成功將產物發佈至 Private 開發 Repository 的 `v0.9.28` Release。檔案必須**原封不動**複製到本公開 Repository 的對應正式 Release。

## 更新內容

- 全部漫畫來源共用精簡的單列閱讀導覽介面，包含章節選單與前後章操作。
- 支援章節的漫畫來源保留章末切章按鈕。
- 漫畫集及 WNACG 的永久離線保存操作移入章節選單；不把一般快取誤稱為永久保存。
- 首頁整合繼續閱讀與收藏作品更新摘要。
- 收藏更新通知採手動確認，不因閱讀自動清除。
- 漫畫卡小／中尺寸與可收合篩選偏好統一於各來源。
- 新增「設定 → 應用程式更新」：由使用者手動檢查本公開 Repository 的最新**正式** Release，下載與驗證 APK，再交由 Android 確認安裝；不會要求使用者登入 GitHub。

## 對外發布前必須完成

1. 從 Private `JackSetting v0.9.28` Release 下載 **正式 Full + Clean** APK（不得下載任何 QA/debug）。
2. 比對上表的檔名、SHA-256、套件 ID、版本碼及簽章。
3. 在 `JackTzeng/JackSettingPR` 建立 tag `v0.9.28` 的正式 GitHub Release，填入以上更新內容，上傳兩個 APK。
4. 確認兩個 Release Asset 可以**不登入 GitHub**直接下載，且公開 Release API 能查到它們。
5. Android 手機實測 Full→Full、Clean→Clean 原地升級，以及收藏、閱讀紀錄、離線檔案保留情況。未完成前，不應標記為實機 QA PASS。

**重要：** 這是第一次包含 App 內更新功能的正式版本，仍需以手動方式安裝一次；之後的正式新版才可在 App 內使用「檢查更新 → 下載並安裝」。
