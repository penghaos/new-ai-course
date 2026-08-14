# GitHub 新手速查表

## 一句话总图

```text
Issue 定义问题 → Branch 隔离工作 → 修改文件 → Add 选择变化
→ Commit 保存本地历史 → Push 发到 GitHub → PR 提议合并
→ Review / Actions 检查 → Merge 进入 main → Pull 同步给其他人
```

## 概念对照

| 概念 | 一句话 | 常见误解 |
|---|---|---|
| Git | 分布式版本控制系统 | 等同于 GitHub |
| GitHub | 托管 Git 仓库并支持协作的平台 | 只是代码网盘 |
| Repository | 带版本历史的项目空间 | 普通文件夹 |
| Commit | 一组有说明的历史变化 | 保存文件 |
| Branch | 独立的变化线 | 复制整个项目 |
| Merge | 组合两条变化线 | 覆盖文件 |
| Issue | 问题、需求或任务的记录 | 只用于报错 |
| Pull Request | 请求审查并接纳一组变化 | 请求别人帮忙下载 |
| Remote | 可同步的另一个仓库位置 | 只有 GitHub 才算远端 |
| origin | 默认远端的惯用昵称 | GitHub 的固定关键词 |
| upstream | Fork 场景中原项目的惯用昵称 | 必须存在的远端 |
| Fork | 自己账号下的关联远端副本 | Star 或 Clone |
| Clone | 带历史和远端关联的本地复制 | 下载 ZIP |

## 每天开始

```bash
git switch main
git pull
git switch -c feat/任务名称
```

## 修改与提交

```bash
git status                 # 看状态
git diff                   # 看未暂存变化
git add 具体文件           # 选择本次提交内容
git diff --staged          # 再检查一次
git commit -m "docs: 写清做了什么"
```

常见提交类型：

- `feat:` 新功能
- `fix:` 修复
- `docs:` 文档
- `test:` 测试
- `refactor:` 重构但不改变功能
- `chore:` 日常维护
- `ci:` 自动化流程

## 发送与同步

```bash
git push -u origin 当前分支名   # 第一次推送
git push                        # 后续推送
git fetch                       # 获取远端消息，先不整合
git pull                        # 获取并整合当前分支
```

## 观察历史

```bash
git log --oneline --decorate -10
git diff main...HEAD
git branch
git remote -v
```

## PR 自查清单

- [ ] 关联了正确 Issue；
- [ ] base 和 compare 分支方向正确；
- [ ] 标题准确概括一个目的；
- [ ] 写明背景、改动、验证和风险；
- [ ] Files changed 没有意外文件；
- [ ] 没有密钥、隐私和大型垃圾文件；
- [ ] 链接、测试或人工检查已完成；
- [ ] 自动检查结果已看过；
- [ ] 评审意见已处理或说明理由。

## 出错时的第一反应

先停下来，保存错误信息，然后运行：

```bash
git status
git branch --show-current
git log --oneline --decorate -10
git diff
git diff --staged
git remote -v
```

把“我执行了什么、完整错误是什么、期望什么、实际什么”写清楚，再求助。不要在不知道状态时连续尝试强制命令。

## 红色危险区

在完全理解前，不要随便执行：

```text
git reset --hard
git clean -fd
git push --force
```

也不要：

- 把 Token、密码、私钥、`.env` 提交；
- 把 Token 发到聊天或截图里；
- 将陌生脚本直接以管理员权限运行；
- 直接在 `main` 上试验大改动；
- 用下载 ZIP 代替协作所需的 Clone；
- 把“能合并”误当成“结果正确”。

## 认证速记

- 网页：密码/通行密钥 + 2FA；
- GitHub Desktop：浏览器授权；
- GitHub CLI：`gh auth login` 后用浏览器授权；
- HTTPS Git：凭证管理器或个人访问令牌；
- SSH：本地私钥 + GitHub 账号中的公钥；
- Git 操作不使用 GitHub 账号密码。

## 求助模板

```markdown
### 我想做什么

### 我刚执行了什么

### 完整错误信息

### 当前状态
- 操作系统：
- 当前分支：
- `git status`：
- 是否已经推送：

### 我已经尝试过什么
```

## 官方入口

- [GitHub 入门](https://docs.github.com/en/get-started)
- [Git 基础](https://docs.github.com/en/get-started/using-git/about-git)
- [身份验证](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github)
- [GitHub Actions](https://docs.github.com/en/actions/get-started)
