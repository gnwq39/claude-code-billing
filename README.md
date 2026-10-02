# Claude Code 充值：分清 Pro、Max、Usage Credits 和 API 余额，避免把钱充错地方

搜索“Claude Code 充值”的人，通常遇到的是三种不同情况：

- Claude Code 登录后提示达到使用限制；
- 想继续进行长时间编码任务，不想等额度重置；
- 没有适合的海外支付方式，想通过第三方平台完成 Claude 订阅或 Claude API 充值。

这三种需求看起来都叫“充值”，实际对应的付款路径完全不同。你可能需要购买 Claude Pro 或 Max，也可能需要单独购买 Usage Credits；如果你是通过 Claude Console 或 API Key 使用 Claude Code，则要充值的是 Console 余额。买错产品，付款成功后也不一定能解决 Claude Code 的问题。

本文以 BeWild（bewild.ai）当前公开的 Claude 相关方案为例，整理 Claude Code 的计费逻辑、官方价格、第三方充值流程、套餐差异和购买前需要确认的事项。先说结论：**如果你只是用 Claude Code 写代码，优先判断自己是通过 Claude 账号登录，还是通过 Console/API Key 登录。**

## Claude Code 充值前，先确认你使用的是哪种计费方式

Claude Code 可以连接 Claude 的 Pro 或 Max 订阅，也可以通过 Claude Console 的 API 额度运行。Anthropic 官方明确区分这两套系统：Pro 或 Max 计划有包含的使用额度；Console/API 则按 API 用量计费。两者不能简单理解为同一个“Claude Code 余额”。

可以在终端里检查当前登录状态和环境变量：

bash
claude
/status


如果系统中设置了 `ANTHROPIC_API_KEY`，Claude Code 可能会优先使用 API Key，而不是你的 Pro 或 Max 订阅。这样产生的费用会进入 API 计费体系，不再消耗订阅内的使用量。Anthropic 官方也特别提醒了这一点。

简单判断如下：

| 使用方式 | 实际消耗什么 | 适合的充值方式 |
| --- | --- | --- |
| 使用 Claude 账号登录 Claude Code | Pro / Max 订阅内的共享使用额度 | 购买或升级 Pro、Max |
| Pro / Max 额度用完后继续使用 | Usage Credits 或 Usage Bundle | 在 Claude 的 Usage 页面购买用量包 |
| 使用 Claude Console 账号或 API Key | Console 预付额度，按 API 用量扣费 | 充值 Claude API / Console 额度 |
| 只使用 Claude 网页聊天 | Claude 订阅额度 | Pro、Max 或其他官方计划 |

如果你的 Claude Code 使用的是订阅账号，购买 API 余额并不会自动增加 Pro 或 Max 的五小时用量上限。反过来，购买 Pro 也不会自动获得 Claude API 额度。

## Claude Pro 和 Max 是否包含 Claude Code？

包含。Anthropic 当前说明，Pro 和 Max 计划可以在网页、桌面端、移动端以及终端中的 Claude Code 使用。Claude 和 Claude Code 共享同一套计划使用限制。

这意味着你在 Claude 网页里进行长对话、上传文件、运行工具，再到终端里执行代码任务，使用量可能会进入同一个限制池。Claude Code 并不是额外赠送的一套无限额度。

官方个人计划的公开基准价格如下：

- **Claude Pro：20 美元/月，或 200 美元/年**
- **Claude Max 5x：100 美元/月**
- **Claude Max 20x：200 美元/月**

Max 5x 和 Max 20x 仍然不是无限使用。它们主要提供更高的使用容量，具体限制还会受到模型、任务长度、上下文、工具调用和当前账号规则影响。官方计划页面也将 Max 5x 描述为 Pro 级别的更高使用容量，Max 20x 则面向更加频繁的使用场景。

### Pro 更适合什么情况？

如果你每天使用 Claude Code 的时间不算特别长，主要处理以下任务，Pro 通常更容易控制成本：

- 修改小型项目；
- 阅读和解释代码；
- 编写简单脚本；
- 修复少量报错；
- 生成测试代码；
- 偶尔处理一个中等规模仓库。

Pro 的问题在于，一旦你连续处理大型仓库、反复运行测试、要求模型多轮修改，使用限制可能比较快触发。此时升级 Max 5x 通常比不断等待额度重置更直接。

