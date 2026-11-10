# JackSetting v0.9.28 — 正式簽章候選版

**狀態：已自動上傳至 [JackSettingPR 的 Draft Release](https://github.com/JackTzeng/JackSettingPR/releases)，尚未正式公開。**

- 正式版：`0.9.28`，Android `versionCode = 92`，升級自 `0.9.27`（版本碼 91）
- 發布來源：`JackTzeng/JackSetting`（Private），使用既有的固定正式簽章
- 簽章憑證 SHA-256：`586C2DA17B0E167F32CC40437D0A8A868D47FA47F12CB631C5A0B1565CB0307A`
- **CI 自動跨 Repo 發布：PASS**，見 [Build Android APK Run 42765314651](https://github.com/JackTzeng/JackSetting/actions/runs/42765314651)（私有，只對授權帳號開放）
- GitHub Actions 產出的 Full／Clean 正式 APK 已自動上傳公開 Repo 的 **v0.9.28 Draft**，遠端 SHA-256 經比對完全一致

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

1. **完成**：Full／Clean 正式建置與固定簽章驗證
2. **完成**：自動跨 Repo 上傳 Draft，並比對 APK SHA-256
3. **尚未完成**：Android 手機 Full→Full、Clean→Clean 的原地升級與資料／離線漫畫保留驗收
4. **尚未完成**：將 Draft Release 按 Publish release 正式公開，驗證無登入下載及 `releases/latest`

第一次安裝含一鍵更新的 v0.9.28 仍需正常安裝 APK 一次；往後版本才可從 App 內下載並安裝。
