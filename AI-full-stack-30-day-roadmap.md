# AI 全栈开发 · 30 天学习路线（前端转型版）

> 适用对象：有 JavaScript/TypeScript、React/Vue、HTTP 与构建工具经验的前端工程师。
> 建议节奏：每天 2–3 小时；若全职学习，可把每天内容压缩到半天并加深动手部分。
> 技术主线：TypeScript + Node.js + Next.js + OpenAI API + Vercel AI SDK；Python 仅在第 2 周安排半天了解，不是必修。

## 使用方法

- 每个任务前面都是复选框，完成一项就把 - [ ] 改成 - [x]，或在支持的 Markdown 预览里直接点击勾选。
- “常用资源汇总”“给前端转 AI 全栈的几条实在建议”是资料与备忘，不是任务，保留为普通列表便于随时查阅。

## 先说明三点

1. AI 全栈 = 模型能力 + 应用工程 + 数据与检索 + 评测与运维。你已有的前端工程能力是最大优势，不必从头学后端。
2. 模型名、价格、SDK 变化很快。文中链接以官方文档为准，具体模型与价格请以官网当天页面为准。
3. 每个阶段都有可运行产出，最后一周是大作业。完成比追求完美更重要。

## 环境准备（Day 0）

- [ ] Node.js 20+（建议用 nvm 或 fnm 管理版本）
- [ ] Git 与 GitHub 账号，用于保存代码与作品
- [ ] OpenAI 平台账号与 API Key，从 platform.openai.com 获取，按需小额充值
- [ ] VS Code 或 Cursor
- [ ] 可选：Docker Desktop，第 4 周部署会用到
- [ ] 可选：Python 3.11+ 与 uv，仅第 2 周半天用到

---

## 第 1 周：LLM 基础与 API 上手（Day 1–7）

### Day 1：建立 AI 全栈全局认知

目标：看懂一张 AI 应用架构图，确定自己的技术栈。

学习：
- [ ] 看 Andrej Karpathy 的视频 Introduction to Large Language Models，约 1 小时，建立“模型如何产生下一个词”的直觉。https://www.youtube.com/watch?v=zjkBMFhNj_g
- [ ] 读 OpenAI 平台文档总览，理解模型层、推理 API 层、应用层、数据与检索层。https://platform.openai.com/docs
- [ ] 浏览 Hugging Face LLM Course 第 0–1 章，了解开源模型生态。https://huggingface.co/learn/llm-course

练习：
- [ ] 画一张“一个聊天应用从用户输入到回答返回”的链路图。

产出：
- [ ] 自己的技术栈选择说明（为什么先走 TypeScript 而不是 Python）。

### Day 2：Token、上下文与模型行为

目标：理解 token 是成本与能力的基本单位。

学习：
- [ ] 用 OpenAI tokenizer 直观感受中英文分词差异。https://platform.openai.com/tokenizer
- [ ] 读 OpenAI documents 里的 models 页面，搞清楚输入 token、输出 token、上下文窗口。https://platform.openai.com/docs/models
- [ ] 快速了解 temperature、top_p、max tokens 等采样参数。

练习：
- [ ] 取 200 字中文先估计 token 数，再用 tokenizer 验证。

产出：
- [ ] 一张“token → 成本 → 上下文限制”速查笔记。

### Day 3：提示工程入门

目标：写出结构化、可复用的提示词。

学习：
- [ ] OpenAI 提示工程指南。https://platform.openai.com/docs/guides/prompt-engineering
- [ ] Anthropic 提示工程长文，补充对比视角。https://www.anthropic.com/engineering/prompt-engineering
- [ ] Google Gemini 提示词指南作为第三视角。https://ai.google.dev/gemini-api/docs/prompting-intro

练习：
- [ ] 在平台 Playground 对比零样本、少样本、思维链、角色设定 4 种写法。

产出：
- [ ] 一份含 5 个模板的提示词库（分类、摘要、改写、翻译、结构化提取）。

### Day 4：OpenAI API 初体验（Node.js）

目标：用代码调用 API，完成第一个脚本。

学习：
- [ ] OpenAI Quickstart。https://platform.openai.com/docs/quickstart
- [ ] OpenAI API Reference 的 Chat Completions 或 Responses API 章节。https://platform.openai.com/docs/api-reference
- [ ] 安装官方 JS SDK（包名 openai），读 README 与基本用法。

练习：
- [ ] 写一个 Node 脚本，读取命令行问题并输出回答；把系统提示、用户消息、温度做成参数。

产出：
- [ ] 可运行的 chat 脚本，用 .env 保存 API Key。

### Day 5：结构化输出

目标：让模型输出可靠的 JSON，而不是自由文本。

