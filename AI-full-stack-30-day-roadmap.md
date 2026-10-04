# AI 全栈开发 · 30 天学习路线（前端转型版）
# AI Full-Stack Development · 30-Day Learning Roadmap (Frontend Transition Edition)

> 适用对象：有 JavaScript/TypeScript、React/Vue、HTTP 与构建工具经验的前端工程师。
> Audience: Frontend engineers with experience in JavaScript/TypeScript, React/Vue, HTTP, and build tooling.
> 建议节奏：每天 2–3 小时；若全职学习，可把每天内容压缩到半天并加深动手部分。
> Suggested pace: 2–3 hours per day. If you are studying full-time, compress each day to half a day and spend more time on hands-on work.
> 技术主线：TypeScript + Node.js + Next.js + OpenAI API + Vercel AI SDK；Python 仅在第 2 周安排半天了解，不是必修。
> Core stack: TypeScript + Node.js + Next.js + OpenAI API + Vercel AI SDK. Python is only a half-day introduction in Week 2 and is not required.

## 使用方法
## How to Use This Roadmap

- 每个任务前面都是复选框，完成一项就把 - [ ] 改成 - [x]，或在支持的 Markdown 预览里直接点击勾选。
  - Every task starts with a checkbox. Mark it as - [x] when done, or click the checkbox directly in a compatible Markdown preview.
- “常用资源汇总”“给前端转 AI 全栈的几条实在建议”是资料与备忘，不是任务，保留为普通列表便于随时查阅。
  - "Common Resources" and "Practical Advice for Frontend Engineers Transitioning to AI Full-Stack" are references and notes, not tasks. They remain plain lists for easy review.
- 本文为双语版本，中文在前、英文在后，一个复选框仍只对应一个任务，完成后勾选一次即可。
  - This is a bilingual document: Chinese comes first, followed by English. Each checkbox still represents one task and only needs to be checked once.

## 先说明三点
## Three Things to Know First

1. AI 全栈 = 模型能力 + 应用工程 + 数据与检索 + 评测与运维。你已有的前端工程能力是最大优势，不必从头学后端。
   AI full-stack = model capability + application engineering + data and retrieval + evaluation and operations. Your existing frontend engineering skills are your biggest advantage; you do not need to learn backend from scratch.
2. 模型名、价格、SDK 变化很快。文中链接以官方文档为准，具体模型与价格请以官网当天页面为准。
   Model names, pricing, and SDKs change quickly. When in doubt, prefer the official documentation linked here; check the official site for the latest models and prices.
3. 每个阶段都有可运行产出，最后一周是大作业。完成比追求完美更重要。
   Every phase produces something runnable, and the final week is a capstone project. Finishing matters more than being perfect.

## 环境准备（Day 0）
## Environment Setup (Day 0)

- [ ] Node.js 20+（建议用 nvm 或 fnm 管理版本） / Node.js 20+ (use nvm or fnm to manage versions).
- [ ] Git 与 GitHub 账号，用于保存代码与作品 / Git and a GitHub account for storing code and projects.
- [ ] OpenAI 平台账号与 API Key，从 platform.openai.com 获取，按需小额充值 / An OpenAI platform account and API Key from platform.openai.com, with a small amount of credit as needed.
- [ ] VS Code 或 Cursor / VS Code or Cursor.
- [ ] 可选：Docker Desktop，第 4 周部署会用到 / Optional: Docker Desktop, used for deployment in Week 4.
- [ ] 可选：Python 3.11+ 与 uv，仅第 2 周半天用到 / Optional: Python 3.11+ and uv, used only for half a day in Week 2.

---

## 第 1 周：LLM 基础与 API 上手（Day 1–7）
## Week 1: LLM Fundamentals and Hands-On API Work (Day 1–7)

### Day 1：建立 AI 全栈全局认知
### Day 1: Build a Big-Picture Understanding of AI Full-Stack

目标：看懂一张 AI 应用架构图，确定自己的技术栈。
Goal: Understand an AI application architecture diagram and decide on your technology stack.

学习 / Learn：
- [ ] 看 Andrej Karpathy 的视频 Introduction to Large Language Models，约 1 小时，建立“模型如何产生下一个词”的直觉。https://www.youtube.com/watch?v=zjkBMFhNj_g
  - Watch Andrej Karpathy's video "Introduction to Large Language Models" (about 1 hour) to build intuition for how models generate the next token.
