# GitHub 为什么这样工作：从代码网盘到协作操作系统

> 十篇文章，依次回答 GitHub 的 Why、What 与 How。

这不是一套命令说明书。

命令说明书解决的是“下一步点哪里”。可你一旦换了电脑、换了界面、遇到冲突，说明书就失效了。真正有用的学习，应该让你在陌生场景中仍然能判断：现在发生了什么，为什么要这么设计，接下来做什么风险最小。

这十篇文章只有一条主线：**GitHub 管理的不是文件，而是变化。**

## 阅读顺序

1. [GitHub 不是代码网盘](./01-GitHub不是代码网盘.md)——先看见它解决的根本问题
2. [Commit 是给变化办身份证](./02-Commit是给变化办身份证.md)——把变化变成可解释的历史
3. [Branch 是低成本试错权](./03-Branch是低成本试错权.md)——理解并行与可逆
4. [本地与远端是两本可以对账的账簿](./04-本地与远端是两本可以对账的账簿.md)——理解 clone、push、fetch、pull
5. [Pull Request 是一份变化提案](./05-PullRequest是一份变化提案.md)——理解为什么先讨论再合并
6. [Issue 是问题的容器](./06-Issue是问题的容器.md)——理解为什么动手前先写清楚
7. [Review 与 Actions 是信任生产线](./07-Review与Actions是信任生产线.md)——理解人审与机审
8. [Fork 是没有写权限时的参与权](./08-Fork是没有写权限时的参与权.md)——理解开源协作
9. [冲突、撤销与秘密泄露](./09-错误不可怕失控才可怕.md)——理解安全边界
10. [AI 时代，GitHub 是变化控制系统](./10-AI时代GitHub是变化控制系统.md)——把全部概念串成完整方法

## 每篇怎么读

每篇都使用同一个认知顺序：

```text
旧误解 → 新定义 → 为什么重要 → 更深一层 → 怎么做 → 一个练习
```

不要一次读完。每天一篇。读完立刻做文末练习，并把结果提交到你自己的 `my-ai-learning` 仓库。

## 读完后的标准

你应该能不用术语解释：

- 为什么保存文件不等于提交；
- 为什么提交不等于推送；
- 为什么推送不等于合并；
- 为什么分支不是项目副本；
- 为什么 PR 不是一道多余手续；
- 为什么自动检查全绿仍然需要人；
- 为什么 AI 越能写代码，人越需要 GitHub。

会操作，只能让你完成一次任务。理解原因，才能让你处理下一次意外。

先读第一篇。先把“代码网盘”这个旧概念洗掉。

## 事实核对与延伸阅读

文章中的产品机制与安全边界以 GitHub 官方资料为依据；界面若变化，先找含义相同的入口，不要死记按钮位置。

- [About Git：版本控制、提交、分支与分布式仓库](https://docs.github.com/en/get-started/using-git/about-git)
- [About remote repositories：Clone、远端、HTTPS 与 SSH](https://docs.github.com/en/get-started/git-basics/about-remote-repositories)
- [About issues：任务、子任务、依赖与项目追踪](https://docs.github.com/en/issues/tracking-your-work-with-issues/learning-about-issues/about-issues)
- [Pull requests：讨论与审查变化的核心协作机制](https://docs.github.com/en/pull-requests/reference/pull-requests)
- [Pull request reviews：评论、批准与请求修改](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)
- [GitHub Actions：工作流与自动化](https://docs.github.com/en/actions/concepts/workflows-and-actions)
- [About forks：Fork、Branch 与上游关系](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks)
- [Removing sensitive data：秘密轮换与历史清理](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository)
- [Review Copilot output：AI 产出仍需彻底审查](https://docs.github.com/en/copilot/how-tos/copilot-on-github/use-copilot-agents/review-copilot-output)
