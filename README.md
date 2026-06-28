🚀 HR-Copilot Pro: 大模型驱动的简历解析与智能决策引擎



升级说明 (V2.0)：相较于仅有 UI 的原型，本版本集成了真实的 PDF 解析链路与 LLM (大语言模型) 动态 API 交互，展示了完整的 AI 工程化落地能力。



🏗 系统架构设计 (Architecture)



本项目采用了当前主流的大模型应用落地架构：



数据清洗层：使用 PyPDF2 实时流式解析非结构化文档，提取纯文本。



Prompt 工程层：基于 System Prompt 设定极客 HR 角色，动态组装 JD 与简历特征。



大模型网关层：原生兼容 OpenAI SDK，支持一键切换 DeepSeek、Qwen（通义千问）、Zhipu 等底层算力。



前端展现层：基于 Streamlit 构建响应式交互，支持流式结果返回与容灾（Mock降级）处理。



✨ 核心工程亮点 (Engineering Highlights)



API 密钥动态注入：不硬编码 Key，支持用户在前端随时配置自有的企业级大模型接口。



优雅降级 (Graceful Degradation)：在 API 调用失败或无 Key 状态下，系统不会崩溃，而是自动切换至 Mock 演示模式，保证业务流转。



Context Window 管理：针对超长简历，在代码级实现了文本切片与 Token 长度限制，防止大模型上下文溢出报错。



🚀 快速启动指南



\# 1. 环境准备 (需 Python 3.8+)

git clone https://github.com/opn48/hr-copilot.git

cd hr-copilot



\# 2. 安装核心依赖

pip install streamlit PyPDF2 openai



\# 3. 启动引擎

streamlit run app.py





📋 Roadmap (下一代规划)



\[ ] 引入 LangChain 实现基于企业自有规范文档的 RAG（检索增强生成）。



\[ ] 接入 ChromaDB，将公司百万级历史简历向量化，支持“语义级搜人”。