学习：
- [ ] OpenAI Structured Outputs 指南。https://platform.openai.com/docs/guides/structured-outputs
- [ ] 了解 JSON Schema 在 API 中的写法与限制。

练习：
- [ ] 做“简历解析器”，输入一段简历文本，输出 name、yearsOfExperience、skills、summary 的 JSON。

产出：
- [ ] 结构化提取脚本，并约定校验失败后的兜底逻辑（重试一次）。

### Day 6：流式输出与错误处理

目标：学会流式渲染与 API 异常处理。

学习：
- [ ] 流式输出原理：SSE（Server-Sent Events）与 API 的 stream 参数。https://platform.openai.com/docs/api-reference
- [ ] 常见错误：限流、超时、内容审核、网络重试；读 OpenAI 错误处理说明。

练习：
- [ ] 把 Day 4 脚本改成逐字流式输出；加自动重试与超时。

产出：
- [ ] 一个可流式输出的终端聊天小程序。

### Day 7：第 1 周小项目 + 复盘

小项目：
- [ ] 提示词工作台：用 Vite + React 做单页应用，左侧编辑系统提示与参数，右侧实时流式展示回答，支持保存与加载提示词模板。

复盘：
- [ ] 画出现在自己的理解图，与 Day 1 对比，记下“不懂但想知道”的问题清单。

本周产出汇总：
- [ ] 技术栈选择说明
- [ ] token 与成本速查笔记
- [ ] 提示词模板库
- [ ] 简历解析器（结构化输出）
- [ ] 终端流式聊天脚本
- [ ] 提示词工作台 Web 应用

---

## 第 2 周：RAG 与工具调用（Day 8–14）

### Day 8：Embeddings 与向量

目标：理解“把文本变成数字”的能力。

学习：
- [ ] OpenAI Embeddings 指南。https://platform.openai.com/docs/guides/embeddings
- [ ] 3Blue1Brown 神经网络系列前几集，建立向量空间直觉。https://www.3blue1brown.com/topics/neural-networks

练习：
- [ ] 写脚本把 20 条短文本转成 embedding，计算两两相似度，找出语义最接近的一对。

产出：
- [ ] 一个简单的语义相似度小工具。

### Day 9：向量检索

目标：搭建可用的检索系统。

学习：
- [ ] 了解 ANN 近似最近邻搜索的概念，比较内存实现与向量数据库（如 pgvector、Chroma）。https://github.com/pgvector/pgvector
- [ ] 读 Pinecone RAG 系列入门篇。https://www.pinecone.io/learn/series/rag/

练习：
- [ ] 把 50 条 FAQ 或公司文档切片、向量化、存进本地向量库，实现“输入问题返回最相关 3 条”。

产出：
- [ ] 可调用的 retrieveTopK 函数。

### Day 10：Function Calling / Tools

目标：让模型调用函数，连接真实世界。

学习：
- [ ] OpenAI Function calling 指南。https://platform.openai.com/docs/guides/function-calling
- [ ] 理解工具调用循环：模型返回参数 → 你执行函数 → 结果回传 → 生成最终回答。

练习：
- [ ] 实现“天气助手”，模型决定调用 getWeather(city)；未提供城市时主动反问。

产出：
- [ ] 带工具调用的脚本，能正确处理“要求补充参数”的分支。

### Day 11：RAG 全流程打通

目标：做第一个完整 RAG 应用（检索 + 引用 + 回答）。

学习：
- [ ] 把 Day 8、9 与生成结合，读 Vercel AI SDK 的 RAG 文档。https://ai-sdk.dev/docs

练习：
- [ ] 做“私有文档问答”，要求模型只依据检索片段回答，并标注来源片段。

产出：
- [ ] 可复用的 ragAnswer(question) 函数，回答附引用。

### Day 12：评测基础

目标：开始用数字而不是感觉来判断好坏。

学习：
- [ ] 理解两个常见评测：检索质量（Recall / MRR）与生成质量（忠实度、相关性）。https://platform.openai.com/docs/guides/evals
- [ ] 了解为什么“手工看几条”不够，需要固定评测集。

练习：
- [ ] 为 RAG 应用写 10–20 个问答用例并打分，记录成表。

产出：
- [ ] 一个最小评测脚本 + 10 条标注用例。

### Day 13：Python 生态半日游（选学）

目标：能读懂常见开源仓库，不要求会写。

学习：
- [ ] 速通 Python 基础语法 1–2 小时：列表、字典、类型提示、包管理。
- [ ] 浏览 Hugging Face Transformers 快速入门。https://huggingface.co/docs/transformers/index
- [ ] 浏览 OpenAI Agents SDK，理解 Python 侧智能体写法（概念即可）。https://openai.github.io/openai-agents-python/

练习：
- [ ] 在 Colab 跑一次最小示例。

