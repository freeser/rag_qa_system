```python
rag_qa_system/
├── config/                     # 配置管理
│   ├── __init__.py
│   ├── settings.py             # Pydantic Settings，统一配置入口
│   └── logging_config.py       # 日志配置
├── core/                       # 核心业务逻辑
    │   ├── __init__.py
    │   ├── document_loader.py      # 文档加载与解析（优化版）
    │   ├── embedding.py            # 嵌入模型加载（本地BGE）
    │   ├── vector_store.py         # 向量库操作（支持Chroma/FAISS）
    │   ├── llm_client.py           # 大模型客户端（支持Ollama/OpenAI）
    │   ├── retriever.py            # 检索模块（相似度检索+重排序）
    │   ├── memory_manager.py       # 多轮对话记忆管理
    │   ├── intent_recognizer.py    # 意图识别（规则+轻量模型）
    │   └── rag_chain.py            # 完整的RAG问答链
    ├── api/                        # FastAPI后端
    │   ├── __init__.py
    │   ├── dependencies.py         # 依赖注入（获取核心组件）
    │   ├── routes/
    │   │   ├── __init__.py
    │   │   ├── upload.py           # 文件上传API
    │   │   ├── qa.py               # 问答API
    │   │   ├── knowledge.py        # 知识库管理API
    │   │   └── system.py           # 系统状态API
    │   └── main.py                 # FastAPI应用入口
    ├── frontend/                   # Streamlit前端
    │   ├── app.py                  # Streamlit主应用
    │   ├── pages/                  # 多页面
    │   │   ├── 1_💬_问答.py
    │   │   ├── 2_📁_知识库管理.py
    │   │   └── 3_⚙️_系统设置.py
    │   └── components/             # 可复用组件
    │       ├── sidebar.py
    │       └── chat.py
    ├── data/                       # 上传文件存储（运行时生成）
    ├── vector_db/                  # 向量库持久化目录
    ├── models/                     # 本地模型存放
    │   ├── bge_reranker_base       # 重排序模型
    │   └── bge_small_zh/           # 嵌入模型
    ├── tests/                      # 单元测试
    ├── requirements.txt
    ├── .env                        # 环境变量（不提交）
    ├── run_api.py                  # API启动脚本
    ├── run_frontend.py             # Streamlit启动脚本
    └── README.md                   # 详细文档
```