- [ ] 读 OpenAI 平台文档总览，理解模型层、推理 API 层、应用层、数据与检索层。https://platform.openai.com/docs
  - Read the OpenAI platform documentation overview to understand the model layer, inference API layer, application layer, and data/retrieval layer.
- [ ] 浏览 Hugging Face LLM Course 第 0–1 章，了解开源模型生态。https://huggingface.co/learn/llm-course
  - Browse chapters 0–1 of the Hugging Face LLM Course to learn about the open-source model ecosystem.

练习 / Practice：
- [ ] 画一张“一个聊天应用从用户输入到回答返回”的链路图。
  - Draw an end-to-end flow diagram showing how a chat application goes from user input to a returned answer.

产出 / Deliverables：
- [ ] 自己的技术栈选择说明（为什么先走 TypeScript 而不是 Python）。
  - A written explanation of your chosen stack and why you are starting with TypeScript rather than Python.

### Day 2：Token、上下文与模型行为
### Day 2: Tokens, Context, and Model Behavior

目标：理解 token 是成本与能力的基本单位。
Goal: Understand that a token is the basic unit of both cost and capability.

学习 / Learn：
- [ ] 用 OpenAI tokenizer 直观感受中英文分词差异。https://platform.openai.com/tokenizer
  - Use the OpenAI tokenizer to see how tokenization differs between Chinese and English.
- [ ] 读 OpenAI documents 里的 models 页面，搞清楚输入 token、输出 token、上下文窗口。https://platform.openai.com/docs/models
  - Read the models page in the OpenAI documentation to understand input tokens, output tokens, and the context window.
- [ ] 快速了解 temperature、top_p、max tokens 等采样参数。
  - Quickly learn sampling parameters such as temperature, top_p, and max tokens.

练习 / Practice：
- [ ] 取 200 字中文先估计 token 数，再用 tokenizer 验证。
  - Take 200 Chinese characters, estimate the token count first, then verify with the tokenizer.

产出 / Deliverables：
- [ ] 一张“token → 成本 → 上下文限制”速查笔记。
  - A quick-reference note covering tokens → cost → context limits.

### Day 3：提示工程入门
### Day 3: Introduction to Prompt Engineering

目标：写出结构化、可复用的提示词。
Goal: Write structured, reusable prompts.

学习 / Learn：
- [ ] OpenAI 提示工程指南。https://platform.openai.com/docs/guides/prompt-engineering
  - Read the OpenAI prompt engineering guide.
- [ ] Anthropic 提示工程长文，补充对比视角。https://www.anthropic.com/engineering/prompt-engineering
  - Read Anthropic's prompt engineering guide for a contrasting perspective.
- [ ] Google Gemini 提示词指南作为第三视角。https://ai.google.dev/gemini-api/docs/prompting-intro
  - Review Google's Gemini prompting guide as a third perspective.

练习 / Practice：
- [ ] 在平台 Playground 对比零样本、少样本、思维链、角色设定 4 种写法。
  - In the playground, compare zero-shot, few-shot, chain-of-thought, and persona-based prompts.

产出 / Deliverables：
- [ ] 一份含 5 个模板的提示词库（分类、摘要、改写、翻译、结构化提取）。
  - A prompt library with 5 templates: classification, summarization, rewriting, translation, and structured extraction.

### Day 4：OpenAI API 初体验（Node.js）
### Day 4: First Experience with the OpenAI API (Node.js)

目标：用代码调用 API，完成第一个脚本。
Goal: Call the API from code and finish your first script.

学习 / Learn：
- [ ] OpenAI Quickstart。https://platform.openai.com/docs/quickstart
  - Follow the OpenAI Quickstart.
- [ ] OpenAI API Reference 的 Chat Completions 或 Responses API 章节。https://platform.openai.com/docs/api-reference
  - Read the Chat Completions or Responses API section of the OpenAI API Reference.
- [ ] 安装官方 JS SDK（包名 openai），读 README 与基本用法。
  - Install the official JS SDK (package name `openai`) and read its README and basic usage.

练习 / Practice：
- [ ] 写一个 Node 脚本，读取命令行问题并输出回答；把系统提示、用户消息、温度做成参数。
  - Write a Node script that reads a question from the command line and prints an answer, with system prompt, user message, and temperature as parameters.

产出 / Deliverables：
- [ ] 可运行的 chat 脚本，用 .env 保存 API Key。
  - A runnable chat script that stores the API Key in .env.

