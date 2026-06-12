# 和 AI 沟通、协作、开发的常见关键词

> 修订版 v2 — 按场景分类，便于记忆和使用

---

## 1. 提示工程（Prompt Engineering）核心词

| 术语 | 说明 |
|------|------|
| **上下文**（Context） | 传入模型的所有内容：对话历史、文档、指令等。注意区分"上下文"（内容）和"上下文窗口"（容量限制） |
| **系统提示**（System Prompt / System Instruction） | 对话开始前注入的全局指令，通常用于设定角色、规则、格式 |
| **用户提示**（User Prompt） | 用户在对话中发送的输入内容 |
| **Few-shot / Zero-shot** | 少样本（提供示例）/ 零样本（不提供示例）提示方式 |
| **思维链**（Chain of Thought，CoT） | 引导模型逐步推理，提升复杂任务准确性 |
| **角色设定**（Role / Persona / You are...） | 指定模型扮演的专家身份或行为风格 |
| **输出格式**（Output Format） | 要求模型以特定结构输出，如 JSON、Markdown、Table |
| **提示层约束**（Constraints） | 在 Prompt 中施加的限制，如"不超过100字""只回答X领域问题" |
| **示例**（Examples） | Few-shot 中提供的输入/输出对，帮助模型理解期望行为 |
| **迭代优化**（Iterate / Refine） | 对 Prompt 反复调整以逼近理想输出 |

---

## 2. 生成与控制相关

| 术语 | 说明 |
|------|------|
| **生成**（Generation） | 模型基于输入逐 Token 产出文本的过程 |
| **温度**（Temperature） | 创意度控制，越高越随机。**范围因平台而异：OpenAI 0–2，Claude 0–1，Gemini 0–1** |
| **Top-p / Top-k** | 采样策略：Top-p 按累积概率截断候选词，Top-k 限制候选词数量 |
| **Max Tokens** | 单次响应的最大输出长度 |
| **Seed** | 随机种子，相同 seed + 相同输入可复现输出 |
| **流式输出**（Streaming） | 模型边生成边返回，降低首字等待时间 |
| **停止序列**（Stop Sequences） | 触发模型停止生成的字符串，如 `\n\n` 或自定义标记。注意：**不是"停止词"**（Stop Words 是 NLP 传统概念，指被过滤的高频无意义词，含义完全不同） |

---

## 3. 模型行为与对齐

| 术语 | 说明 |
|------|------|
| **对齐**（Alignment） | 使模型行为符合人类意图和价值观的技术方向 |
| **RLHF** | 基于人类反馈的强化学习（Reinforcement Learning from Human Feedback），主流对齐训练方法 |
| **幻觉**（Hallucination） | 模型生成看似合理但实为捏造的内容 |
| **一致性**（Consistency） | 同一问题在多次调用中输出结果的稳定程度 |
| **偏见**（Bias） | 训练数据中不均衡分布导致的系统性倾向 |
| **安全护栏**（Safety Guardrails） | 模型运行时的过滤机制，拦截有害输出，由平台层或模型训练层实现——区别于 Prompt 层约束（Constraints） |
| **指令遵循**（Instruction Following） | 模型准确执行用户指令的能力 |

---

## 4. 进阶协作与开发关键词

