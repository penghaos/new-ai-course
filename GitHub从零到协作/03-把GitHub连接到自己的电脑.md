# 第 3 课：把 GitHub 连接到自己的电脑

## 3.1 这次多了哪些状态

网页练习只有 GitHub 上的远端仓库。连接电脑后，需要同时理解：

```mermaid
flowchart LR
    W["工作区：你正在编辑的文件"] -->|"stage / git add"| S["暂存区：本次准备提交什么"]
    S -->|"commit"| L["本地仓库：提交历史"]
    L -->|"push"| R["GitHub 远端仓库"]
    R -->|"fetch / pull"| L
```

新手最容易混淆的是：

- 保存文件，只改变工作区；
- 暂存，选择下一次提交包含什么；
- commit，只写入本地历史；
- push，才把本地提交发送到 GitHub。

## 3.2 路线 A：使用 GitHub Desktop（推荐先学）

### 第一步：安装并登录

从 [GitHub Desktop 官网](https://desktop.github.com/)下载安装。打开后选择通过浏览器登录 GitHub，按提示授权。

### 第二步：克隆仓库

选择 **File → Clone Repository**，在 GitHub.com 标签中找到 `my-ai-learning`。

选择一个容易找到的本地位置。点击 **Clone**。

克隆（clone）得到的不是普通下载包，而是：当前文件 + 完整 Git 历史 + 远端关联。

### 第三步：新建分支

在 **Current Branch** 中选择 **New Branch**，名称：

```text
docs/add-prompts-guide
```

先切到 `main` 并 Fetch/Pull 最新内容，再从 `main` 新建分支，是一个值得养成的习惯。

### 第四步：修改文件

用任意文本编辑器在仓库内创建 `prompts/README.md`：

```markdown
# 我的提示词库

## 使用原则

1. 先写清目标和背景；
2. 说明期望的输出格式；
3. 对重要结果进行核验；
4. 不在提示词里放密码或隐私。
```

保存后切回 GitHub Desktop。左侧会出现变化文件，右侧显示具体差异。

### 第五步：提交

在 Summary 输入：

```text
docs: 添加提示词库使用说明
```

点击 **Commit to docs/add-prompts-guide**。观察：文件变化清空了，但 GitHub 网站上还没有这个提交，因为它目前只在本地。

### 第六步：发布分支并开 PR

点击 **Publish branch** 或 **Push origin**。然后选择 **Create Pull Request**，浏览器会打开 PR 页面。按上一课的模板补全描述并创建。

## 3.3 路线 B：使用命令行理解底层

命令行不是必须替代 Desktop。你可以先阅读和观察，再亲手执行。

### 检查 Git

打开终端：

```bash
git --version
```

如果没有 Git，按 [GitHub 官方安装说明](https://docs.github.com/en/get-started/git-basics/set-up-git) 安装。不同系统步骤不同，不要从陌生下载站获取安装包。

### 配置提交身份

这两项会写入今后的提交记录：

```bash
git config --global user.name "你的名字或 GitHub 用户名"
git config --global user.email "你的 GitHub 邮箱或 noreply 邮箱"
```

检查配置：

```bash
git config --global --list
```

如果不想在公开提交里暴露真实邮箱，可在 GitHub 邮箱设置中启用隐私，并使用 GitHub 提供的 `noreply` 邮箱。

### 克隆

在 GitHub 仓库首页点击 **Code**，复制 HTTPS 地址：

```bash
git clone https://github.com/你的用户名/my-ai-learning.git
cd my-ai-learning
```

如果这份仓库已被 GitHub Desktop 克隆，不要在同一位置重复克隆；直接在终端进入现有目录即可。

### 每天开始工作的标准流程

```bash
git switch main
git pull
git switch -c docs/add-resources
```

含义：回到主线 → 同步远端主线 → 从最新主线创建工作分支。

如果旧版 Git 不支持 `git switch`，可使用 `git checkout main` 和 `git checkout -b 分支名`。

### 修改后观察状态

创建或编辑文件后：

```bash
git status
git diff
```

`status` 回答“现在有哪些状态”；`diff` 回答“具体改了什么”。提交前先看这两个命令，是最有价值的习惯之一。

### 选择并提交变化

```bash
git add resources/README.md
git diff --staged
git commit -m "docs: 添加学习资源索引"
```

新手先明确添加具体文件，避免习惯性 `git add .` 把临时文件、下载文件或秘密一并提交。

### 推送

```bash
git push -u origin docs/add-resources
```

第一次推送的 `-u` 建立本地分支与远端分支的跟踪关系，之后通常只需 `git push`。

身份验证推荐使用 GitHub Desktop、GitHub CLI 的浏览器登录或系统凭证管理器。不要使用账号密码进行 Git 认证，也不要把 Token 写入远端网址。

## 3.4 12 个新手常用命令

| 命令 | 人话 | 是否改变状态 |
|---|---|---|
| `git status` | 我现在处于什么状态？ | 否 |
| `git diff` | 未暂存的变化是什么？ | 否 |
| `git diff --staged` | 下一次提交会包含什么？ | 否 |
| `git log --oneline` | 历史上有哪些提交？ | 否 |
| `git clone URL` | 把远端仓库完整复制到本地 | 是 |
| `git switch 分支` | 切换工作分支 | 是 |
| `git switch -c 新分支` | 创建并切换新分支 | 是 |
| `git add 文件` | 把变化放进暂存区 | 是 |
| `git commit -m "说明"` | 形成一个本地提交 | 是 |
| `git fetch` | 获取远端消息，不整合 | 是，较安全 |
| `git pull` | 获取并整合远端变化 | 是 |
| `git push` | 把本地提交发送到远端 | 是 |

先用只读命令观察，再用写命令行动。发生意外时，不要凭感觉连续执行更多命令。

## 3.5 `.gitignore`：告诉 Git 哪些文件不要管

在仓库根目录创建 `.gitignore`：

```gitignore
# 系统与编辑器临时文件
.DS_Store
Thumbs.db
.vscode/

# 环境变量和秘密
.env
.env.*

# 常见依赖与构建产物
node_modules/
dist/

# 临时文件
*.tmp
*.log
```

注意：`.gitignore` 只对尚未被追踪的文件生效。文件一旦进入历史，仅加入忽略规则并不能从历史中移除。

## 3.6 每日工作闭环

```text
同步 main → 建分支 → 修改 → status/diff → add → diff --staged
→ commit → push → PR → review/checks → merge → 本地切回 main → pull
```

结束后：

```bash
git switch main
git pull
git branch -d docs/add-resources
```

`-d` 只删除已经安全合并的本地分支；如果 Git 拒绝，先弄清原因，不要立刻改用强制删除。

## 3.7 常见故障

### `nothing to commit`

可能没有保存文件、编辑了另一个目录、变化被忽略，或内容与原来相同。先运行 `git status`，再确认当前路径和分支。

### `rejected` / 远端有你没有的提交

先同步再推送：

```bash
git pull
git push
```

若出现冲突，转到第 5 课。不要直接强制推送覆盖别人。

### `Authentication failed`

账号密码不能用于 Git 操作。用 GitHub Desktop、`gh auth login`、系统凭证管理器、个人访问令牌或 SSH 重新认证。Token 只给必要权限并设置有效期。

### 提交出现在错误分支

如果尚未推送，不要慌，也不要继续叠加操作。先记录 `git status` 和 `git log --oneline -5`，再查明移动提交的安全方法。新手可先在 Desktop 中查看历史，必要时请有经验的人协助。

## 本课练习

1. 分别在修改后、暂存后、提交后、推送后运行 `git status`，记录输出差异。
2. 一次修改两个文件，只暂存其中一个，用 `git diff` 和 `git diff --staged` 观察两个世界。
3. 在新分支完成 `resources/README.md`，推送并用 PR 合并。
4. 合并后在本地回到 `main` 并拉取，确认文件出现。

## 本课验收

- [ ] 能指出工作区、暂存区、本地仓库、远端仓库；
- [ ] 能解释 save、add、commit、push 的区别；
- [ ] 能用 Desktop 完成一次本地修改到 PR；
- [ ] 能安全使用 12 个常见命令中的核心 8 个；
- [ ] 知道认证失败时不该反复输入账号密码；
- [ ] 知道为什么不随手强制推送。