### Day 5：结构化输出
### Day 5: Structured Output

目标：让模型输出可靠的 JSON，而不是自由文本。
Goal: Make the model return reliable JSON instead of free-form text.

学习 / Learn：
- [ ] OpenAI Structured Outputs 指南。https://platform.openai.com/docs/guides/structured-outputs
  - Read the OpenAI Structured Outputs guide.
- [ ] 了解 JSON Schema 在 API 中的写法与限制。
  - Learn how JSON Schema is expressed in the API and what its limitations are.

练习 / Practice：
- [ ] 做“简历解析器”，输入一段简历文本，输出 name、yearsOfExperience、skills、summary 的 JSON。
  - Build a resume parser that takes resume text and outputs JSON with name, yearsOfExperience, skills, and summary.

产出 / Deliverables：
- [ ] 结构化提取脚本，并约定校验失败后的兜底逻辑（重试一次）。
  - A structured-extraction script with a fallback for validation failures, such as retrying once.

### Day 6：流式输出与错误处理
### Day 6: Streaming Output and Error Handling

目标：学会流式渲染与 API 异常处理。
Goal: Learn streaming rendering and API error handling.

学习 / Learn：
- [ ] 流式输出原理：SSE（Server-Sent Events）与 API 的 stream 参数。https://platform.openai.com/docs/api-reference
  - Learn how streaming works: SSE (Server-Sent Events) and the API's stream parameter.
- [ ] 常见错误：限流、超时、内容审核、网络重试；读 OpenAI 错误处理说明。
  - Learn common errors such as rate limits, timeouts, content moderation, and network retries; read the OpenAI error-handling guidance.

练习 / Practice：
- [ ] 把 Day 4 脚本改成逐字流式输出；加自动重试与超时。
  - Update the Day 4 script to stream output token by token, and add automatic retries and timeouts.

产出 / Deliverables：
- [ ] 一个可流式输出的终端聊天小程序。
  - A terminal chat micro-app that supports streaming output.

### Day 7：第 1 周小项目 + 复盘
### Day 7: Week 1 Mini Project + Retrospective

小项目 / Mini Project：
- [ ] 提示词工作台：用 Vite + React 做单页应用，左侧编辑系统提示与参数，右侧实时流式展示回答，支持保存与加载提示词模板。
  - Prompt workbench: build a Vite + React single-page app with a prompt/parameters editor on the left, real-time streaming responses on the right, and support for saving and loading prompt templates.

复盘 / Retrospective：
- [ ] 画出现在自己的理解图，与 Day 1 对比，记下“不懂但想知道”的问题清单。
  - Draw your updated mental model, compare it with Day 1, and list the questions you do not understand yet but want to answer.

本周产出汇总 / Week 1 Deliverables：
- [ ] 技术栈选择说明 / Stack-selection explanation.
- [ ] token 与成本速查笔记 / Token and cost quick-reference note.
- [ ] 提示词模板库 / Prompt template library.
- [ ] 简历解析器（结构化输出）/ Resume parser with structured output.
- [ ] 终端流式聊天脚本 / Terminal streaming chat script.
- [ ] 提示词工作台 Web 应用 / Prompt workbench web app.

---

## 第 2 周：RAG 与工具调用（Day 8–14）
## Week 2: RAG and Tool Calling (Day 8–14)

### Day 8：Embeddings 与向量
### Day 8: Embeddings and Vectors

目标：理解“把文本变成数字”的能力。
Goal: Understand the ability to "turn text into numbers."

学习 / Learn：
- [ ] OpenAI Embeddings 指南。https://platform.openai.com/docs/guides/embeddings
  - Read the OpenAI Embeddings guide.
- [ ] 3Blue1Brown 神经网络系列前几集，建立向量空间直觉。https://www.3blue1brown.com/topics/neural-networks
  - Watch the first few episodes of 3Blue1Brown's neural networks series to build intuition for vector spaces.

练习 / Practice：
- [ ] 写脚本把 20 条短文本转成 embedding，计算两两相似度，找出语义最接近的一对。
  - Write a script to embed 20 short texts, compute pairwise similarity, and find the most semantically similar pair.

产出 / Deliverables：
- [ ] 一个简单的语义相似度小工具。
  - A simple semantic-similarity utility.

### Day 9：向量检索
### Day 9: Vector Retrieval

目标：搭建可用的检索系统。
Goal: Build a usable retrieval system.