产出：
- [ ] 一张 JS 生态与 Python 生态对照表。

### Day 14：第 2 周小项目 + 复盘

小项目：
- [ ] 升级提示词工作台，加入“上传文档 → 向量化 → 问答”，做一个带引用的本地 RAG 问答应用。

本周产出汇总：
- [ ] 语义相似度工具
- [ ] retrieveTopK 函数
- [ ] 带工具调用的天气助手
- [ ] RAG 问答函数（附引用）
- [ ] 最小评测集与打分脚本
- [ ] Python 生态对照表

---

## 第 3 周：智能体与全栈整合（Day 15–21）

### Day 15：Next.js + Vercel AI SDK 上手

目标：用最熟的 React 技术栈跑通 AI 接口。

学习：
- [ ] AI SDK 概览：Provider / Model / useChat / generateText。https://ai-sdk.dev/docs
- [ ] Next.js App Router 路由与 Route Handlers。https://nextjs.org/docs

练习：
- [ ] 搭最小 Next.js 项目，做一个“问一句答一句”的流式聊天页。

产出：
- [ ] 可运行的 ai-chat 项目骨架，Push 到 GitHub。

### Day 16：流式聊天 UI

目标：做好体验细节：打字机效果、停止生成、错误提示、Markdown 渲染。

学习：
- [ ] AI SDK 的 useChat 用法。https://ai-sdk.dev/docs
- [ ] 选一个 Markdown 渲染组件，处理代码高亮与表格。

练习：
- [ ] 给聊天页加停止、重新生成、复制与错误重试。

产出：
- [ ] 体验完整的聊天界面。

### Day 17：工具调用 UI 与状态管理

目标：把第 2 周的 Function Calling 搬到产品里。

学习：
- [ ] AI SDK 的 tool 定义方式与流式工具状态展示。https://ai-sdk.dev/docs

练习：
- [ ] 做“数据分析助手”，前端上传 CSV，模型根据自然语言生成统计结果（求和、均值、图表数据）。

产出：
- [ ] 能展示“模型选择了哪个工具、返回了什么结果”的界面。

### Day 18：把 RAG 集成进产品

目标：把第 2 周 RAG 能力做成可上传、可查询的产品。

学习：
- [ ] 复习服务端向量库用法；了解文件解析（PDF/Markdown）与分块策略。

练习：
- [ ] 实现“上传文档 → 异步解析向量化 → 进度提示 → 带引用问答”。

产出：
- [ ] 完整 RAG 功能模块。

### Day 19：多步智能体与记忆

目标：理解“智能体 = 模型 + 工具 + 循环 + 记忆”的模式。

学习：
- [ ] 读 AI SDK 或 OpenAI 文档中多步工具调用与会话状态的内容。https://ai-sdk.dev/docs
- [ ] 了解短期记忆（会话历史）与长期记忆（用户画像、摘要压缩）的区别。

练习：
- [ ] 做“旅行规划助手”，连续使用查天气、查攻略两个工具，并总结本轮任务状态。

产出：
- [ ] 一次会调用多个工具的智能体 Demo。

### Day 20：安全与成本

目标：把产品从“能用”推向“可上线”。

学习：
- [ ] 提示注入风险与缓解：把系统能力与用户输入隔离。
- [ ] 输出审核与内容安全策略。
- [ ] token 成本估算与用量监控。https://platform.openai.com/docs

练习：
- [ ] 给应用加“每用户/每会话”用量与限额；设计一条能挡住基础提示注入的系统提示。

产出：
- [ ] 安全与成本设计清单。

### Day 21：第 3 周小项目 + 复盘

小项目：
- [ ] 整合聊天 + 工具 + RAG，做“个人知识库助手”：上传自己的笔记文档，既能问答，也能执行“总结本周内容”“提取行动项”等工具任务。

本周产出汇总：
- [ ] Next.js + AI SDK 项目骨架
- [ ] 流式聊天界面
- [ ] 数据分析助手
- [ ] RAG 产品模块
- [ ] 多步智能体 Demo
- [ ] 安全与成本清单

---

## 第 4 周：生产化与大作业（Day 22–30）

### Day 22：可观测性

目标：看清每次调用花了多少钱、发生了什么。

学习：
- [ ] 接入可观测工具（如 Langfuse）。https://langfuse.com/
- [ ] 或先自己记录结构化日志：输入、输出、token、耗时、工具调用链。

练习：
- [ ] 给应用加日志与用量表格。

### Day 23：缓存与降本

目标：用最少成本得到稳定效果。

学习：
- [ ] 提示词缓存与语义缓存（相似问题复用旧答案）。https://platform.openai.com/docs
- [ ] 模型分级：简单任务用便宜模型、复杂任务用强模型。

