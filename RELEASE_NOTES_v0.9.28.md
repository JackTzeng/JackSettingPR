# JackSetting v0.9.28 — 正式公開版本

**狀態：已於 2026-11-10 正式公開發布。** [公開 Release](https://github.com/JackTzeng/JackSettingPR/releases/tag/v0.9.28)

- 正式版：`0.9.28`，Android `versionCode = 92`，升級自 `0.9.27`（版本碼 91）
- 發布來源：`JackTzeng/JackSetting`（Private），使用既有的固定正式簽章
- 簽章憑證 SHA-256：`586C2DA17B0E167F32CC40437D0A8A868D47FA47F12CB631C5A0B1565CB0307A`
- **CI 自動跨 Repo 發布：PASS**，見 [Build Android APK Run 42765314651](https://github.com/JackTzeng/JackSetting/actions/runs/42765314651)（私有，只對授權帳號開放）
- GitHub Actions 已自動上傳、驗證 Full／Clean，並於專案負責人確認驗收後，透過受限放行工作流程從 Draft 正式發布

## APK 檔案規格

| 版本 | APK 名稱 | 套件 ID |
| --- | --- | --- |
| Full | `JackSetting-v0.9.28-release.apk` | `com.jacktzeng.jacksetting` |
| Clean | `JackSetting-v0.9.28-clean-release.apk` | `com.jacktzeng.jacksetting.clean` |

**校驗碼以該筆 GitHub Release Assets 的 `digest: sha256:...` 欄位及 Release Notes 為準。** 每次重新建置的 APK 位元組可能不同，請勿依賴此長期保存的文字檔作為固定 checksum 表。GitHub Actions 每次自動上傳 Draft 時會同步更新該筆 Release 的 SHA-256 說明並驗證遠端資產。

## 本次更新

- 全來源共用單列章節閱讀工具列，支援來源保留章末前後章切換
- 漫畫集與 WNACG 的永久離線保存入口集中於章節選單
- 首頁繼續閱讀與收藏更新摘要
- 收藏更新需手動確認，不因閱讀自動清除
- 小／中漫畫卡與可收合篩選偏好
- 設定頁「檢查更新 → 下載並安裝」，查詢本公開 Repo 的正式 Release，驗證 APK 後由 Android 系統確認安裝

## 發布 Gate

1. **完成**：Full／Clean 正式建置、固定簽章、套件 ID／版本及 SHA-256 驗證
2. **完成**：自動跨 Repo 上傳及私有來源檔案比對
3. **專案負責人確認**：手機驗收通過，授權公開發布
4. **完成**：受限 GitHub Actions 正式發布 v0.9.28，`releases/latest` 成功回傳正式版

放行工作流程：[Publish approved JackSettingPR release #42768251297](https://github.com/JackTzeng/JackSetting/actions/runs/42768251297)（需私有 Repo 權限）。

第一次安裝含一鍵更新的 v0.9.28 仍需正常安裝 APK 一次；往後版本才可從 App 內下載並安裝。