学习 / Learn：
- [ ] 了解 ANN 近似最近邻搜索的概念，比较内存实现与向量数据库（如 pgvector、Chroma）。https://github.com/pgvector/pgvector
  - Learn the ANN (approximate nearest neighbor) concept and compare in-memory implementations with vector databases such as pgvector and Chroma.
- [ ] 读 Pinecone RAG 系列入门篇。https://www.pinecone.io/learn/series/rag/
  - Read the introductory articles in Pinecone's RAG series.

练习 / Practice：
- [ ] 把 50 条 FAQ 或公司文档切片、向量化、存进本地向量库，实现“输入问题返回最相关 3 条”。
  - Chunk 50 FAQ entries or company documents, embed them, store them in a local vector database, and return the 3 most relevant items for a query.

产出 / Deliverables：
- [ ] 可调用的 retrieveTopK 函数。
  - A callable retrieveTopK function.

### Day 10：Function Calling / Tools
### Day 10: Function Calling / Tools

目标：让模型调用函数，连接真实世界。
Goal: Let the model call functions and connect to the real world.

学习 / Learn：
- [ ] OpenAI Function calling 指南。https://platform.openai.com/docs/guides/function-calling
  - Read the OpenAI Function Calling guide.
- [ ] 理解工具调用循环：模型返回参数 → 你执行函数 → 结果回传 → 生成最终回答。
  - Understand the tool-calling loop: the model returns arguments → you execute the function → results are sent back → the model generates the final answer.

练习 / Practice：
- [ ] 实现“天气助手”，模型决定调用 getWeather(city)；未提供城市时主动反问。
  - Build a weather assistant where the model decides to call getWeather(city), and asks for the city if it is missing.

产出 / Deliverables：
- [ ] 带工具调用的脚本，能正确处理“要求补充参数”的分支。
  - A script with tool calling that correctly handles the "missing required parameter" branch.

### Day 11：RAG 全流程打通
### Day 11: End-to-End RAG

目标：做第一个完整 RAG 应用（检索 + 引用 + 回答）。
Goal: Build your first complete RAG application: retrieval + citations + answer.

学习 / Learn：
- [ ] 把 Day 8、9 与生成结合，读 Vercel AI SDK 的 RAG 文档。https://ai-sdk.dev/docs
  - Combine Days 8 and 9 with generation, and read the RAG documentation in the Vercel AI SDK.

练习 / Practice：
- [ ] 做“私有文档问答”，要求模型只依据检索片段回答，并标注来源片段。
  - Build private-document Q&A that requires the model to answer only from retrieved chunks and cite source chunks.

产出 / Deliverables：
- [ ] 可复用的 ragAnswer(question) 函数，回答附引用。
  - A reusable ragAnswer(question) function whose answer includes citations.

### Day 12：评测基础
### Day 12: Evaluation Fundamentals

目标：开始用数字而不是感觉来判断好坏。
Goal: Start judging quality with numbers instead of intuition.

学习 / Learn：
- [ ] 理解两个常见评测：检索质量（Recall / MRR）与生成质量（忠实度、相关性）。https://platform.openai.com/docs/guides/evals
  - Understand two common evaluation areas: retrieval quality (Recall / MRR) and generation quality (faithfulness and relevance).
- [ ] 了解为什么“手工看几条”不够，需要固定评测集。
  - Understand why spot-checking a few examples is not enough and why a fixed evaluation set is needed.

练习 / Practice：
- [ ] 为 RAG 应用写 10–20 个问答用例并打分，记录成表。
  - Write and score 10–20 Q&A cases for the RAG app and record the results in a table.

产出 / Deliverables：
- [ ] 一个最小评测脚本 + 10 条标注用例。
  - A minimal evaluation script plus 10 labeled test cases.

### Day 13：Python 生态半日游（选学）
### Day 13: Half-Day Tour of the Python Ecosystem (Optional)

目标：能读懂常见开源仓库，不要求会写。
Goal: Be able to read common open-source repositories, without needing to write Python.

学习 / Learn：
- [ ] 速通 Python 基础语法 1–2 小时：列表、字典、类型提示、包管理。
  - Spend 1–2 hours on Python basics: lists, dictionaries, type hints, and package management.
- [ ] 浏览 Hugging Face Transformers 快速入门。https://huggingface.co/docs/transformers/index
  - Browse the Hugging Face Transformers quick start.
