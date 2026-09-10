# Nibs 内测版下载源

这个仓库**不放代码**，只放 Nibs 桌面版内测包的构建产物，供应用内「检查更新」匿名读取。

- 主仓库（私有）：https://github.com/grobenis/Nibs
- 客户端读取的固定地址：
  `https://github.com/grobenis/Nibs_release/releases/latest/download/versions.json`

## 这些资产是什么

| 文件 | 说明 |
|---|---|
| `versions.json` | 更新清单。应用按平台取自己那份：版本、下载地址、sha256、大小。 |
| `sticky-notes-app_<版本>_amd64.deb` | Linux x64 安装包（Ubuntu 22.04 实测）。 |

Release 由主仓库的 `.github/workflows/release.yml` 在推送 `v*` tag 时自动发布。
**请勿手工改动这里的资产**——下次发版会覆盖，且客户端校验的 sha256 会对不上。

## 手动安装

```bash
sudo dpkg -i sticky-notes-app_<版本>_amd64.deb
```

---

> **这个 README 请勿删除。** 本仓库必须**至少有一次提交**：GitHub 不允许在空仓库上
> 把 Release 定稿，接口会返回 `Repository is empty.`，Release 会永久停在草稿状态——
> 而草稿对匿名下载是不可见的，`releases/latest/download/` 也就永远 404。