练习：
- [ ] 实现简单语义缓存，命中率显示在界面上。

### Day 24：评测与回归

目标：让改动可以被验证。

学习：
- [ ] 建立固定评测集，每次改提示词或版本后自动打分。https://platform.openai.com/docs/guides/evals
- [ ] 把检索质量与生成质量分开测。

练习：
- [ ] 为大作业写 20 条评测用例，跑一遍并记录基线分数。

### Day 25：部署

目标：把应用放到公网。

学习：
- [ ] Vercel 部署 Next.js 全栈应用。https://vercel.com/docs
- [ ] 或 Docker + 自建服务器，含环境变量与密钥管理。https://docs.docker.com/

练习：
- [ ] 部署第 3 周项目，拿到公网 URL，验证生产可用。

### Day 26–29：毕业大作业

Day 26 选题与脚手架：
- [ ] 从下面三个方向选一个，定义“最小可行但完整”的范围。
- [ ] 搭好项目结构、鉴权与基本页面。

Day 27 核心功能：
- [ ] 打通主链路：数据写入 → 检索或工具 → 流式输出 → 引用与错误处理。

Day 28 打磨与边界：
- [ ] 处理空数据、超长输入、失败重试、加载状态、移动端适配。

Day 29 测试与发布：
- [ ] 跑评测、做成本预估、写 README、部署上线、提交 GitHub。

Day 30 复盘与输出：
- [ ] 写 800–1200 字项目总结：解决了什么问题、技术方案、踩过的坑、改进方向。
- [ ] 更新简历与作品集，放 Demo 链接、架构图、评测结果。
- [ ] 整理“30 天后继续学什么”清单。

### 大作业三选一（勾选你选定的一项）

- [ ] 面试准备助手：上传 JD 与个人简历，生成匹配分析、面试问题、模拟追问；带简历解析与检索。
- [ ] 智能客服知识库：企业文档问答，带引用、人工转接标记、会话统计与成本面板。
- [ ] 个人第二大脑：聚合笔记与收藏，支持问答、摘要、行动项提取与定时复盘报告。

### 完成标准（建议逐项对照）

- [ ] 主链路完整可演示
- [ ] 至少 1 个工具调用
- [ ] RAG 回答带来源引用
- [ ] 有流式体验与错误处理
- [ ] 有 20 条评测用例且能自动打分
- [ ] 已部署并有 README

---

## 常用资源汇总

官方文档：
- OpenAI Docs：https://platform.openai.com/docs
- OpenAI API Reference：https://platform.openai.com/docs/api-reference
- OpenAI 提示工程：https://platform.openai.com/docs/guides/prompt-engineering
- OpenAI 结构化输出：https://platform.openai.com/docs/guides/structured-outputs
- OpenAI Function calling：https://platform.openai.com/docs/guides/function-calling
- OpenAI Embeddings：https://platform.openai.com/docs/guides/embeddings
- OpenAI Evals：https://platform.openai.com/docs/guides/evals
- Anthropic 提示工程：https://www.anthropic.com/engineering/prompt-engineering
- Gemini API 文档：https://ai.google.dev/gemini-api/docs

框架与工具：
- Vercel AI SDK：https://ai-sdk.dev/docs
- Next.js：https://nextjs.org/docs
- LangChain JS：https://js.langchain.com/docs/
- pgvector：https://github.com/pgvector/pgvector
- Langfuse（可观测）：https://langfuse.com/
- Docker：https://docs.docker.com/
- Vercel：https://vercel.com/docs

课程与图书：
- Hugging Face LLM Course：https://huggingface.co/learn/llm-course
- DeepLearning.AI 短课程：https://www.deeplearning.ai/short-courses/
- 3Blue1Brown 神经网络系列：https://www.3blue1brown.com/topics/neural-networks
- Karpathy Introduction to Large Language Models：https://www.youtube.com/watch?v=zjkBMFhNj_g
- Pinecone RAG 系列：https://www.pinecone.io/learn/series/rag/

社区与中文资源：
- ModelScope 魔搭（国产开源模型与教程）：https://modelscope.cn/
- OpenAI 开发者论坛：https://community.openai.com/

---

## 给前端转 AI 全栈的几条实在建议

1. 不要先补数学或先啃 Python。先用 API 做出东西，遇到瓶颈再回头补理论，效率最高。
2. 你的价值 = 前端体验 + 后端数据流 + AI 能力 + 评测与成本意识。单纯会调 API 不够，能把体验和可靠性做好才是壁垒。
3. RAG 和评测是“全栈”里最容易被前端背景同学忽视、却最能拉开差距的两块，要重点投入。
4. 每个知识点都要落到可运行的代码上，别只收藏链接。
5. 从第一天就建立自己的踩坑文档，记录报错、限流、还原方法与思路。