- [ ] 浏览 OpenAI Agents SDK，理解 Python 侧智能体写法（概念即可）。https://openai.github.io/openai-agents-python/
  - Browse the OpenAI Agents SDK to understand how agents are written in Python at a conceptual level.

练习 / Practice：
- [ ] 在 Colab 跑一次最小示例。
  - Run a minimal example in Colab.

产出 / Deliverables：
- [ ] 一张 JS 生态与 Python 生态对照表。
  - A table comparing the JS and Python ecosystems.

### Day 14：第 2 周小项目 + 复盘
### Day 14: Week 2 Mini Project + Retrospective

小项目 / Mini Project：
- [ ] 升级提示词工作台，加入“上传文档 → 向量化 → 问答”，做一个带引用的本地 RAG 问答应用。
  - Upgrade the prompt workbench by adding "upload document → embed → Q&A," turning it into a local RAG app with citations.

本周产出汇总 / Week 2 Deliverables：
- [ ] 语义相似度工具 / Semantic similarity utility.
- [ ] retrieveTopK 函数 / retrieveTopK function.
- [ ] 带工具调用的天气助手 / Weather assistant with tool calling.
- [ ] RAG 问答函数（附引用）/ RAG Q&A function with citations.
- [ ] 最小评测集与打分脚本 / Minimal evaluation set and scoring script.
- [ ] Python 生态对照表 / Python ecosystem comparison table.

---

## 第 3 周：智能体与全栈整合（Day 15–21）
## Week 3: Agents and Full-Stack Integration (Day 15–21)

### Day 15：Next.js + Vercel AI SDK 上手
### Day 15: Getting Started with Next.js + Vercel AI SDK

目标：用最熟的 React 技术栈跑通 AI 接口。
Goal: Use the React stack you know best to call an AI API end to end.

学习 / Learn：
- [ ] AI SDK 概览：Provider / Model / useChat / generateText。https://ai-sdk.dev/docs
  - Read the AI SDK overview: Provider / Model / useChat / generateText.
- [ ] Next.js App Router 路由与 Route Handlers。https://nextjs.org/docs
  - Learn Next.js App Router routing and Route Handlers.

练习 / Practice：
- [ ] 搭最小 Next.js 项目，做一个“问一句答一句”的流式聊天页。
  - Create a minimal Next.js project with a streaming chat page that answers one message at a time.

产出 / Deliverables：
- [ ] 可运行的 ai-chat 项目骨架，Push 到 GitHub。
  - A runnable ai-chat project skeleton pushed to GitHub.

### Day 16：流式聊天 UI
### Day 16: Streaming Chat UI

目标：做好体验细节：打字机效果、停止生成、错误提示、Markdown 渲染。
Goal: Polish the experience: typewriter effect, stop generation, error messages, and Markdown rendering.

学习 / Learn：
- [ ] AI SDK 的 useChat 用法。https://ai-sdk.dev/docs
  - Learn how to use useChat from the AI SDK.
- [ ] 选一个 Markdown 渲染组件，处理代码高亮与表格。
  - Choose a Markdown renderer and handle code highlighting and tables.

练习 / Practice：
- [ ] 给聊天页加停止、重新生成、复制与错误重试。
  - Add stop, regenerate, copy, and error retry to the chat page.

产出 / Deliverables：
- [ ] 体验完整的聊天界面。
  - A complete chat interface.

### Day 17：工具调用 UI 与状态管理
### Day 17: Tool-Calling UI and State Management

目标：把第 2 周的 Function Calling 搬到产品里。
Goal: Bring Week 2's Function Calling into a product UI.

学习 / Learn：
- [ ] AI SDK 的 tool 定义方式与流式工具状态展示。https://ai-sdk.dev/docs
  - Learn how the AI SDK defines tools and displays streaming tool state.

练习 / Practice：
- [ ] 做“数据分析助手”，前端上传 CSV，模型根据自然语言生成统计结果（求和、均值、图表数据）。
  - Build a "data analysis assistant" where users upload CSV files and the model generates statistics or chart data from natural-language requests, such as sums and averages.

产出 / Deliverables：
- [ ] 能展示“模型选择了哪个工具、返回了什么结果”的界面。
  - An interface that shows which tool the model chose and what it returned.

### Day 18：把 RAG 集成进产品
### Day 18: Integrating RAG into a Product

目标：把第 2 周 RAG 能力做成可上传、可查询的产品。
Goal: Turn Week 2's RAG capability into a product that supports uploads and queries.