| 术语 | 说明 |
|------|------|
| **RAG**（Retrieval-Augmented Generation） | 检索增强生成：先从知识库检索相关内容，再交由模型生成，缓解幻觉、扩展知识边界 |
| **Agent / 多代理**（Agent / Multi-Agent） | 具备自主规划和工具调用能力的 AI 系统；多代理指多个 Agent 协作 |
| **工具调用**（Tool Use / Function Calling） | 模型通过结构化调用触发外部函数或 API。**注意：两者不完全等价**——Tool Use 是 Anthropic 术语，Function Calling 是 OpenAI 早期术语，各平台 schema 格式不同，跨平台开发不能直接互换 |
| **MCP**（Model Context Protocol） | Anthropic 提出的开放标准协议，规范 Agent 与外部工具/资源的交互方式，是当前 Agent 开发的重要基础设施 |
| **ReAct**（Reason + Act） | 推理与行动交替进行的 Agent 范式：思考→工具调用→观察→再思考 |
| **嵌入 / 向量**（Embedding / Vector） | 将文本映射到高维向量空间，支撑语义搜索和 RAG |
| **向量数据库**（Vector DB） | 存储和检索嵌入向量的数据库，如 ChromaDB、Pinecone、Weaviate |
| **微调**（Fine-tuning / LoRA / SFT） | 在预训练基础上用特定数据继续训练，使模型适应特定任务或风格 |
| **预训练**（Pre-training） | 在海量通用语料上训练基础模型的阶段 |
| **推理**（Inference） | 模型在生产环境中处理输入并生成输出的过程（区别于"数学推理"语境） |
| **上下文窗口**（Context Window） | 模型单次处理的最大 Token 容量，决定可传入信息的上限 |
| **结构化输出**（Structured Outputs） | 通过 JSON Schema 强制模型输出符合规范的结构，**强于仅在 Prompt 中要求输出 JSON**（后者不保证格式合法） |
| **Prefill / Assistant Prefill** | Claude 特有：预填 assistant 回复的开头内容，可强控格式和行为 |
| **Token 消耗**（Token Usage） | 输入 + 输出所消耗的 Token 数量，直接影响成本和速率限制 |
| **Prompt 注入**（Prompt Injection） | 攻击手段：通过恶意输入覆盖或绕过原始系统指令 |
| **越狱**（Jailbreak） | 通过特定 Prompt 诱导模型绕过安全限制产生违禁输出 |

---

## 5. 协作流程常用词

| 术语 | 说明 |
|------|------|
| **澄清**（Clarify） | 在执行前明确任务边界和歧义 |
| **任务拆解**（Task Decomposition） | 将复杂目标拆成可执行子步骤 |
| **逐步思考**（Step by Step） | 引导模型显式输出推理过程，提升准确性 |
| **自我验证**（Self-Check / Verification） | 要求模型检查自身输出是否符合要求 |
| **反馈回路**（Feedback Loop） | 基于输出结果持续调整输入或流程 |
| **版本迭代**（Version / Iteration） | 对 Prompt 或输出进行有记录的版本化演进 |
| **评估指标**（Evaluation / Metrics） | 衡量模型输出质量的量化标准 |
| **边缘案例**（Edge Cases） | 边界条件或异常输入，测试模型鲁棒性的关键场景 |
| **鲁棒性**（Robustness） | 模型在噪声输入、异常情况下保持稳定输出的能力 |

---

## 实用提示模板关键词（直接可用）

```
"请一步一步思考"（Think step by step）
"严格按照以下格式输出"
"基于以上上下文"
"不要幻觉/编造，不确定时说不知道"
"扮演XX专家角色"
"检查你的回答是否准确"
"使用表格/JSON输出"
"如果信息不足，请先向我澄清"
```

---

## 推荐日常使用组合

| 场景 | 推荐组合 |
|------|---------|
| **简单任务** | 角色 + 任务 + 格式 + 约束 |
| **复杂开发** | 上下文 + CoT + Tool Use + Self-Check + 迭代 |
| **代码相关** | Few-shot 示例 + 语言/版本 + 注释要求 + 测试用例 |
| **Agent 开发** | System Prompt + Tool Use schema + ReAct + MCP |
| **RAG 场景** | Embedding + Vector DB + 检索结果注入 + 来源引用约束 |

---

*修订说明：修正 Temperature 范围（平台差异）、Stop Sequences 译名（停止序列 ≠ 停止词）、Guardrails 混用问题（提示层约束 vs 安全护栏分开描述）、上下文定义精确化、补充 MCP / RLHF / Structured Outputs / Prefill，以及 Tool Use vs Function Calling 的跨平台差异说明。*
