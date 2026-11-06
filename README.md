# Horizon Docker 镜像

自动化构建 [Thysrael/Horizon](https://github.com/Thysrael/Horizon) 的多架构 Docker 镜像(MIT)。

📡 AI 驱动的新闻雷达：聚合多源信息，生成中英双语每日简报。

## 镜像

- GHCR: `ghcr.io/dockers-x/horizon` (amd64/arm64)
- Docker Hub: `czyt/horizon`

标签：语义化版本(基于上游 pyproject version + 日期)、`latest`。

## 用法

```bash
docker run --rm -v ./data:/app/data --env-file .env ghcr.io/dockers-x/horizon:latest --hours 24
```

配置见上游 README（`.env` 放 API keys，`data/config.json` 定义信源）。

## 自动化

`.github/workflows/docker.yml` 每 6 小时检查上游 main 分支变化，有新提交则锁定该 commit 构建镜像并记录版本。
