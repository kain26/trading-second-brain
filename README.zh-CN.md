<div align="center">

# 🧠 Trading Second Brain｜交易第二大脑

### 把每一张图、每一笔交易、每一次错误、每一份 PDF / PPT / 手写笔记，变成可以重复调用的交易记忆。

为交易员设计的多模态 AI 知识系统。

[English](./README.md) · **简体中文** · [日本語](./README.ja.md) · [한국어](./README.ko.md)

**Fork 它，把你的交易历史喂给它，让过去的交易参与下一次决策。**

</div>

---

## 为什么做这个项目？

很多交易员其实已经有一个“第二大脑”，只是它碎了一地。

TradingView 截图躺在相册里，成交记录在券商 CSV 里，研究资料困在 PDF 里，交易想法散落在 Notion、聊天记录、X 收藏、PPT 和纸质笔记里。

每天写了复盘，第二天开盘以后却很少真正重新调用。

**Trading Second Brain 的目标，就是把这些碎片变成 AI Agent 能搜索、比较、更新和长期维护的交易记忆。**

> 重点不是保存更多信息。  
> 而是在真正需要的时候，让过去的信息重新出现。

---

## 和普通交易日志有什么区别？

| 普通交易日志 | Trading Second Brain |
|---|---|
| 记录今天发生什么 | 让今天的经验参与未来决策 |
| 主要是文字 | 文字 + 图片 + K线 + PDF + PPT + 手写 + CSV |
| 单日复盘 | 跨几十、几百笔交易寻找模式 |
| 笔记不断重复 | 优先更新已有知识文件 |
| 规则容易忘 | 每次规则修改都有原因和证据 |
| AI 只看到今天的问题 | AI 可以检索你的历史 |

---

## 核心闭环

```text
截图 / PDF / PPT / 手写笔记 / CSV / 文字
                    ↓
                  inbox/
                    ↓
                 AI 识别
                    ↓
           提取 / 分类 / 交叉验证
                    ↓
 knowledge/ strategies/ journal/ trades/
          \          |          /
               LEARNINGS.md
                    ↓
               decisions.md
                    ↓
                 MEMORY.md
                    ↓
                  AI Agent
                    ↓
                 下一交易日
```

**每做一笔交易，都应该让下一笔交易更聪明。**

---

## 原生支持多模态资料

现在的 AI 已经不只会读 Markdown。

你可以把这些资料放进系统：

- 📈 TradingView / 券商交易截图
- 🧱 GEX、Dealer Gamma、Call Wall / Put Wall 图
- 📄 PDF 论文和研究报告
- 🖥️ PPT / Slides
- ✍️ 手机拍摄的手写交易笔记
- 📊 券商导出的 CSV
- 📝 每日复盘、策略笔记

Agent 的原则是：**先提取事实，再做解释；保留原文件；最后把知识归档到正确的位置。**

---

## 项目结构

```text
trading-second-brain/
├── CLAUDE.md       # AI Agent 操作说明书
├── MEMORY.md       # 长期稳定信息 + 硬性规则
├── LEARNINGS.md    # 被重复证据支持的经验
├── decisions.md    # 为什么修改某条规则
├── knowledge/      # 市场知识
├── strategies/     # 可执行策略
├── journal/        # 每日交易复盘
├── trades/         # 结构化成交数据
├── screenshots/    # K线与交易截图
├── research/       # PDF / PPT / 研究资料原件
├── inbox/          # 尚未整理的资料
├── templates/      # 可直接复制的模板
└── prompts/        # AI 工作流 Prompt
```

---

## 5 分钟开始使用

**第一步：Fork 这个 Repo。** 把它当成你的交易操作系统。

**第二步：填写 `MEMORY.md`。** 只记录长期稳定的信息，例如主要市场、交易周期、最大日亏损、最大交易次数，以及反复出现的行为问题。不要把每天的观点都塞进 Memory。

**第三步：把所有杂乱资料先丢进 `inbox/`。** 图片、PDF、PPT、手写照片、CSV 都可以。

