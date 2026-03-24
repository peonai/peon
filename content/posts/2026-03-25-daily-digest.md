---
title: "OpenAI 细化 Sora 安全设计，Mozilla 推出 Agent 知识共享平台"
date: 2026-03-25T07:30:00+08:00
categories: ["digest"]
tags: ["AI", "OpenAI", "Sora", "Mozilla", "Claude Code", "Agent"]
---

本期涵盖 3 月 22 日至 3 月 24 日的资讯。

## OpenAI 披露 Sora 安全设计细节

来源：https://openai.com/index/creating-with-sora-safely

OpenAI 发布了 Sora 2 和 Sora 应用的安全设计文档，核心是「从源头构建安全」。每段视频都带有可见和不可见的来源信号，嵌入 C2PA 元数据，内部还有反向图像和音频搜索工具可以追踪视频来源。

在人物肖像方面，OpenAI 引入了「角色」机制：用户可以创建自己的数字分身，只有用户本人决定谁能使用这些角色，随时可以撤销授权。上传照片生成视频需要声明已获得被拍摄者的同意，涉及儿童的内容有更严格的审核。

针对青少年用户，Sora 限制了成人内容、关闭了向成人推荐青少年 profile 的功能，家长可以在 ChatGPT 中管理青少年的 DM 和信息流设置。有害内容在生成阶段就会被多层防护拦截，包括性内容、恐怖主义宣传和自我伤害相关内容。

这套安全框架把「谁能用你的形象」「能不能撤回」「生成后是否可追踪」这条权限链补得更完整了。不是技术突破，而是把平台治理做得更细。视频生成从演示产品往可规模化的内容平台推进了一步。

---

## Mozilla 推出 cq：Agent 版 Stack Overflow

来源：https://blog.mozilla.ai/cq-stack-overflow-for-agents/

Mozilla AI 发布了 cq（读作 /ˈkɒl.ə.kwi/），一个面向 AI Agent 的知识共享平台。思路很简单：Agent 在执行任务时会遇到各种问题，与其让每个 Agent 独立踩坑，不如把学到的经验共享出来。

实际场景是这样的：一个 Agent 发现 Stripe 返回 200 状态码但 body 里是限速错误，它把这个知识提交到 cq commons。其他 Agent 在处理 Stripe API 之前查询 commons，就知道要处理这种边缘情况了。

这个项目回应了一个现实问题——Stack Overflow 的月度提问量从 2014 年高峰期的 20 万条跌到 2025 年底的 3862 条。开发者转向 ChatGPT 和 Claude 寻求帮助，但 Agent 们各自为战，重复踩同一个坑。

cq 目前有 Claude Code 和 OpenCode 插件、MCP 服务器管理本地知识库、团队 API 用于组织内共享、UI 供人工审核。代码开源，Mozilla 在征集社区反馈。

这个方向有价值，但成败取决于能否建立足够的参与度。知识库的覆盖面决定了 Agent 是否愿意查询，Agent 的贡献意愿又取决于知识库的质量——典型的双边市场冷启动问题。

---

## Simon Willison 用 Claude Skill 生成 Starlette 1.0 示例

来源：https://simonwillison.net/2026/Mar/22/starlette/

Starlette 1.0 发布了。这个 Python ASGI 框架是 FastAPI 的基础，长期以来没有 1.0 版本意味着 API 不稳定，现在终于承诺了稳定性。主要的 breaking change 是启动和关闭逻辑从 `on_startup`/`on_shutdown` 参数改成了 lifespan 上下文管理器。

Simon Willison 用 Claude 的 skill-creator skill 生成了一个 Starlette 1.0 的 skill 文档，包含所有特性的代码示例。然后用这个 skill 让 Claude 生成一个任务管理应用——有项目、任务、评论和标签，用 SQLite 和 Jinja2 模板。

Claude 不仅生成了代码，还自己跑测试验证功能正常。这个流程展示了「框架知识打包成 skill，再交给 agent 执行」的具体做法。

对开发者来说，这类 skill 的价值在于：当模型训练数据里的框架版本过时，skill 可以注入最新的 API 用法。是一个临时但实用的方案。

---

## Neil Kakkar 谈如何用 Claude Code 提升效率

来源：https://neilkakkar.com/productive-with-claude-code.html

Neil Kakkar 分享了他加入 Tano 后 6 周内把提交量翻倍的经验。核心思路是：从「实现者」变成「Agent 的管理者」。

他做了几件事：写了 `/git-pr` skill 自动生成 PR 描述，把构建工具换成 SWC 让重启时间从 1 分钟降到 1 秒以内，用 Claude Code 的预览功能让 Agent 自己验证 UI，给每个 worktree 分配独立端口避免冲突。这些改变让他能同时运行 5 个 Agent 在不同分支上工作。

他强调的是：最高杠杆的工作不是写功能，而是搭建让 Agent 高效工作的基础设施。每个瓶颈解决后，下一个瓶颈会自动显现——经典的理论约束问题。

这篇文章不是产品发布或技术突破，但对「如何真正把 Agent 接入工作流」有参考价值。关键是基础设施，不是 AI 本身。

---

## Christopher Meiklejohn 用 Claude 测试移动应用

来源：https://christophermeiklejohn.com/ai/zabriskie/development/android/ios/2026/03/22/teaching-claude-to-qa-a-mobile-app.html

Christopher Meiklejohn 一个人开发了 Zabriskie（一个社区应用），需要覆盖 Web、iOS 和 Android 三个平台。他用 Capacitor 把 React Web 应用包装成原生应用，但测试成了问题——Playwright 测不了原生 shell 里的 WebView，XCTest 和 Espresso 又测不了 HTML 内容。

解决方案是让 Claude 驱动移动平台。Android 相对简单：WebView 暴露 Chrome DevTools Protocol socket，可以注入 localStorage 实现登录、导航、截图。90 分钟搞定。

iOS 是另一回事。WKWebView 不暴露 CDP，Safari Web Inspector 用的是私有协议。他花了 6 小时处理各种问题：AppleScript 打不了 `@` 符号（被当快捷键）、原生弹窗无法自动关闭、坐标点击在不同工具里有不同的坐标系。最后的方案涉及写 TCC 数据库预授权通知权限、用 `ui_describe_point` 探测 UI 坐标、组合 AppleScript 和 idb 执行点击。

两个平台现在每天早上自动跑一遍，覆盖 25 个屏幕，发现问题时自动在论坛发 bug 报告。这篇文章的价值在于展示了移动端自动化的现实难度——Android 给了一个 WebSocket 说「随便用」，iOS 给了一扇锁着的门说「请用 Xcode」。