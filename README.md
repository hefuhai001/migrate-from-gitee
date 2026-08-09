# migrate-from-gitee

> 将 Gitee 仓库批量迁移到 GitHub 的自动化工具

## 📖 项目简介

使用 GitHub Actions 自动化批量迁移 Gitee 仓库到 GitHub，支持公开/私有仓库的自动识别。

## ✨ 功能特点

- 批量迁移多个仓库
- 自动识别公开/私有仓库
- 保留完整 Git 历史（所有分支和标签）
- 基于 GitHub Actions，无需本地环境

## 🚀 使用方法

### 1. 配置 Secrets

在仓库的 `Settings` → `Secrets and variables` → `Actions` 中添加：

| Secret 名称 | 说明 |
|------------|------|
| `GITEE_USERNAME` | Gitee 用户名 |
| `GITEE_TOKEN` | Gitee 私人令牌（需勾选 `repo` 权限） |
| `GH_PAT` | GitHub Personal Access Token（需勾选 `repo` 权限） |

### 2. 编辑仓库列表

在 `.github/workflows/migrate-cli.yml` 中修改 `REPOS` 数组，列出需要迁移的仓库名：

```yaml
REPOS=(
  "repo-name-1"
  "repo-name-2"
  # ...
)