**第四步：运行 `prompts/inbox-triage.md`。** Agent 会执行：识别 → 提取 → 分类 → 搜索已有知识 → 更新或新建文件 → 保留原始来源。

**第五步：收盘后运行 `prompts/daily-review.md`，周末运行 `prompts/weekly-review.md`。**

---

## One Topic = One Maintainable File

不要再创建：

```text
交易笔记.md
重要笔记.md
新策略最终版.md
新策略最终版2.md
```

更推荐：

```text
knowledge/
├── dealer-gamma.md
├── gamma-flip.md
├── put-wall.md
├── call-wall.md
├── vwap.md
└── 0dte-gamma.md
```

这里真正的原则不是“疯狂拆文件”，而是：

> **一个可以独立理解、独立维护的知识单元 = 一个文件。**

---

## 信息不是直接进入 Memory

```text
原始资料
   ↓
journal / knowledge
   ↓
重复出现的证据
   ↓
LEARNINGS.md
   ↓
明确修改规则
   ↓
decisions.md
   ↓
长期稳定规则
   ↓
MEMORY.md
```

这样可以避免一次亏损、一次情绪化交易，就让 AI 帮你发明一条“永久规则”。

---

## 最重要的四个文件

### `CLAUDE.md`

AI Agent 的地图。告诉 AI 应该先读什么、去哪里寻找历史、图片/PDF/手写笔记怎么处理，以及哪些东西绝对不能猜。

### `MEMORY.md`

长期稳定的交易者信息：市场、风格、风险上限、行为弱点和真正需要长期遵守的规则。

### `LEARNINGS.md`

用真实交易反复验证出来，但仍然允许被未来证据推翻的经验。

### `decisions.md`

记录一条规则**为什么出现**。半年后你不仅知道“不能这样做”，还知道当初是什么交易、什么亏损让你制定了这条规则。

---

## 已经准备好的 AI Prompt

| Prompt | 用途 |
|---|---|
| `inbox-triage.md` | 自动整理混合资料 |
| `screenshot-analysis.md` | 识别 K 线 / 交易截图 |
| `research-extraction.md` | 提取 PDF / PPT 研究 |
| `handwritten-notes.md` | 识别手写交易笔记 |
| `daily-review.md` | 每日交易复盘 |
| `weekly-review.md` | 周度统计和模式识别 |

---

## 数据积累以后，你可以直接问 AI

- 我一天中哪个时间段最容易亏钱？
- 连续盈利两笔以后，我的下一笔交易表现怎么样？
- Positive Gamma 和 Negative Gamma 环境下，哪个策略表现最好？
- 找出所有我违反同一条止损规则的交易。
- 对比最近 30 张亏损交易截图，有没有重复出现的 Price Action？
- 哪个策略的真实 expectancy 最高？
- 我第一次制定这条规则是什么时候？为什么？
- 哪些“经验”真的有数据支持，哪些只是我自己讲的故事？

这才是这个项目最终想解决的问题。

---

## Public Repo 和真正的私人 Second Brain

推荐：

```text
Public Repo  = 操作系统 / 模板 / Prompt
Private Repo = 你真正的交易大脑
```

券商 Statement、账户号码、API Key、私人 PnL 和敏感成交数据不要上传到 Public Repo。

---

## Roadmap

- [ ] SPX / 0DTE 完整示例
- [ ] 带截图的真实 Daily Journal 示例
- [ ] Trade CSV 分析示例
- [ ] Inbox 自动分类
- [ ] 本地语义搜索 / Embeddings
- [ ] 券商数据适配
- [ ] 更多 Agent 指令
- [ ] 社区贡献模板

---

## Disclaimer

这是交易知识管理框架，不构成投资建议、金融建议或自动交易推荐。交易存在重大风险。

<div align="center">

**你的截图是数据。你的错误是数据。你的规则也是数据。**

**让它们可以被搜索，也可以被再次利用。**

</div>
