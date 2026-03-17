# Spec Repo

Spec 的唯一真實來源（Source of Truth）。

## 分支策略

| 分支 | 對應環境 | 說明 |
|------|---------|------|
| `dev` | 開發環境 | 反映最新的開發中 spec |
| `main` | Production | 反映線上正式版的 spec |

## 目錄結構

```
spec-repo/
├── backend/          # 後端技術 spec（每個微服務一個子目錄）
├── frontend/         # 前端技術 spec（每個前端系統一個子目錄）
├── business/         # 業務 spec（前後端合併產出）
├── scripts/          # CI/CD 用的腳本
└── docs/             # 系統設計文件
```

## 更新方式

### 日常更新（自動）
1. 開發者在各 Repo 產出 changeset
2. push to dev 後 CI 自動合併 changeset → 推 MR 到本 Repo 的 dev 分支
3. Production MR 時觸發 dev → main merge

### 初始化（手動）
使用 Spec Keeper plugin 的 `/spec:init` + `/spec:push` 指令。

### 查看 Spec
- PM / User 看 `main` 分支 = 線上目前的行為
- PM / User 看 `dev` 分支 = 即將上線的行為
