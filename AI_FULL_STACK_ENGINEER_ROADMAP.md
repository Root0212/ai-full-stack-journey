# AI 全栈工程师学习路线：从模型原理到生产级 AI 系统

> 版本：2026-08-25  
> 适用对象：已有机器学习、深度学习基础，希望重建完整知识体系并具备端到端交付能力的工程师  
> 建议周期：52 周（每周 15–25 小时）；若每周 8–12 小时，可按 18–24 个月执行

---

## 0. 先定义目标：什么是“AI 全栈”

AI 全栈不是把所有框架学一遍，而是能独立完成下面的闭环：

1. 把业务问题转化为可测量的 ML/LLM 任务；
2. 获取、清洗、版本化数据，建立可靠评测集；
3. 理解并实现核心模型，能训练、微调、诊断和比较；
4. 构建 RAG、Agent、视觉/多模态等应用；
5. 做 API、前端、异步任务、数据库和权限；
6. 优化训练与推理成本、延迟、吞吐、显存；
7. 测试、部署、监控、回滚并持续迭代；
8. 对安全、隐私、幻觉、偏差和供应链风险负责。

这条路线采用 **70% 动手 + 20% 阅读/视频 + 10% 总结**。每个阶段必须有可运行代码、实验报告和可演示系统，不能只“看完课程”。

---

## 1. 总体路线图

| 阶段 | 周数 | 核心主题 | 阶段作品 |
|---|---:|---|---|
| 0 | 1–2 | 工程与数学体检 | 可复现实验模板 |
| 1 | 3–7 | PyTorch、DL 基础重建 | 从零实现训练框架与 CNN |
| 2 | 8–13 | 现代计算机视觉 | 检测/分割服务 |
| 3 | 14–19 | NLP、Transformer、LLM 原理 | 从零小型 GPT |
| 4 | 20–25 | 微调、后训练、评测 | LoRA/SFT 模型与评测报告 |
| 5 | 26–31 | Embedding、检索、RAG | 可评测的生产型 RAG |
| 6 | 32–37 | Agent、工作流、Context/Harness Engineering | 有状态工具 Agent |
| 7 | 38–43 | AI Infra、MLOps/LLMOps | CI/CD + 监控的 AI 服务 |
| 8 | 44–48 | 推理加速、压缩、分布式 | vLLM 压测与量化对比 |
| 9 | 49–52 | 综合毕业项目、求职输出 | 生产级作品与技术文章 |

建议并行维护三条贯穿全年的支线：

- **论文线**：每两周精读 1 篇，输出一页 paper note。
- **工程线**：持续练 Git、Linux、Docker、SQL、后端、测试与云部署。
- **产品线**：每个项目先写指标、用户、失败场景，再写代码。

---

## 2. 学习纪律与验收方式

### 每周节奏

- 2 次理论学习：推导、课程、论文；
- 3 次实现：从零代码、框架实验、系统构建；
- 1 次实验复盘：记录假设、变量、结果、失败原因；
- 1 次公开输出：README、博客、演示视频或技术分享。

### 每个项目统一交付标准

- `README.md`：问题、架构、数据、启动方式、指标、局限；
- `pyproject.toml` 或锁定依赖，支持一条命令启动；
- 单元测试、集成测试，关键路径有失败测试；
- 数据/模型版本与实验追踪；
- 离线指标 + 在线系统指标（延迟、吞吐、成本）；
- Docker 镜像、API 文档、简单 UI；
- 错误分析：至少人工分析 30 个失败样例；
- 一篇设计文档和一篇复盘文档。

### “掌握”判据

对一个主题，只有同时做到以下四项才算掌握：

1. 能不用术语向别人解释；
2. 能写出最小实现；
3. 能用成熟框架做同一任务并解释差异；
4. 能用数据定位失败、性能或成本问题。

---

## 3. 分阶段详细任务

## 阶段 0（第 1–2 周）：工程与基础体检

### 理论清单

- 线性代数：矩阵乘法、特征值/SVD、范数；
- 概率统计：MLE/MAP、交叉熵、KL、置信区间、假设检验；
- 优化：SGD/AdamW、学习率、正则化、数值稳定性；
- Python、NumPy、PyTorch autograd；
- Linux shell、Git、HTTP、SQL、Docker、基本并发。

### 必做任务

- 用 NumPy 实现线性回归、softmax 回归、两层 MLP 和反向传播；
- 用 PyTorch 重写，并做梯度检查；
- 建一个统一项目模板：配置、日志、测试、lint、Docker、CI；
- 用 FastAPI 暴露推理接口，用简单网页或 Gradio 做 UI；
- 对一次训练记录 seed、数据版本、环境、指标与模型文件。

### 推荐资料

