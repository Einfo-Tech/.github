# Einfo-Tech Shared Workflows

组织级共享 GitHub Actions Workflow。

## wecom-notify

将 Push / Delete / PR 合并等事件推送到企业微信群机器人。

### 使用方法

在各仓库的 `.github/workflows/notify.yml` 中添加：

```yaml
name: Notify WeCom

on:
  push:
    branches: ['**']
  delete:
  pull_request:
    types: [opened, closed]

jobs:
  notify:
    uses: Einfo-Tech/.github/.github/workflows/wecom-notify.yml@main
    secrets: inherit
```

无需在各仓库单独配置 Secret，组织级 `WECOM_WEBHOOK` 自动继承。
