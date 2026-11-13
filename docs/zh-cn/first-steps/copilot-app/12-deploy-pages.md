---
title: "第 12 课 - 使用 GitHub Pages 部署网站"
description: "使用 GitHub Copilot 应用配置 Pages 工作流、审查拉取请求，并验证 Space Quiz 已上线。"
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

使用 GitHub Pages 部署 Space Quiz，让它拥有公开访问地址。Copilot 可以准备工作流并指导部署，但你仍需负责审查更改并确认网站已上线。

本课将完成以下任务：

- 请 Copilot 配置 GitHub Pages 部署。
- 在合并之前审查工作流和拉取请求。
- 跟进部署并验证已发布的网站。

## 场景

Space Quiz 已位于 GitHub 仓库中，但用户还需要一种简单的体验方式。使用 GitHub Pages 发布单文件网站，无需添加服务器或运行时依赖，即可通过公开 URL 访问。

## 请 Copilot 准备部署

> [!WARNING]
> 创建拉取请求可能会提交并推送代码。发送此提示之前，请检查审批设置和目标仓库。设置为 **Approve all** 时，不要认为系统一定会再次请求确认。

在 `space-quiz` 的 Copilot 应用会话中发送以下提示：

```plaintext
为此仓库准备 GitHub Pages 部署。创建 GitHub Actions 工作流，在需要时构建网站，并在更改进入默认分支后将网站部署到 GitHub Pages。如果仓库中还没有 README，请添加一个，介绍此应用以及如何在本地运行它。使用这些更改创建拉取请求，并报告链接以及所需的 Pages 设置或权限。不要合并、启用自动合并、更改 Pages 设置或部署。停止并等待我审查。
```

## 审查工作流和拉取请求

1. 确认只有在仓库中尚无 README 时才添加了 README。
2. 审查拉取请求中的更改，包括工作流的构建和部署步骤、触发条件及权限。
3. 确认工作流从默认分支部署，而不是从尚未合并的拉取请求部署。
4. 请求修正并审查更新后的差异。在授权合并之前，等待拉取请求所需的检查全部通过。

## 授权合并和部署

> [!WARNING]
> 以下提示授权智能体合并已审查的拉取请求、更改仓库的 Pages 设置并发布网站。只有在完成审查并确认仓库和拉取请求后才能发送。根据审批设置，这些操作可能不会再次请求确认。

将 `<PR_NUMBER>` 替换为已审查的拉取请求编号，然后单独发送以下提示：

```plaintext
我已审查此仓库中的拉取请求 <PR_NUMBER>，并授权合并和部署。使用 GitHub Actions 启用 GitHub Pages；只有在所需检查通过后才合并该拉取请求，并持续监控部署，直到成功。报告已上线网站的最终 URL。如果你没有启用 Pages 或合并的权限，请准确说明我需要批准或执行什么操作；网站上线之前不要报告成功。
```

![三阶段示意图：space-quiz 拉取请求已合并；GitHub Actions 的 Deploy website 运行成功，包含 Build website、Upload artifact 和 Deploy to Pages 步骤；Space Quiz 已在 yourname.github.io/space-quiz/ 上线。](../../../_images/first-steps-app-pages-deploy.svg)

## 验证部署

1. 跟进 GitHub Actions 部署运行，直到成功。
2. 打开报告的 URL，确认 Space Quiz 已加载。

如果智能体无法启用 Pages 或合并拉取请求，请按照它提供的具体说明操作。只有在部署成功且网站正常加载后，才能将任务视为完成。

## 总结和后续步骤

Space Quiz 现已作为实时网站发布，你也已亲自验证部署，而不是仅依赖智能体的报告。继续学习[第 13 课：回顾与后续步骤][next-lesson]。

[next-lesson]: ../13-review/