学习 / Learn：
- [ ] 复习服务端向量库用法；了解文件解析（PDF/Markdown）与分块策略。
  - Review server-side vector database usage and learn about parsing PDFs/Markdown plus chunking strategies.

练习 / Practice：
- [ ] 实现“上传文档 → 异步解析向量化 → 进度提示 → 带引用问答”。
  - Implement "upload document → parse and embed asynchronously → progress indicators → cited Q&A."

产出 / Deliverables：
- [ ] 完整 RAG 功能模块。
  - A complete RAG feature module.

### Day 19：多步智能体与记忆
### Day 19: Multi-Step Agents and Memory

目标：理解“智能体 = 模型 + 工具 + 循环 + 记忆”的模式。
Goal: Understand the pattern "agent = model + tools + loop + memory."

学习 / Learn：
- [ ] 读 AI SDK 或 OpenAI 文档中多步工具调用与会话状态的内容。https://ai-sdk.dev/docs
  - Read about multi-step tool calling and conversation state in the AI SDK or OpenAI documentation.
- [ ] 了解短期记忆（会话历史）与长期记忆（用户画像、摘要压缩）的区别。
  - Understand the difference between short-term memory (conversation history) and long-term memory (user profiles and compressed summaries).

练习 / Practice：
- [ ] 做“旅行规划助手”，连续使用查天气、查攻略两个工具，并总结本轮任务状态。
  - Build a travel-planning assistant that calls weather and itinerary tools in sequence and summarizes the current task state.

产出 / Deliverables：
- [ ] 一次会调用多个工具的智能体 Demo。
  - An agent demo that calls multiple tools in one session.

### Day 20：安全与成本
### Day 20: Security and Cost

目标：把产品从“能用”推向“可上线”。
Goal: Move the product from "working" to "production-ready."

学习 / Learn：
- [ ] 提示注入风险与缓解：把系统能力与用户输入隔离。
  - Learn prompt-injection risks and mitigations, especially isolating system capabilities from user input.
- [ ] 输出审核与内容安全策略。
  - Learn output moderation and content-safety strategies.
- [ ] token 成本估算与用量监控。https://platform.openai.com/docs
  - Estimate token costs and monitor usage.

练习 / Practice：
- [ ] 给应用加“每用户/每会话”用量与限额；设计一条能挡住基础提示注入的系统提示。
  - Add per-user/per-session usage limits and design a system prompt that blocks basic prompt-injection attempts.

产出 / Deliverables：
- [ ] 安全与成本设计清单。
  - A security and cost design checklist.

### Day 21：第 3 周小项目 + 复盘
### Day 21: Week 3 Mini Project + Retrospective

小项目 / Mini Project：
- [ ] 整合聊天 + 工具 + RAG，做“个人知识库助手”：上传自己的笔记文档，既能问答，也能执行“总结本周内容”“提取行动项”等工具任务。
  - Combine chat, tools, and RAG to build a "personal knowledge-base assistant" that accepts uploaded notes, answers questions, and runs tool tasks such as "summarize this week" and "extract action items."

本周产出汇总 / Week 3 Deliverables：
- [ ] Next.js + AI SDK 项目骨架 / Next.js + AI SDK project skeleton.
- [ ] 流式聊天界面 / Streaming chat interface.
- [ ] 数据分析助手 / Data analysis assistant.
- [ ] RAG 产品模块 / RAG product module.
- [ ] 多步智能体 Demo / Multi-step agent demo.
- [ ] 安全与成本清单 / Security and cost checklist.

---

## 第 4 周：生产化与大作业（Day 22–30）
## Week 4: Productionization and Capstone Project (Day 22–30)

### Day 22：可观测性
### Day 22: Observability

目标：看清每次调用花了多少钱、发生了什么。
Goal: See clearly how much each call costs and what happened during it.

学习 / Learn：
- [ ] 接入可观测工具（如 Langfuse）。https://langfuse.com/
  - Integrate an observability tool such as Langfuse.
- [ ] 或先自己记录结构化日志：输入、输出、token、耗时、工具调用链。
  - Alternatively, start by writing structured logs yourself: input, output, tokens, latency, and tool-call chain.

练习 / Practice：
- [ ] 给应用加日志与用量表格。
  - Add logs and a usage table to the app.

### Day 23：缓存与降本
### Day 23: Caching and Cost Reduction