### Max 5x 和 Max 20x 怎么选？

Max 5x 的月费是 100 美元，适合把 Claude Code 当作日常开发工具的人，例如每天需要处理多个代码任务、长时间调试或频繁操作大型仓库。

Max 20x 的月费是 200 美元，适合高度依赖 Claude Code 的开发者、个人项目维护者或需要连续运行多个复杂任务的用户。但 200 美元并不等于无限量使用。你仍然需要观察账号中的实际 Usage 页面，确认当前额度和重置时间。

如果你只是偶尔遇到一次限制，不建议直接从 Pro 跳到 Max 20x。先等限制重置，或者确认是否可以使用 Usage Credits，通常更容易控制预算。

## 官方 Usage Credits 和 Claude API 充值有什么区别？

这是 Claude Code 充值中最容易混淆的部分。

### Usage Credits：给付费订阅超额使用

Anthropic 为 Pro、Max 和 Team 用户提供了额外的 Usage Credits。它们用于在套餐包含的使用额度耗尽后继续使用 Claude，包括 Claude Code、Claude Desktop、移动端 Claude、Cowork 以及部分第三方产品。

官方当前公开的 Usage Bundle 价格为：

| 用量包面额 | 折扣 | 实际支付 |
| ---: | ---: | ---: |
| 50 美元 | 10% | 45 美元 |
| 250 美元 | 20% | 200 美元 |
| 1000 美元 | 30% | 700 美元 |

个人 Pro 和 Max 用户每月购买折扣用量包的额度上限为 2000 美元；超过月度上限后，额外用量会按标准 Usage Credits 费率计费。用量包不会替代 Pro 或 Max 的基础额度，而是在套餐内额度用尽并启用额外用量后才开始消耗。

购买步骤通常是：

1. 登录 Claude；
2. 进入 `Settings`；
3. 打开 `Usage`；
4. 启用 Usage Credits；
5. 点击 `Buy usage`；
6. 选择用量包并确认付款。

如果你只是想解决“Claude Code 达到限制”的问题，官方 Usage Credits 更接近真正意义上的额外用量充值。

### Claude API / Console 余额：给 API Key 和 PAYG 使用

Claude Console 是另一套计费体系。它主要面向 API 调用、Workbench、应用程序和通过 API Key 登录的 Claude Code 工作流。

Anthropic 官方说明，Pro 或 Max 订阅不会自动包含 Claude API 额度。通过 Console/API 运行 Claude Code时，会按照 API 费率消耗 Console 余额。

这类余额适合：

- 通过 API Key 运行 Claude Code；
- 在服务器或脚本中调用 Claude；
- 使用 Claude API 开发应用；
- 需要独立管理组织、Workspace、API Key 和预算。

如果你只是登录 Claude Code 使用个人订阅，通常不需要先购买 API 充值。除非你明确知道自己使用的是 Console 账号或 API Key。

## BeWild 当前公开的 Claude 相关套餐

BeWild 的官网定位是通过微信、支付宝等方式帮助用户订阅部分 AI 服务。其公开帮助中心列出了 Claude Pro、Max 5x、Max 20x，以及 Claude API 额度充值方案。Claude 订阅流程通常需要登录自己的 Claude 账号，并按页面提示提交 Cookie；Claude API 充值流程则要求提交登录状态下的 Session Key。

下面整理与“Claude Code 充值”直接相关的公开方案。由于 BeWild 的动态结账页会根据商品、地区、付款方式和当前活动显示实际金额，静态页面并没有稳定展示所有方案的最终人民币或港币实付价格，购买前应以结账页为准。

