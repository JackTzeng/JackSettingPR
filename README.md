# JackSetting 官方 APK 發布庫

本 Repository **僅用於公開發布 JackSetting Android 正式 APK**。它不存放原始碼、簽章金鑰、私有 CI 設定或 QA 測試包。開發用 Repository `JackTzeng/JackSetting` 持續保持 **Private**。

> **目前狀態：尚未發布第一個正式版 Release。** 請勿將本頁 README 當成可下載的正式 APK。

## 使用者如何安裝、更新

1. 第一次安裝：從本 Repo 的 [Releases](https://github.com/JackTzeng/JackSettingPR/releases) 下載符合需求的 **Full** 或 **Clean** 正式版 APK，並依 Android 指示安裝。
2. 後續更新：在已安裝的 JackSetting **設定 → 應用程式更新 → 檢查更新**。
3. 有新版時按 **下載並安裝**。App 會在內部下載並驗證 APK，然後開啟 Android 安裝確認畫面。
4. 更新需沿用同一個 Android 套件名稱與正式簽章；正確的原地更新可保留手機上的收藏、閱讀紀錄及離線資料。**不要為了更新而解除安裝正式 App。**

首次具備上述更新功能的正式版本仍需手動安裝一次；之後才能透過 App 內更新。

## 官方 Full／Clean APK 格式

正式 Release 標籤：`vX.Y.Z`（例如 `v0.9.29`），不得設為 Draft 或 Pre-release；每個正式 Release 必須同時包含：

| 版本 | APK 檔名範例 | Android 套件名稱 |
| --- | --- | --- |
| Full | `JackSetting-v0.9.29-release.apk` | `com.jacktzeng.jacksetting` |
| Clean | `JackSetting-v0.9.29-clean-release.apk` | `com.jacktzeng.jacksetting.clean` |

上述檔名只是格式範例，**不是已發布的檔案**。禁止把 `qa`、`debug` 或暫時簽章的 APK 發布成正式版本。

正式 APK 必須從私有專案的正式發布流程產生，通過套件名稱、`versionCode`、APK 簽章憑證及 SHA-256 完整性檢查；新版必須比舊版的 `versionCode` 高。Release 應附上更新說明。

## App 使用的公開更新來源

`https://api.github.com/repos/JackTzeng/JackSettingPR/releases/latest`

- App **只在使用者按「檢查更新」時**發起查詢，無背景自動檢查。
- 只使用正式版 Release，排除 Draft 與 Pre-release。
- Full 只取 Full APK，Clean 只取 Clean APK。
- App 下載後核對 Release 內的 APK SHA-256、下載長度、套件名稱、版本碼及簽章，確認後才呼叫 Android 系統安裝程式。
- 公開 Release 無須 GitHub 登入，也**不會在 APK 內放 GitHub Token**。
- 若目前 API 回傳 404，代表尚未有公開的正式 Release；不能視為已完成更新。

## 開發者發布檢查表

1. 私有開發 Repo 的正式版本已通過 CI、實機驗收與固定正式簽章驗證。
2. 以正確的版本標籤建立本 Repo 的正式 GitHub Release。
3. 上傳同一版本的 **Full＋Clean** 正式 APK，核對檔名、版本碼、套件名稱、簽章及 SHA-256。
4. Release 填寫實際更新內容，並確認兩個 Assets 均可公開匿名下載。
5. 使用現有正式 App 分別實測 Full→Full、Clean→Clean 的原地更新，以及收藏／歷史／離線內容保留。
6. 驗證成功才對外宣布；發布失敗不得用 QA APK 替代。

**發布原則：** 本 Repo 只放正式簽章 APK 與版本資訊。初期可人工上傳；跨 Repo 自動發布待手動流程穩定再導入。