目标：用最少成本得到稳定效果。
Goal: Achieve stable results at the lowest possible cost.

学习 / Learn：
- [ ] 提示词缓存与语义缓存（相似问题复用旧答案）。https://platform.openai.com/docs
  - Learn prompt caching and semantic caching (reusing answers for similar questions).
- [ ] 模型分级：简单任务用便宜模型、复杂任务用强模型。
  - Tier your models: use cheaper models for simple tasks and stronger models for complex tasks.

练习 / Practice：
- [ ] 实现简单语义缓存，命中率显示在界面上。
  - Implement a simple semantic cache and show its hit rate in the UI.

### Day 24：评测与回归
### Day 24: Evaluation and Regression Testing

目标：让改动可以被验证。
Goal: Make changes verifiable.

学习 / Learn：
- [ ] 建立固定评测集，每次改提示词或版本后自动打分。https://platform.openai.com/docs/guides/evals
  - Create a fixed evaluation set and score automatically after every prompt or version change.
- [ ] 把检索质量与生成质量分开测。
  - Measure retrieval quality and generation quality separately.

练习 / Practice：
- [ ] 为大作业写 20 条评测用例，跑一遍并记录基线分数。
  - Write 20 evaluation cases for the capstone project, run them, and record the baseline scores.

### Day 25：部署
### Day 25: Deployment

目标：把应用放到公网。
Goal: Put the app on the public internet.

学习 / Learn：
- [ ] Vercel 部署 Next.js 全栈应用。https://vercel.com/docs
  - Deploy a Next.js full-stack app on Vercel.
- [ ] 或 Docker + 自建服务器，含环境变量与密钥管理。https://docs.docker.com/
  - Or use Docker with your own server, including environment variables and secret management.

练习 / Practice：
- [ ] 部署第 3 周项目，拿到公网 URL，验证生产可用。
  - Deploy the Week 3 project, get a public URL, and verify it works in production.

### Day 26–29：毕业大作业
### Day 26–29: Graduation Capstone Project

Day 26 选题与脚手架 / Day 26: Topic Selection and Scaffold：
- [ ] 从下面三个方向选一个，定义“最小可行但完整”的范围。
  - Choose one of the three directions below and define a "minimum viable but complete" scope.
- [ ] 搭好项目结构、鉴权与基本页面。
  - Set up the project structure, authentication, and basic pages.

Day 27 核心功能 / Day 27: Core Features：
- [ ] 打通主链路：数据写入 → 检索或工具 → 流式输出 → 引用与错误处理。
  - Build the main flow: write data → retrieve or call tools → stream output → citations and error handling.

Day 28 打磨与边界 / Day 28: Polish and Edge Cases：
- [ ] 处理空数据、超长输入、失败重试、加载状态、移动端适配。
  - Handle empty data, long inputs, failed retries, loading states, and mobile responsiveness.

Day 29 测试与发布 / Day 29: Testing and Release：
- [ ] 跑评测、做成本预估、写 README、部署上线、提交 GitHub。
  - Run evaluations, estimate costs, write a README, deploy, and push to GitHub.

Day 30 复盘与输出 / Day 30: Retrospective and Output：
- [ ] 写 800–1200 字项目总结：解决了什么问题、技术方案、踩过的坑、改进方向。
  - Write a 800–1200 word project summary covering the problem solved, technical approach, pitfalls, and improvements.
- [ ] 更新简历与作品集，放 Demo 链接、架构图、评测结果。
  - Update your resume and portfolio with Demo links, architecture diagrams, and evaluation results.
- [ ] 整理“30 天后继续学什么”清单。
  - Create a "what to learn after 30 days" list.

### 大作业三选一（勾选你选定的一项）
### Capstone Project: Choose One of Three

- [ ] 面试准备助手：上传 JD 与个人简历，生成匹配分析、面试问题、模拟追问；带简历解析与检索。 / Interview prep assistant: upload a job description and resume to get a match analysis, interview questions, and simulated follow-ups, with resume parsing and retrieval.
- [ ] 智能客服知识库：企业文档问答，带引用、人工转接标记、会话统计与成本面板。 / Smart support knowledge base: enterprise document Q&A with citations, handoff flags, conversation analytics, and a cost dashboard.
- [ ] 个人第二大脑：聚合笔记与收藏，支持问答、摘要、行动项提取与定时复盘报告。 / Personal second brain: aggregate notes and bookmarks, with Q&A, summaries, action-item extraction, and scheduled review reports.