| 套餐 / 方案 | 核心配置与用途 | 官方参考价格或充值面额 | 计费周期 | 购买入口 |
| --- | --- | ---: | --- | --- |
| Claude Pro | Claude 网页、桌面端、移动端与 Claude Code；标准个人使用额度 | 20 美元/月；200 美元/年 | 月付或年付 | [ 查看 Claude Pro 方案](https://bit.ly/Bewild) |
| Claude Max 5x | 更高使用容量，适合较频繁的 Claude Code 工作流 | 100 美元/月 | 月付 | [ 查看 Claude Max 5x 方案](https://bit.ly/Bewild) |
| Claude Max 20x | 更高档位，适合高频、长时间或大型项目任务 | 200 美元/月 | 月付 | [ 查看 Claude Max 20x 方案](https://bit.ly/Bewild) |
| Claude API / Console 20 | 向 Claude Console 账户充值 20 美元额度 | 充值面额 20 美元 | 按用量扣除 | [ 查看 Claude API 20 美元充值](https://bit.ly/Bewild) |
| Claude API / Console 100 | 向 Claude Console 账户充值 100 美元额度 | 充值面额 100 美元 | 按用量扣除 | [ 查看 Claude API 100 美元充值](https://bit.ly/Bewild) |

表中的 Claude Pro、Max 5x 和 Max 20x 是官方订阅价格基准，不代表通过第三方平台支付时的最终金额。BeWild 的帮助页面显示，Claude 订阅可以选择单月或多月连续订阅，长期订阅价格以页面当时展示为准；多月方案可能会提前预存余额并按月续费。

Claude API 方案则是另一类商品。BeWild 帮助中心公开列出 20 美元和 100 美元两种充值额度，并说明到账目标是 Claude 账户的默认工作区。

目前没有可验证的公开证据表明上述方案存在统一、长期有效的固定优惠码。你可以进入结账页检查是否出现优惠字段，但不要把历史页面、其他用户的邀请码或搜索结果中的旧价格当成当前实付价格。

## 通过 BeWild 订阅 Claude Pro 或 Max 的流程

如果你选择用 BeWild 开通 Claude Code 所需的 Pro 或 Max 计划，流程大致分为四步。

### 1. 选择 Claude 方案

进入订阅页面后，选择 Claude Pro / Max 相关卡片，再选择单月或多月方案。

单月方案通常只订阅一个周期，到期后不继续预存月份。多月方案可能采用按月自动续费或预存余额的方式，页面中的具体说明比宣传文字更重要，付款前要确认：

- 是新购、续费还是升级；
- 订阅几个月；
- 是否自动续费；
- 付款后能否在 Claude 官方账户中看到正确档位；
- 后续取消订阅会不会影响已预存月份。

### 2. 登录自己的 Claude 账号

BeWild 的 Claude 教程要求用户登录自己的 Claude 账号，并从 `claude.ai` 页面导出 Cookie JSON，再粘贴回订单页面。帮助中心强调，Cookie 必须从已经登录的 Claude 页面导出，不能从搜索引擎、Google 页面或其他网站复制。

Cookie 是账号凭证的一部分，处理时应注意：

- 只在自己的设备上操作；
- 不要把 Cookie 发到群聊或公开客服群；
- 不要把完整 Cookie 截图上传到论坛；
- 使用完后退出相关登录状态；
- 如果账号出现异常，及时重新登录并检查安全设置。

### 3. 核对付款金额和套餐档位

进入收银台后，重点核对以下内容：

- Claude Pro、Max 5x 还是 Max 20x；
- 单月还是多月；
- 实际货币和付款金额；
- 是否包含服务费；
- 是否有优惠；
- 付款收款方名称；
- 订单邮箱和账号是否对应。

BeWild 的帮助页面显示，支付完成后通常需要等待约 5 到 30 分钟，期间可以在订单或交易记录中查看进度。若页面正在处理，不建议反复创建新订单，以免出现重复付款或多个订单同时处理的情况。

### 4. 回到 Claude Code 验收

订阅成功后，不要只看第三方平台的“已完成”状态。还需要在 Claude 账号中检查：

- 当前计划是否变为 Pro、Max 5x 或 Max 20x；
- Claude 网页端是否能够使用；
- Claude Code 是否使用同一个账号登录；
- `/status` 显示的计划是否正确；
- 环境变量中是否仍然存在 `ANTHROPIC_API_KEY`。

如果 Claude Code 仍然走 API Key，刚买的 Pro 或 Max 可能不会被使用。此时可以先退出当前会话：

bash
claude logout
claude login


然后选择与 Claude Pro 或 Max 绑定的账号重新登录。Anthropic 官方也建议，在订阅账号与 Console 账号之间切换时使用 `/login`，并确认当前认证方式。

## 通过 BeWild 充值 Claude API 的流程

如果你的目标是给 Claude Console 增加 API 额度，应该选择 Claude API 充值，而不是 Claude Pro 或 Max。

BeWild 当前帮助中心列出的 API 充值面额为 20 美元和 100 美元。充值前需要确认目标账号和工作区，因为余额通常会进入账号的默认 Workspace。若一个账号有多个 Workspace，只看邮箱而不确认工作区，很容易误以为“充值没有到账”。

操作时建议按这个顺序：

1. 先进入 Claude Console，记录充值前余额；
2. 确认当前组织和默认 Workspace；
3. 在 BeWild 选择 Claude API 充值额度；
4. 按页面要求获取 Session Key；
5. 提交前确认 Session Key 来自已经登录的 Claude 页面；
6. 付款后保存订单号和付款记录；
7. 回到同一个 Console Workspace 检查余额；
8. 用小额测试请求验证 API 是否正常。

BeWild 的教程说明，Claude API 充值流程通常需要从登录后的页面打开开发者工具，在 Application → Cookies 中找到 `sessionKey`，并将其提交到充值页面。这个字段属于敏感账号凭证，不应该发给其他人或保存在公开位置。

### API 充值后仍然无法使用怎么办？

余额增加不代表所有 API 请求都会自动成功。还需要检查：

- API Key 是否属于充值的 Workspace；
- 当前模型是否有权限；
- 请求格式是否正确；
- 是否触发速率限制；
- 是否设置了错误的 `ANTHROPIC_BASE_URL`；
- Claude Code 是否仍然登录了其他账号；
- Console 的自动充值和预算限制是否发生变化。

如果第三方订单显示完成，但 Console 余额没有增加，先不要重复付款。保存订单号、付款金额、充值前后余额截图和错误信息，再联系订单平台处理。

## Claude Code 充值失败的常见原因

### 把 Pro 充值当成 API 充值

Pro 或 Max 是消费者订阅，主要提供 Claude 网页、桌面端、移动端和 Claude Code 的订阅访问。API 充值则进入 Console 余额。两者的使用入口、账单和余额都不同。

### Claude Code 使用了错误的登录方式

如果设置了 `ANTHROPIC_API_KEY`，Claude Code 可能跳过 Pro 或 Max 订阅，直接按 API 计费。检查环境变量后，再重新运行 `claude login`。

### 订阅到了错误账号

如果浏览器中同时登录多个 Claude 账号，导出的 Cookie 可能对应错误账户。付款前务必确认：

- Claude 页面右上角账号；
- 订单中填写的邮箱；
- 开通后检查的账号；
- Claude Code 终端登录的账号。

如果已经开通到错误账号，不要继续提交同一订单的凭证，也不要重复付款，应先保留订单号并联系平台核查。

### 账号仍有逾期账单或有效订阅

BeWild 的问题处理页面提到，Claude 账号处于已有订阅、Overdue 账单或未处理付款失败状态时，重新提交 Cookie 可能验证失败。遇到这种情况，先检查 Claude 账户的 Billing 页面，再决定是等待当前订阅结束、处理逾期账单，还是联系客服。

### 误以为 Max 计划无限使用

Max 5x 和 Max 20x 是更高容量的订阅档位，不代表完全没有限制。Claude Code 与 Claude 网页活动共享计划用量，因此长时间运行大型任务仍可能触发限制。

## 到底应该买哪个？

可以按使用目的判断：

- **只是偶尔使用 Claude Code**：先看 Claude Pro。
- **每天使用，Pro 经常达到限制**：考虑 Max 5x。
- **Claude Code 是主要开发工具，长时间处理大型仓库**：再评估 Max 20x。
- **已经使用 API Key、脚本或服务器调用**：选择 Claude API / Console 充值。
- **只是临时超出订阅额度**：优先查看官方 Usage Credits 和 Usage Bundle。
- **不确定当前到底走订阅还是 API**：先检查 Claude Code 的登录账号和 `ANTHROPIC_API_KEY`，不要急着付款。

如果你希望通过 BeWild 查看当前可购买的 Claude 方案，可以从这个入口进入，再以登录后的商品页和结账页为准：

[👉 查看 Claude Code 相关订阅与充值方案](https://bit.ly/Bewild)

最后再强调一次：**“Claude Code 充值”不是一个单一商品名称。** Pro、Max、Usage Credits 和 Claude API 余额分别对应不同的账户体系。付款前先确认登录方式、目标账号、Workspace、套餐周期和实际金额，通常比盯着某个看起来便宜的充值入口更重要。
