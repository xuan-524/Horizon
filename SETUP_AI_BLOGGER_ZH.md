# Horizon 中文 AI 博主版部署说明

本版本已经完成以下预配置：

- 每天北京时间 07:30 由 GitHub Actions 自动运行
- 生成中文 AI 新闻日报并发布到 GitHub Pages
- 聚合 AI 实验室、开源工具、行业新闻和社区观点
- 最多保留 18 条高价值内容，避免信息过载和模型费用失控
- 默认关闭邮件、Webhook、Twitter 和付费信息源
- 自动使用 GitHub Actions 自带的 `GITHUB_TOKEN`，无需创建个人访问令牌

## 你只需要完成的步骤

### 1. 准备 AI 密钥

默认使用 DeepSeek：

- GitHub Secret 名称：`DEEPSEEK_API_KEY`
- 不要把密钥写入代码、提交记录或聊天消息

如果你更想使用 OpenAI、Gemini、Claude、通义千问或豆包，需要同步修改
`data/config.github.json` 和工作流中的环境变量。

### 2. 添加 GitHub Secret

进入你的 Horizon 仓库：

1. 打开 `Settings`
2. 打开 `Secrets and variables` → `Actions`
3. 点击 `New repository secret`
4. Name 填 `DEEPSEEK_API_KEY`
5. Secret 填你的 DeepSeek API Key

### 3. 首次运行

1. 打开仓库的 `Actions`
2. 选择 `Daily Horizon Summary`
3. 点击 `Run workflow`
4. 等待任务完成并确认出现 `gh-pages` 分支

### 4. 开启 GitHub Pages

1. 打开 `Settings` → `Pages`
2. Source 选择 `Deploy from a branch`
3. Branch 选择 `gh-pages`
4. Folder 选择 `/ (root)`
5. 保存后等待站点发布

## 可选推送

日报站点稳定运行后，再按需开启飞书、钉钉、企业微信、Discord、Slack 或通用
Webhook。默认先不开启，避免首次部署同时排查多个外部系统。

## 验收标准

- Actions 手动运行成功
- `gh-pages` 分支生成日报文件
- Pages 页面可以打开
- 日报为中文，条目数不超过 18
- 仓库中不存在明文 API Key
