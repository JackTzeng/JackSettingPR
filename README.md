# JackSetting 官方 APK 發布庫

本 Repository **僅用於公開發布 JackSetting Android 正式 APK**。它不存放原始碼、簽章金鑰、私有 CI 設定或 QA 測試包。開發用 Repository `JackTzeng/JackSetting` 持續保持 **Private**。

> **最新正式版：v0.9.28（已公開發布）** — [查看 Release](https://github.com/JackTzeng/JackSettingPR/releases/tag/v0.9.28)。

## 直接下載

- **[Full 正式 APK](https://github.com/JackTzeng/JackSettingPR/releases/download/v0.9.28/JackSetting-v0.9.28-release.apk)** — 全部五個漫畫來源
- **[Clean 正式 APK](https://github.com/JackTzeng/JackSettingPR/releases/download/v0.9.28/JackSetting-v0.9.28-clean-release.apk)** — 漫畫集、CopyManga

上述檔案均已通過固定正式簽章及 SHA-256 檢查。請使用 Android 正常安裝流程，不要解除安裝已有正式版以免刪除收藏、紀錄和離線資料。

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

## 開發者發布流程（自動上傳，人工放行）

私有 `JackTzeng/JackSetting` 的 GitHub Actions 已具備 **跨 Repository 自動上傳程式**：

1. 在**私有**開發 Repo 的 Actions secrets 設定一次 `JACKSETTING_PUBLIC_RELEASE_TOKEN`（fine-grained PAT：只授權 `JackTzeng/JackSettingPR`，`Contents: Read and write`）。
2. 每次 Private `main` 正式建置成功後，自動檢查 Full/Clean 固定簽章、套件 ID 與版本碼，並在本公開 Repo 建立 **Draft Release**，上傳兩個 APK，遠端核對 SHA-256。
3. Draft Release 尚未提供給一般使用者或 App 內 `releases/latest`。在手機實測 Full→Full、Clean→Clean、閱讀資料與離線檔案保留後，再由發行負責人按 **Publish release** 放行。
4. 正式發布後，JackSetting App 的使用者可以使用設定頁「檢查更新 → 下載並安裝」。之後版本只要提高 `versionCode` 與 `versionName`，同一流程就能再次執行。

**不需要人工下載後重新上傳 APK**。不設定跨 Repo 憑證時，私有 CI 會顯示警告並跳過公開 Draft 上傳；絕不將簽章金鑰或 GitHub Token 存進 APK。不要將 QA/Debug APK 放入此 Repo。

跨 Repo 憑證設定：<https://github.com/JackTzeng/JackSetting/settings/secrets/actions>

詳細發行要求：APK 必須為相同的正式簽章、更高的 Android `versionCode`，並且兩種版本的 Release 資產均經 SHA-256 確認。已正式發佈的相同版本不得被 CI 靜默覆寫。