- [李沐《动手学深度学习》中文站](https://zh.d2l.ai/) / [B 站课程](https://space.bilibili.com/1567748478/channel/seriesdetail?sid=358497)
- [PyTorch 官方 Tutorials](https://pytorch.org/tutorials/)
- [MIT Missing Semester](https://missing.csail.mit.edu/)
- [Full Stack Python](https://www.fullstackpython.com/)
- [FastAPI 官方教程](https://fastapi.tiangolo.com/tutorial/)
- [Docker Get Started](https://docs.docker.com/get-started/)

**通过标准**：在全新环境中 15 分钟内复现训练与服务；能解释梯度、过拟合、数据泄漏和训练/验证/测试划分。

---

## 阶段 1（第 3–7 周）：深度学习基础重建

### 理论清单

- 初始化、归一化、残差连接、dropout；
- CNN、RNN/LSTM、Attention；
- 优化与调参、损失函数、类别不平衡；
- mixed precision、profiling、可复现性。

### 必做任务

1. 从零实现 `Linear`、`Conv2d`、BatchNorm、LayerNorm、Attention；
2. 在 CIFAR-10 上训练 CNN/ResNet，做至少 8 组消融；
3. 用 profiler 找到数据加载与 GPU 瓶颈；
4. 对错误样本按类别、置信度和数据质量分桶；
5. 写一份“为什么这个模型有效/失败”的实验报告。

### 主资料

- [fast.ai Practical Deep Learning for Coders](https://course.fast.ai/)
- [Dive into Deep Learning](https://d2l.ai/)
- [Deep Learning（Goodfellow 等，在线版）](https://www.deeplearningbook.org/)
- [Andrej Karpathy: Neural Networks Zero to Hero（YouTube）](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ)

> 取舍：你已有 DL 基础，不必逐页重学教材；以“能从零实现 + 能诊断训练”为目标查漏补缺。

---

## 阶段 2（第 8–13 周）：现代计算机视觉

### 理论清单

- 分类、检测、语义/实例分割、关键点；
- ResNet、ViT、DETR；
- 数据增强、迁移学习、自监督学习；
- CLIP、视觉语言模型、扩散模型概念；
- mAP、IoU、Dice、校准与长尾评测。

### 必做项目：工业视觉质检服务

- 自建或选一个真实小数据集；
- 完成数据标注、质量检查、增强与版本管理；
- 比较 CNN 与 ViT 迁移学习；
- 至少完成检测或分割之一；
- 导出 ONNX，比较 PyTorch/ONNX Runtime 延迟；
- 提供批量上传、可视化结果、错误样本回流页面。

### 主资料

- [Stanford CS231n 官方课程笔记](https://cs231n.github.io/)（基础扎实，仍是首选）
- [Stanford CS231n 2025 课程主页/课件](https://cs231n.stanford.edu/2025/)
- [Hugging Face Community Computer Vision Course](https://huggingface.co/learn/computer-vision-course/unit0/welcome/welcome)
- [PyTorch Vision Tutorials](https://pytorch.org/tutorials/intermediate/torchvision_tutorial.html)
- [Ultralytics YOLO Docs](https://docs.ultralytics.com/)（工程入门；不要用它替代检测原理）
- [OpenMMLab MMDetection](https://github.com/open-mmlab/mmdetection) / [MMSegmentation](https://github.com/open-mmlab/mmsegmentation)
- [Hugging Face Diffusion Course](https://huggingface.co/learn/diffusion-course/unit0/1)

**通过标准**：能解释 IoU/mAP、anchor 与 DETR 的差异；能定位问题来自数据、阈值、模型还是部署预处理。

---

## 阶段 3（第 14–19 周）：NLP、Transformer 与 LLM 原理

### 理论清单

- 经典 NLP：分词、TF-IDF、word2vec、序列标注、检索；
- BPE/Unigram tokenizer；
- Transformer、位置编码、RoPE、MHA/GQA/MQA；
- decoder-only LM、预训练目标、scaling law；
- MoE、长上下文、生成策略与 KV cache；
- 训练数据清洗、去重、污染与基础评测。

### 必做任务

1. 从零写 BPE tokenizer；
2. 只用 PyTorch 基础模块实现 decoder-only Transformer；
3. 在小语料训练 10M–100M 参数语言模型；
4. 实现 greedy、top-k、top-p、temperature、KV cache；
5. 画训练曲线并分析算力、显存、参数量和 token 数；
6. 复现 Stanford CS336 Assignment 1 的核心部分。

### 主资料（按顺序）

- [Stanford CS224N](https://web.stanford.edu/class/cs224n/)：NLP 与深度学习体系
- [Hugging Face LLM Course](https://huggingface.co/learn/llm-course/chapter1/1)：生态与任务实战
- [Karpathy: Let's build GPT](https://www.youtube.com/watch?v=kCc8FmEb1nY) / [nanoGPT](https://github.com/karpathy/nanoGPT)
- [Stanford CS336: Language Modeling from Scratch](https://cs336.stanford.edu/) / [官方 GitHub](https://github.com/stanford-cs336)
- [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)
- [The Annotated Transformer](https://nlp.seas.harvard.edu/annotated-transformer/)
- [《Speech and Language Processing》在线草稿](https://web.stanford.edu/~jurafsky/slp3/)

**通过标准**：能从张量形状推导 attention；能估算参数、FLOPs、训练显存和 KV cache；能解释预训练与推理的不同瓶颈。

---

## 阶段 4（第 20–25 周）：微调、后训练与评测

### 理论清单

- instruction tuning、SFT、PEFT/LoRA/QLoRA；
- preference learning：RLHF、DPO 及其边界；
- reward model、数据配比、灾难性遗忘；
- benchmark、LLM-as-judge、人工评测、污染与置信区间；
- 结构化输出、tool calling、prompt/context engineering。

### 必做项目：领域模型后训练

- 选择一个有明确评测的领域任务；
- 构造/清洗 instruction 数据，划分不可泄漏的 golden set；
- 比较 zero-shot、few-shot、RAG、LoRA/SFT；
- 用 TRL/PEFT 完成 LoRA，记录吞吐、显存和成本；
- 建自动评测 + 双盲人工评测，报告置信区间；
- 写 model card、data card、安全边界与回滚方案。

### 主资料

- [Hugging Face LLM Course](https://huggingface.co/learn/llm-course/chapter11/1)
- [Hugging Face smol-course（后训练）](https://huggingface.co/learn/smol-course/unit0/1)
- [Transformers](https://github.com/huggingface/transformers)、[PEFT](https://github.com/huggingface/peft)、[TRL](https://github.com/huggingface/trl)
- [LoRA 论文](https://arxiv.org/abs/2106.09685)、[QLoRA 论文](https://arxiv.org/abs/2305.14314)、[DPO 论文](https://arxiv.org/abs/2305.18290)
- [EleutherAI LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness)
- [OpenAI Evals](https://github.com/openai/evals)

### Prompt、Context 与 Harness Engineering 的正确位置

- **Prompt engineering**：指令、示例、输出 schema、约束与失败恢复；
- **Context engineering**：决定给模型哪些信息、何时给、如何压缩/排序/缓存；
- **Harness engineering**：围绕模型构建工具、状态、验证器、测试、权限、重试、观测与反馈闭环。

不要把它们当三个证书方向；在后续 RAG/Agent 项目中用成功率、延迟、成本和安全性证明能力。

---

## 阶段 5（第 26–31 周）：Embedding、检索与生产型 RAG

### 理论清单

- 倒排索引、BM25、dense retrieval、ANN、HNSW；
- embedding、bi-encoder、cross-encoder/reranker；
- chunking、metadata、hybrid search、query rewriting；
- RAG 的 faithfulness、context precision/recall、answer relevance；
- 引用、权限过滤、增量索引、缓存、prompt injection。

### 必做项目：可评测知识库 RAG

1. 解析 PDF/HTML/Markdown，保留页码与来源；
2. 建 BM25、dense、hybrid 三套 baseline；
3. 加 reranker，系统比较 chunk 大小、top-k 与查询改写；
4. 构建 100 条以上问题与证据标注的 golden set；
5. 分开评测 retrieval 与 generation，不能只看最终回答；
6. 实现引用、拒答、租户权限、增量更新与注入防护；
7. 展示 p50/p95 延迟、每问成本和错误类型。

### 主资料

- [Stanford Introduction to Information Retrieval（免费在线书）](https://nlp.stanford.edu/IR-book/)
- [Sentence Transformers 文档](https://sbert.net/)
- [FAISS](https://github.com/facebookresearch/faiss)
- [Elasticsearch Search Labs：RAG](https://www.elastic.co/search-labs/blog/articles/retrieval-augmented-generation-rag)
- [LlamaIndex 官方文档](https://docs.llamaindex.ai/)
- [RAG 原始论文](https://arxiv.org/abs/2005.11401)
- [RAGAS](https://github.com/explodinggradients/ragas)（评测工具，不应代替人工 golden set）

**通过标准**：看到答案错误时，能判断是解析、召回、排序、上下文、生成还是评测问题。

---

## 阶段 6（第 32–37 周）：Agent、工作流与可靠性

### 理论清单

- tool use、ReAct、planning、reflection 的适用边界；
- deterministic workflow 与 autonomous agent 的取舍；
- 状态机、短期/长期记忆、checkpoint、human-in-the-loop；
- MCP/工具协议概念、schema、幂等、权限、sandbox；
- agent eval：任务成功率、步骤数、工具错误、成本、轨迹评测；
- prompt injection、数据外泄、越权与不可逆操作审批。

### 学习顺序

1. 先不用框架，用 Python 写 tool loop、状态和停止条件；
2. 再用 LangChain 学组件接口；
3. 用 LangGraph 实现有状态、可恢复工作流；
4. 最后比较 smolagents/LlamaIndex Agents 等，不追框架数量。

### 必做项目：研究/工单处理 Agent

- 至少 4 个工具，其中一个是有副作用工具的安全模拟器；
- schema 校验、超时、重试、幂等键、权限和审批；
- checkpoint、断点恢复、流式输出、人工介入；
- 建 50–100 个任务评测集，比较纯 prompt、workflow、agent；
- trace 每一步，统计成功率、步骤、延迟、token、成本；
- 做 prompt injection 与越权红队测试。

### 主资料

- [Hugging Face Agents Course](https://huggingface.co/learn/agents-course/unit0/introduction)
- [LangChain Academy: Introduction to LangGraph](https://academy.langchain.com/courses/intro-to-langgraph)
- [LangGraph 官方文档](https://docs.langchain.com/oss/python/langgraph/overview)
- [LangChain 官方文档](https://docs.langchain.com/oss/python/langchain/overview)
- [LangGraph GitHub](https://github.com/langchain-ai/langgraph)
- [ReAct 论文](https://arxiv.org/abs/2210.03629)
- [Anthropic: Building Effective Agents](https://www.anthropic.com/research/building-effective-agents)
- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/)

> 框架迭代很快。永远以当前官方文档为准，并把业务逻辑放在独立函数中，避免被某个框架锁死。

---

## 阶段 7（第 38–43 周）：AI Infra、MLOps 与 LLMOps

### 理论清单

- 数据、特征、模型、prompt 与评测集版本化；
- experiment tracking、model registry、pipeline orchestration；
- batch/online/streaming inference；
- CI/CD/CT、canary、shadow、A/B、rollback；
- observability：logs、metrics、traces、data/model drift；
- Kubernetes 基础、GPU 调度、队列、autoscaling；
- SLO、容量规划、单位经济成本、安全与隐私。

### 必做项目：完整 AI 平台最小闭环

- 数据处理 → 训练/微调 → 评测 → 注册 → 部署 pipeline；
- MLflow 记录实验与模型；DVC 或对象存储管理数据版本；
- FastAPI + worker queue + PostgreSQL/Redis；
- GitHub Actions 跑测试、镜像构建和部署；
- Prometheus/Grafana 或 OpenTelemetry 做指标与 trace；
- 演练坏模型回滚、依赖失败、流量突增与数据漂移。

### 主资料

- [Full Stack Deep Learning](https://fullstackdeeplearning.com/course/)
- [Full Stack LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/)
- [Made With ML](https://madewithml.com/)
- [MLOps Zoomcamp](https://github.com/DataTalksClub/mlops-zoomcamp)
- [Designing Machine Learning Systems（Chip Huyen）资料页](https://huyenchip.com/book/)
- [MLflow Docs](https://mlflow.org/docs/latest/)、[DVC Docs](https://dvc.org/doc)
- [Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [OpenTelemetry Docs](https://opentelemetry.io/docs/)

**通过标准**：一次部署失败时能快速定位代码、模型、数据、依赖或基础设施；能回答系统的 SLO 与每 1,000 次请求成本。

---

## 阶段 8（第 44–48 周）：推理加速、模型压缩与分布式

### 理论清单

- GPU 架构、memory hierarchy、roofline、算术强度；
- batching、continuous batching、KV cache、PagedAttention；
- FlashAttention、speculative decoding、prefix caching；
- FP16/BF16/FP8/INT8/INT4，PTQ/QAT；
- pruning、distillation、low-rank；
- data/tensor/pipeline/context parallel，ZeRO/FSDP；
- Triton kernel 基础，profiling 与 benchmark 方法。

### 必做项目：同一模型的服务与压缩实验

- 用 Transformers 建 baseline，再用 vLLM 服务；
- 比较不同 batch、并发、输入/输出长度的 TTFT、TPOT、吞吐；
- 比较 BF16、8-bit、4-bit 的显存、速度与任务质量；
- 用 Nsight/PyTorch Profiler 找瓶颈；
- 至少写一个简单 Triton kernel，并验证正确性/性能；
- 输出可复现 benchmark，包含硬件、软件版本与 warm-up 方法。

### 主资料

- [Stanford CS336](https://cs336.stanford.edu/)（Systems 作业尤其重要）
- [MIT 6.S965 TinyML and Efficient Deep Learning](https://hanlab.mit.edu/courses/2023-fall-65940)
- [EfficientML.ai 课程资料](https://efficientml.ai/)
- [vLLM Docs](https://docs.vllm.ai/) / [vLLM GitHub](https://github.com/vllm-project/vllm)
- [llama.cpp](https://github.com/ggml-org/llama.cpp)
- [NVIDIA TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM)
- [DeepSpeed Tutorials](https://www.deepspeed.ai/tutorials/)、[PyTorch FSDP](https://pytorch.org/tutorials/intermediate/FSDP_tutorial.html)
- [Triton Tutorials](https://triton-lang.org/main/getting-started/tutorials/index.html)
- [CUDA Programming Guide](https://docs.nvidia.com/cuda/cuda-c-programming-guide/)
- [FlashAttention 论文与代码](https://github.com/Dao-AILab/flash-attention)

**通过标准**：区分 latency/throughput、prefill/decode、compute-bound/memory-bound；任何“加速 X 倍”都能说明基线、硬件、负载和质量代价。

---

## 阶段 9（第 49–52 周）：毕业项目与作品集

### 推荐毕业项目（任选一项，做到生产级）

#### A. 多模态企业知识助手

PDF/表格/图片解析，hybrid RAG，图表问答，带引用、权限、评测、反馈学习和监控。

#### B. AI 软件工程 Agent

代码检索、计划、沙箱执行、测试、patch review、checkpoint、审批和轨迹评测；重点展示 harness engineering。

#### C. 边缘视觉系统

训练检测/分割模型，蒸馏/量化，部署到边缘设备，提供云端管理、数据回流和漂移监控。

### 毕业验收

- 公开 GitHub 仓库（敏感凭据和数据除外）；
- 5–10 分钟演示视频；
- 架构图、ADR（架构决策记录）、威胁模型；
- 评测集、实验表、错误分析、负载测试；
- 云端可访问 demo 或一条命令本地启动；
- 3 篇文章：模型原理、系统设计、失败复盘；
- 20 分钟技术答辩：为什么这样设计、替代方案和成本。

---

## 4. 52 周逐周任务清单

| 周 | 任务 | 可验收输出 |
|---:|---|---|
| 1 | 数学/Python/PyTorch 体检 | NumPy MLP + 梯度检查 |
| 2 | Git、测试、Docker、API | 项目模板 + CI + API |
| 3 | 训练循环、优化器、初始化 | 可复现实验 |
| 4 | CNN 与卷积实现 | CIFAR baseline |
| 5 | ResNet、归一化、正则化 | 消融表 |
| 6 | Attention/RNN 基础 | 最小实现与单测 |
| 7 | profiling 与错误分析 | 性能/错误报告 |
| 8 | CV 数据与迁移学习 | 数据卡 + baseline |
| 9 | 检测原理与实现 | detector baseline |
| 10 | 分割与指标 | segmentation baseline |
| 11 | ViT/DETR/CLIP | 模型比较 |
| 12 | ONNX 与服务化 | 推理 API |
| 13 | CV 项目完善 | demo + 报告 |
| 14 | 经典 NLP 与 tokenizer | BPE 实现 |
| 15 | Transformer 数学与代码 | attention 单测 |
| 16 | decoder-only GPT | 前向/反向通过 |
| 17 | 小模型训练 | loss 曲线与样例 |
| 18 | KV cache 与生成 | 生成性能对比 |
| 19 | CS336 核心作业 | mini-GPT 报告 |
| 20 | HF 生态与数据处理 | 标准训练 pipeline |
| 21 | LoRA/QLoRA | 微调模型 |
| 22 | SFT 数据工程 | data card |
| 23 | DPO/RLHF 原理与小实验 | 对比实验 |
| 24 | LLM 评测 | golden set + harness |
| 25 | 领域后训练项目 | model card + demo |
| 26 | BM25、embedding、ANN | 检索 baseline |
| 27 | chunk/index pipeline | 可增量索引 |
| 28 | hybrid + reranker | retrieval 消融 |
| 29 | RAG generation/citation | 引用回答 API |
| 30 | RAG 评测与红队 | 评测/安全报告 |
| 31 | RAG 项目完善 | 完整 demo |
| 32 | 原生 tool loop | 无框架 Agent |
| 33 | ReAct、状态与记忆 | trace + 测试 |
| 34 | LangChain 组件 | 小型 workflow |
| 35 | LangGraph/checkpoint/HITL | 可恢复 Agent |
| 36 | Agent eval 与安全 | 任务集 + 红队 |
| 37 | Agent 项目完善 | demo + 轨迹报告 |
| 38 | MLflow/DVC | 实验与数据版本 |
| 39 | pipeline/registry | 训练部署流水线 |
| 40 | Docker/K8s/队列 | 异步服务 |
| 41 | CI/CD、canary、rollback | 发布演练 |
| 42 | metrics/logs/traces | dashboard |
| 43 | 故障与成本演练 | postmortem |
| 44 | GPU/roofline/profiler | 瓶颈报告 |
| 45 | vLLM/PagedAttention | 服务压测 |
| 46 | 量化/蒸馏/剪枝 | 质量性能表 |
| 47 | 分布式/FSDP/DeepSpeed | 扩展实验 |
| 48 | Triton/FlashAttention | kernel benchmark |
| 49 | 毕业项目设计 | PRD + ADR + threat model |
| 50 | 核心系统实现 | end-to-end alpha |
| 51 | 评测、压测、安全 | 完整报告 |
| 52 | 发布、演示、答辩 | GitHub + 视频 + 文章 |

---

## 5. 中文/B 站与 GitHub 补充资源

### 中文资源

- [李沐 B 站主页](https://space.bilibili.com/1567748478)：论文精读、动手学深度学习；讲解严谨，适合建立原理。
- [Datawhale](https://github.com/datawhalechina)：开源学习资料集合；按具体项目质量选择，不必全部追。
- [Datawhale self-llm](https://github.com/datawhalechina/self-llm)：开源大模型微调与部署实践。
- [InternLM Tutorial](https://github.com/InternLM/Tutorial)：中文大模型、微调、部署、Agent 实战。
- [OpenMMLab](https://github.com/open-mmlab)：CV 工程生态与模型库。
- [Happy-LLM](https://github.com/datawhalechina/happy-llm)：中文 LLM 原理与实践导读。

### 值得长期阅读的 GitHub

- 模型原理：[nanoGPT](https://github.com/karpathy/nanoGPT)、[minGPT](https://github.com/karpathy/minGPT)
- LLM from scratch：[LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch)
- 训练生态：[Transformers](https://github.com/huggingface/transformers)、[Accelerate](https://github.com/huggingface/accelerate)
- Agent：[smolagents](https://github.com/huggingface/smolagents)、[LangGraph](https://github.com/langchain-ai/langgraph)
- Serving：[vLLM](https://github.com/vllm-project/vllm)、[llama.cpp](https://github.com/ggml-org/llama.cpp)
- 分布式：[DeepSpeed](https://github.com/deepspeedai/DeepSpeed)、[Megatron-LM](https://github.com/NVIDIA/Megatron-LM)
- 评测：[lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness)、[RAGAS](https://github.com/explodinggradients/ragas)
- AI 工程：[Made With ML](https://github.com/GokuMohandas/Made-With-ML)

---

## 6. 论文阅读主干（不要一次全读）

按项目进度阅读，每篇回答：解决什么问题、关键假设、方法、实验是否支持结论、如何复现、何时会失败。

1. ResNet — [Deep Residual Learning](https://arxiv.org/abs/1512.03385)
2. ViT — [An Image is Worth 16x16 Words](https://arxiv.org/abs/2010.11929)
3. CLIP — [Learning Transferable Visual Models](https://arxiv.org/abs/2103.00020)
4. Transformer — [Attention Is All You Need](https://arxiv.org/abs/1706.03762)
5. BERT — [Pre-training of Deep Bidirectional Transformers](https://arxiv.org/abs/1810.04805)
6. GPT-3 — [Language Models are Few-Shot Learners](https://arxiv.org/abs/2005.14165)
7. Scaling Laws — [Scaling Laws for Neural Language Models](https://arxiv.org/abs/2001.08361)
8. Chinchilla — [Training Compute-Optimal LLMs](https://arxiv.org/abs/2203.15556)
9. LoRA / QLoRA / DPO（见阶段 4）
10. RAG（见阶段 5）
11. ReAct（见阶段 6）
12. FlashAttention — [Fast and Memory-Efficient Exact Attention](https://arxiv.org/abs/2205.14135)
13. vLLM — [Efficient Memory Management with PagedAttention](https://arxiv.org/abs/2309.06180)

---

## 7. 工具栈建议：学概念，不囤框架

| 层 | 第一选择 | 第二选择/用于比较 |
|---|---|---|
| 训练 | PyTorch | JAX（选修） |
| 模型生态 | Hugging Face Transformers | 原生 PyTorch 实现 |
| CV | torchvision / OpenMMLab | Ultralytics |
| 微调 | PEFT + TRL | Axolotl/Unsloth（按需） |
| 检索 | FAISS + PostgreSQL/pgvector | Elasticsearch/Milvus |
| RAG | 先手写 pipeline | LlamaIndex/LangChain |
| Agent | 先手写 tool loop | LangGraph/smolagents |
| API/UI | FastAPI + React/Next.js | Gradio/Streamlit 用于原型 |
| 实验 | MLflow | Weights & Biases |
| 数据版本 | DVC/对象存储 | lakeFS |
| 服务 | vLLM | llama.cpp/TensorRT-LLM |
| 运维 | Docker + Kubernetes | 云厂商托管服务 |
| 观测 | OpenTelemetry + Prometheus/Grafana | LangSmith 等专用平台 |

核心原则：每引入一个框架，都要能回答它替你处理了什么、隐藏了什么、失败时如何绕过。

---

## 8. 全面扩展路线（原“选修分支”）

这些方向并非不需要学习。“选修”的意思是：它们不是成为通用 AI 全栈工程师的共同前置依赖，应在主线建立模型、评测、服务和基础设施能力之后学习，避免六条线同时开工却没有一条形成作品。

### 推荐时间安排

- 主线第 1–31 周完成后，可在不影响主线的情况下开始第一个分支；
- 主线 52 周结束后，用 **24–32 周** 完成下面六个分支；
- 推荐顺序：多模态与生成视觉 → 语音 → 推荐系统 → 图机器学习 → 强化学习 → 边缘 AI；
- 每个分支采用“1 周理论 + 1 周实现 + 1 周项目”的最小闭环；重点分支延长到 4–6 周；
- 所有分支都学，但只选 1–2 个做到求职级深度，其余做到能正确选型、实现 baseline 和评测。

| 扩展阶段 | 周数 | 主题 | 最低交付物 |
|---|---:|---|---|
| E1 | 4–5 | 多模态与生成视觉 | 图文检索/VQA + 可控生成 |
| E2 | 3–4 | 语音与音频 AI | 流式 ASR + 语音 RAG |
| E3 | 4–5 | 推荐与搜索系统 | 两阶段推荐服务 |
| E4 | 3–4 | 图机器学习 | GNN 节点/图任务 + Graph RAG 对比 |
| E5 | 4–5 | 强化学习 | DQN/PPO 从零实现 + 环境项目 |
| E6 | 4–5 | 边缘 AI | 量化模型部署到真实/模拟边缘端 |
| E7 | 2–4 | 可靠、因果与负责任 AI | 校准/漂移/公平性审计报告 |

### E1（4–5 周）：多模态与生成视觉

#### 知识清单

- ViT、视觉 tokenizer、CLIP 对比学习与跨模态对齐；
- image-text encoder、VLM projector、cross-attention；
- BLIP-2、LLaVA 类视觉指令模型；
- VAE、DDPM、score matching、classifier-free guidance；
- latent diffusion、DiT、ControlNet；
- 图文检索、caption、VQA 与生成质量评测。

#### 路线与任务

1. 第 1 周：实现 ViT patch embedding 和 CLIP-style contrastive loss；
2. 第 2 周：用预训练 CLIP 做 zero-shot 分类和图文检索，分析失败样例；
3. 第 3 周：拆解一个 LLaVA 类 VLM，完成图像问答或领域 LoRA；
4. 第 4 周：从零实现小型 DDPM，并用 Diffusers 做 ControlNet/LoRA 实验；
5. 第 5 周：组合成带引用的多模态文档助手，评测 OCR、图表和普通图片三类问题。

#### 推荐资源

- [Stanford CS231n](https://cs231n.github.io/)：视觉主干与现代视觉架构；
- [Hugging Face Community Computer Vision Course](https://huggingface.co/learn/computer-vision-course/unit0/welcome/welcome)；
- [Hugging Face Diffusion Course](https://huggingface.co/learn/diffusion-course/unit0/1)；
- [UvA Deep Learning Tutorials](https://uvadlc-notebooks.readthedocs.io/en/latest/)：ViT、对比学习等可运行教程；
- [Umar Jamil: Stable Diffusion from Scratch](https://www.youtube.com/watch?v=ZBKpAp_6TGI)；
- [LLaVA GitHub](https://github.com/haotian-liu/LLaVA)、[OpenCLIP](https://github.com/mlfoundations/open_clip)、[Diffusers](https://github.com/huggingface/diffusers)；
- 论文：[CLIP](https://arxiv.org/abs/2103.00020)、[BLIP-2](https://arxiv.org/abs/2301.12597)、[LLaVA](https://arxiv.org/abs/2304.08485)、[DDPM](https://arxiv.org/abs/2006.11239)、[Latent Diffusion](https://arxiv.org/abs/2112.10752)、[DiT](https://arxiv.org/abs/2212.09748)。

**验收**：能解释“视觉编码器—projector—LLM”的数据流；图文检索有 Recall@K，VQA 有分类错误分析，生成实验有固定 prompt/seed 和质量—速度比较。

### E2（3–4 周）：语音与音频 AI

#### 知识清单

- waveform、采样率、STFT、Mel spectrogram；
- CTC、RNN-T、encoder-decoder ASR；
- wav2vec 2.0、自监督语音表示、Whisper；
- speaker recognition、audio classification、TTS 基础；
- 流式识别的 VAD、chunk、延迟与 WER/CER。

#### 路线与任务

1. 第 1 周：音频信号处理，训练关键词识别 classifier；
2. 第 2 周：用 Wav2Vec2/Whisper 完成 ASR，按噪声、口音、长度分析 CER/WER；
3. 第 3 周：实现 VAD + 流式分块 + ASR + 标点恢复；
4. 第 4 周：构建会议助手：转写、speaker diarization、摘要、可追溯语音 RAG。

#### 推荐资源

- [Hugging Face Audio Course](https://huggingface.co/learn/audio-course/chapter0/introduction)；
- [Stanford CS224S: Spoken Language Processing](https://web.stanford.edu/class/cs224s/)；
- [SpeechBrain Tutorials](https://speechbrain.readthedocs.io/en/latest/tutorials.html)；
- [torchaudio Tutorials](https://pytorch.org/audio/stable/tutorials.html)；
- [Whisper GitHub](https://github.com/openai/whisper)、[pyannote-audio](https://github.com/pyannote/pyannote-audio)；
- 论文：[wav2vec 2.0](https://arxiv.org/abs/2006.11477)、[Whisper](https://arxiv.org/abs/2212.04356)。

**验收**：报告 CER/WER、real-time factor、端到端 p95 延迟；能区分声学错误、语言错误、切分错误和说话人分离错误。

### E3（4–5 周）：推荐系统与搜索排序

#### 知识清单

- collaborative filtering、matrix factorization、implicit feedback；
- candidate generation、two-tower、ANN retrieval；
- learning to rank、Wide & Deep、DeepFM、序列推荐；
- 冷启动、曝光偏差、负采样、多目标排序；
- Recall@K、NDCG、MAP、coverage/diversity、线上 A/B；
- feature store、实时特征、召回与排序服务。

#### 路线与任务

1. 第 1 周：MovieLens 上实现 popularity、item-CF、matrix factorization；
2. 第 2 周：训练 two-tower，使用 FAISS 召回；
3. 第 3 周：训练 ranking 模型，对 hard negative 与采样策略做实验；
4. 第 4 周：构建召回—粗排—精排 API、特征 pipeline 和离线回放；
5. 第 5 周：加入冷启动、多样性和探索策略，写线上实验方案。

#### 推荐资源

- [Recommender Systems Handbook/课程资料：Stanford CS246](https://web.stanford.edu/class/cs246/)；
- [Google Machine Learning: Recommendation Systems](https://developers.google.com/machine-learning/recommendation)；
- [NVIDIA Merlin](https://github.com/NVIDIA-Merlin/Merlin)；
- [Microsoft Recommenders](https://github.com/recommenders-team/recommenders)；
- [TorchRec](https://github.com/pytorch/torchrec)；
- [RecBole](https://github.com/RUCAIBox/RecBole)；
- 论文：[Wide & Deep](https://arxiv.org/abs/1606.07792)、[DeepFM](https://arxiv.org/abs/1703.04247)、[SASRec](https://arxiv.org/abs/1808.09781)。

**验收**：严格采用时间切分避免未来信息泄漏；同时报告召回、排序、多样性、覆盖率和服务延迟，而非只报告一个准确率。

### E4（3–4 周）：图机器学习与 Graph RAG

#### 知识清单

- graph representation、message passing、GCN、GraphSAGE、GAT；
- node/edge/graph prediction、negative sampling；
- knowledge graph embedding 与 link prediction；
- graph sampling、oversmoothing、异构图；
- Graph RAG 与普通向量 RAG 的适用边界。

#### 路线与任务

1. 第 1 周：NumPy/PyTorch 实现 message passing 与 GCN；
2. 第 2 周：用 PyG 完成节点分类和 link prediction；
3. 第 3 周：从文档抽实体关系，构建知识图谱与图检索；
4. 第 4 周：在同一问题集比较 BM25、vector RAG、Graph RAG 的质量、延迟和成本。

#### 推荐资源

- [Stanford CS224W: Machine Learning with Graphs](https://web.stanford.edu/class/cs224w/)；
- [CS224W YouTube Playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rPLKxIpqhjhPgdQy7imNkDn)；
- [Geometric Deep Learning Book](https://geometricdeeplearning.com/)；
- [PyTorch Geometric Tutorials](https://pytorch-geometric.readthedocs.io/en/latest/get_started/colabs.html)；
- [DGL Tutorials](https://www.dgl.ai/pages/start.html)；
- 论文：[GCN](https://arxiv.org/abs/1609.02907)、[GraphSAGE](https://arxiv.org/abs/1706.02216)、[GAT](https://arxiv.org/abs/1710.10903)。

**验收**：能说明 Graph RAG 在何种多跳/关系问题上可能获益，并用对照实验避免“用了图所以更好”的循环论证。

### E5（4–5 周）：强化学习

#### 知识清单

- MDP、Bellman equation、dynamic programming；
- Monte Carlo、TD、Q-learning、DQN；
- policy gradient、actor-critic、PPO；
- exploration、credit assignment、off-policy/on-policy；
- offline RL、imitation learning、multi-agent 概念；
- RLHF 中 PPO 与普通控制 RL 的联系和差异。

#### 路线与任务

1. 第 1 周：在 GridWorld 实现 value iteration、policy iteration、Q-learning；
2. 第 2 周：不依赖高层 RL 库实现 DQN，加入 replay 与 target network；
3. 第 3 周：推导并实现 REINFORCE/actor-critic；
4. 第 4 周：实现或完整拆解 PPO，在固定环境做稳定性实验；
5. 第 5 周：做一个自定义环境，或把 preference optimization 与 LLM 后训练阶段关联起来。

#### 推荐资源

- [Sutton & Barto《Reinforcement Learning》免费版](http://incompleteideas.net/book/the-book-2nd.html)；
- [David Silver RL Course](https://www.davidsilver.uk/teaching/)；
- [Berkeley CS285 Deep Reinforcement Learning](https://rail.eecs.berkeley.edu/deeprlcourse/)；
- [OpenAI Spinning Up](https://spinningup.openai.com/en/latest/)；
- [Hugging Face Deep RL Course](https://huggingface.co/learn/deep-rl-course/unit0/introduction)：内容仍适合入门，但官方已说明处于低维护状态；
- [CleanRL](https://github.com/vwxyzjn/cleanrl)、[Stable-Baselines3](https://github.com/DLR-RM/stable-baselines3)。

**验收**：画多随机种子学习曲线和置信区间；能解释样本效率、训练稳定性、reward hacking，而不是只展示一次成功录屏。

### E6（4–5 周）：边缘 AI 与端侧部署

#### 知识清单

- 设备的算力、内存、功耗和热约束；
- PTQ/QAT、剪枝、蒸馏、operator fusion；
- ONNX、TensorRT、TFLite/LiteRT、Core ML；
- dynamic shape、校准集、算子兼容与精度漂移；
- cloud-edge partition、OTA 更新、端侧隐私。

#### 路线与任务

1. 第 1 周：将阶段 2 的视觉模型导出 ONNX，验证数值一致性；
2. 第 2 周：比较 FP32/FP16/INT8，记录精度、内存、延迟；
3. 第 3 周：做 QAT 或知识蒸馏，恢复压缩损失；
4. 第 4 周：部署到 Jetson/手机/树莓派；无设备则用目标 runtime 与 CPU 模拟；
5. 第 5 周：实现端云协同、模型版本和失败回退。

#### 推荐资源

- [MIT 6.S965 TinyML and Efficient Deep Learning](https://hanlab.mit.edu/courses/2023-fall-65940)；
- [EfficientML.ai](https://efficientml.ai/)；
- [TinyML Book / Harvard TinyML](https://tinyml.seas.harvard.edu/)；
- [ONNX Runtime Tutorials](https://onnxruntime.ai/docs/tutorials/)、[TensorRT Docs](https://docs.nvidia.com/deeplearning/tensorrt/)、[LiteRT](https://ai.google.dev/edge/litert)；
- [ExecuTorch](https://pytorch.org/executorch/stable/index.html)、[Core ML Tools](https://apple.github.io/coremltools/docs-guides/)；
- [MCUNet](https://github.com/mit-han-lab/mcunet)、[TinyChat](https://github.com/mit-han-lab/llm-awq)。

**验收**：必须在目标 runtime 实测，不用桌面 GPU 推测端侧性能；报告模型大小、峰值内存、p50/p95 延迟、功耗或近似能耗及精度下降。

### E7（2–4 周）：可靠性、因果与负责任 AI

这是“全面”体系中经常被漏掉的一支，至少达到审计和正确选型能力。

- 学习 calibration、uncertainty、OOD、drift、公平性和可解释性；
- 理解 correlation、intervention、counterfactual 的区别；
- 为毕业项目按用户子群做切片评测、置信度校准、隐私与偏差审计；
- 推荐：[Google Rules of ML](https://developers.google.com/machine-learning/guides/rules-of-ml)、[NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)、[Fairlearn](https://fairlearn.org/)、[Causal Inference: The Mixtape](https://mixtape.scunning.com/)、[DoWhy](https://www.pywhy.org/dowhy/)。

**完成全部扩展后的能力边界**：你不必在每个分支都达到研究员深度，但应能实现标准 baseline、设计正确评测、部署一个小系统，并知道何时邀请该领域专家。

---

## 9. 防止“跟不上时代”的更新机制

不要追逐每日新名词，建立固定信息过滤器：

- 每周：浏览 Hugging Face Papers、arXiv Sanity 或 Papers with Code，仅收藏与当前项目有关的内容；
- 每月：选 1 个新方法，在固定数据集与 baseline 上复现；
- 每季度：重跑核心 benchmark，更新依赖，写一次技术雷达：Adopt/Trial/Assess/Hold；
- 永久：优先论文、官方文档、课程和源代码，谨慎对待“十分钟掌握一切”的二手内容。

新技术采用前问五个问题：

1. 它解决了哪个可测量的问题？
2. 相比简单 baseline 提升多少？
3. 质量、延迟、成本和维护代价是什么？
4. 实验是否匹配我的真实负载？
5. 移除它后系统是否仍然可理解、可运行？

---

## 10. 今天就开始的前 14 天

### 第 1 周

- Day 1：建立 `ai-full-stack-journey` 仓库、环境、任务看板；
- Day 2：NumPy 写 softmax 回归并做数值梯度检查；
- Day 3：NumPy 写两层 MLP 与反向传播；
- Day 4：PyTorch 重写，加入配置、日志和 seed；
- Day 5：pytest、ruff、类型检查与 GitHub Actions；
- Day 6：FastAPI 推理接口 + Docker；
- Day 7：写第一份周报：知识缺口、实验结果、下周计划。

### 第 2 周

- Day 8：CIFAR-10 数据 pipeline 与 baseline；
- Day 9：实现 Conv2d/BatchNorm 的最小版本；
- Day 10：训练小 CNN，保存指标和 checkpoint；
- Day 11：比较 SGD/AdamW、两种学习率；
- Day 12：PyTorch Profiler 分析瓶颈；
- Day 13：错误样本可视化 + Gradio/网页 demo；
- Day 14：整理 README、实验表、演示视频，按验收标准自评。

---

## 11. 你收藏的 B 站课程评估与观看策略

> 评估日期：2026-08-25。评价依据是公开可见的标题、目录、课程来源和本路线的重复度。B 站长合集适合中文辅助，但不应以“完整播放”为完成指标。观看一章后必须完成对应代码或测验。

| BV 号 | 已核对内容 | 建议 | 放入路线的位置 | 原因 |
|---|---|---|---|---|
| [BV1BYe4z5E9z](https://www.bilibili.com/video/BV1BYe4z5E9z/) | 尚硅谷机器学习，120 节；数学、特征工程、KNN、线性/逻辑回归、树、贝叶斯、集成、无监督等 | **不必通看；查漏补缺** | 阶段 0 前自测，最多 1–2 周 | 体系完整且案例多，但你已有 ML/DL 基础，与吴恩达 ML、D2L 和路线阶段 0/1 高度重复。优先看不熟的 PCA、树/集成、聚类和模型评估，跳过历史、环境和已掌握推导。 |
| [BV1k44LzPEhU](https://www.bilibili.com/video/BV1k44LzPEhU/) | 尚硅谷 NLP；分词/BPE、Word2Vec、RNN/LSTM/GRU、Seq2Seq、Attention、Transformer、GPT/BERT/T5，并带智能输入法、情感分析等项目 | **建议选择性系统看** | 阶段 3，第 14–16 周 | 中文讲解和经典 NLP 过渡较完整，能补只会 Transformer、不懂 NLP 演进的问题。分词到 Attention 建议看；GPT/BERT 后改用 CS224N、HF LLM Course 与 CS336；旧式项目做 1 个即可。 |
| [BV14pH9eVEp6](https://www.bilibili.com/video/BV14pH9eVEp6/) | Umar Jamil：基于 PyTorch 从零构建多模态/视觉语言模型 | **建议看并复现，不要只看** | E1 第 2–3 周 | 从零张量实现对理解 VLM 很有价值。把它作为代码辅导，配合 CLIP/LLaVA 原论文与官方仓库；复现后补评测和服务化，因为单个实现视频通常不覆盖生产评测。 |
| [BV1owrpYKEtP](https://www.bilibili.com/video/BV1owrpYKEtP/) | 吴恩达 2022 Machine Learning Specialization 中文搬运/配套版本 | **二选一，不与尚硅谷 ML 双刷** | 阶段 0 前；基础薄弱才完整看 | 吴恩达课程结构、直觉和练习质量好，但目标偏机器学习基础。你若能独立实现线性/逻辑回归、树、聚类并正确评测，就只做课程测验/实验；若自测不足，优先选它作为基础主课。 |
| [BV1iEHPzGEpa](https://www.bilibili.com/video/BV1iEHPzGEpa/) | 你注明为 Vizuara 深度学习合集；公开索引未稳定返回完整目录 | **按主题选看，不整套替代主课** | 阶段 1、3、8 对应主题 | Vizuara 的可视化理论讲解通常适合建立直觉；选择 backprop、CNN、Transformer、优化/GPU 等薄弱章节。主作业仍用 D2L、Karpathy、CS231n/CS336，避免“听懂但写不出”。 |
| [BV1bWRnYJEEF](https://www.bilibili.com/video/BV1bWRnYJEEF/) | 公开页面元数据不足，当前无法可靠确认标题和完整目录 | **暂不列为必看** | 待确认 | 在无法核对讲师、目录、代码和发布时间时，不能负责任地判为主课。保留收藏；先用下面的五项量表自评，或补充视频标题/目录后再决定。 |

### 两门机器学习课如何二选一

先闭卷完成以下自测：

1. 从零实现线性回归、逻辑回归和两层 MLP 的梯度；
2. 解释 bias–variance、正则化、交叉验证和数据泄漏；
3. 对树模型、SVM、聚类、PCA 说明适用场景与核心假设；
4. 在一个表格数据集建立 sklearn pipeline，正确划分并做错误分析；
5. 解释 accuracy、precision/recall、ROC-AUC、PR-AUC 在不平衡数据中的选择。

- 能完成 4–5 项：两套都不用通看，只查缺口；
- 能完成 2–3 项：选 **吴恩达 2022** 做主线，尚硅谷作中文查阅；
- 只能完成 0–1 项：完整学习吴恩达课程并完成 labs，之后直接进入本路线，不再完整刷第二套。

### Vizuara 合集的正确用法

Vizuara 适合作为“第二解释源”，而不是唯一课程：

- 第一次：先看路线主资料和做实现；
- 卡住时：看对应 Vizuara 章节获取可视化直觉；
- 看完：合上视频，自己画计算图、写公式、实现最小代码；
- 能实现后：回到论文/官方文档核对符号、边界和最新 API。

### 长视频是否值得看的五项量表

每项 0–2 分，总分低于 6 分直接跳过，6–8 分选择性看，9–10 分可作为主课：

1. **来源**：讲师/机构是否有相关专业背景，是否注明原作者和版本；
2. **结构**：是否有完整 syllabus，从目标、原理、实现到评测；
3. **实践**：是否有可运行代码、作业、测试与数据，而非只有跟敲；
4. **时效**：原理课可较旧；框架/API 课应接近当前版本并以官方文档为准；
5. **产出**：看完能否形成一个可独立复现、可量化评测的作品。

### 最终观看清单

- **完整/近完整学习**：尚硅谷 NLP 的经典 NLP 主干；
- **边看边复现**：Umar Jamil 多模态从零实现；
- **按薄弱点选择**：Vizuara 深度学习合集；
- **二选一或只查漏**：吴恩达 ML 与尚硅谷 ML；
- **等待补充信息**：BV1bWRnYJEEF。

总原则：课程不是收藏品。每 10 小时视频至少对应 15–20 小时代码、实验和复盘；否则“全面”只会变成重复入门。

---

## 结语

你的优势是已有 ML/DL 基础，所以不需要从“认识神经网络”重新开始，而要从 **实现、评测、系统化和生产约束** 重新开始。真正抗迭代的能力不是记住 LangChain 某个 API，而是理解模型、数据、检索、工具、系统和评测之间的边界，并能用实验作出工程决策。

执行时只盯住当前阶段：**每阶段一个可展示作品，每周一个可验证输出，每个结论都有 baseline。**