### 完成标准（建议逐项对照）
### Completion Criteria (Review Item by Item)

- [ ] 主链路完整可演示 / The main flow is complete and demoable.
- [ ] 至少 1 个工具调用 / At least one tool call.
- [ ] RAG 回答带来源引用 / RAG answers include source citations.
- [ ] 有流式体验与错误处理 / Includes streaming UX and error handling.
- [ ] 有 20 条评测用例且能自动打分 / Has 20 evaluation cases and can score automatically.
- [ ] 已部署并有 README / Deployed and documented with a README.

---

## 常用资源汇总
## Common Resources

官方文档 / Official Documentation：
- OpenAI Docs：https://platform.openai.com/docs / OpenAI Docs
- OpenAI API Reference：https://platform.openai.com/docs/api-reference / OpenAI API Reference
- OpenAI 提示工程：https://platform.openai.com/docs/guides/prompt-engineering / OpenAI Prompt Engineering
- OpenAI 结构化输出：https://platform.openai.com/docs/guides/structured-outputs / OpenAI Structured Outputs
- OpenAI Function calling：https://platform.openai.com/docs/guides/function-calling / OpenAI Function Calling
- OpenAI Embeddings：https://platform.openai.com/docs/guides/embeddings / OpenAI Embeddings
- OpenAI Evals：https://platform.openai.com/docs/guides/evals / OpenAI Evals
- Anthropic 提示工程：https://www.anthropic.com/engineering/prompt-engineering / Anthropic Prompt Engineering
- Gemini API 文档：https://ai.google.dev/gemini-api/docs / Gemini API Documentation

框架与工具 / Frameworks and Tools：
- Vercel AI SDK：https://ai-sdk.dev/docs / Vercel AI SDK
- Next.js：https://nextjs.org/docs / Next.js
- LangChain JS：https://js.langchain.com/docs/ / LangChain JS
- pgvector：https://github.com/pgvector/pgvector / pgvector
- Langfuse（可观测）：https://langfuse.com/ / Langfuse (observability)
- Docker：https://docs.docker.com/ / Docker
- Vercel：https://vercel.com/docs / Vercel

课程与图书 / Courses and Books：
- Hugging Face LLM Course：https://huggingface.co/learn/llm-course / Hugging Face LLM Course
- DeepLearning.AI 短课程：https://www.deeplearning.ai/short-courses/ / DeepLearning.AI Short Courses
- 3Blue1Brown 神经网络系列：https://www.3blue1brown.com/topics/neural-networks / 3Blue1Brown Neural Networks Series
- Karpathy Introduction to Large Language Models：https://www.youtube.com/watch?v=zjkBMFhNj_g / Karpathy: Introduction to Large Language Models
- Pinecone RAG 系列：https://www.pinecone.io/learn/series/rag/ / Pinecone RAG Series

社区与中文资源 / Community and Chinese Resources：
- ModelScope 魔搭（国产开源模型与教程）：https://modelscope.cn/ / ModelScope (open-source models and tutorials in Chinese)
- OpenAI 开发者论坛：https://community.openai.com/ / OpenAI Developer Forum

---

## 给前端转 AI 全栈的几条实在建议
## Practical Advice for Frontend Engineers Transitioning to AI Full-Stack

1. 不要先补数学或先啃 Python。先用 API 做出东西，遇到瓶颈再回头补理论，效率最高。
   Do not start by cramming math or Python. Build something with APIs first, then return to theory when you hit a bottleneck; that is the fastest path.
2. 你的价值 = 前端体验 + 后端数据流 + AI 能力 + 评测与成本意识。单纯会调 API 不够，能把体验和可靠性做好才是壁垒。
   Your value = frontend experience + backend data flow + AI capability + evaluation and cost awareness. Knowing how to call an API is not enough; your moat is building good UX and reliability.
3. RAG 和评测是“全栈”里最容易被前端背景同学忽视、却最能拉开差距的两块，要重点投入。
   RAG and evaluation are the two parts of full-stack AI that frontend engineers most often overlook, and also where you can create the biggest advantage. Invest in them deliberately.
4. 每个知识点都要落到可运行的代码上，别只收藏链接。
   Turn every concept into runnable code; do not just bookmark links.
5. 从第一天就建立自己的踩坑文档，记录报错、限流、还原方法与思路。
   Start a troubleshooting journal on day one: record errors, rate limits, recovery steps, and your reasoning.