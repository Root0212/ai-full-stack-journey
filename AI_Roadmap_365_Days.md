# 我的 AI Roadmap：365 天成为 AI 专业应用型人才

> 执行周期：2026-09-23 ～ 2027-09-22  
> 学习节奏：每周 6 天；周日休息/补欠账；工作日与周六约 4 小时  
> 个人起点：通信＋深度学习硕士，具备 Python/PyTorch 和神经网络经验；补齐 ML、LLM、工程、项目与面试能力  
> 求职定位：**AI 应用/大模型工程师为主线，兼具算法训练、微调、部署能力**

---

## 1. 一年后的可验证目标

到 2027-09-22，你应能：

1. 画出 AI/ML/DL/NLP/CV/LLM/RAG/Agent/MLOps 的关系，并解释常见算法的假设、损失、训练和评价。
2. 用 NumPy 实现经典 ML 与两层网络；用 PyTorch 独立完成训练、诊断、调参与复现。
3. 从零训练一个小型 GPT（学习流程，不追求“大”），对开源小模型做 LoRA/QLoRA，并客观评测。
4. 独立构建带检索评测的 RAG、可调用工具的 Agent、FastAPI 服务、Docker 镜像与演示界面。
5. GitHub 至少有 5 个可运行项目、12 篇技术笔记、1 个生产级毕业项目。
6. 完成约 150 道算法题，能够应对中国 AI 应用/算法岗位的常见编程、ML、DL、LLM 与项目面试。

### 推荐岗位优先级

| 优先级 | 岗位 | 原因 |
|---|---|---|
| A | AI 应用工程师 / 大模型应用工程师 | 一年内最匹配，既用模型又交付产品，岗位面较宽 |
| A | 大模型算法工程师（应用/微调/评测方向） | 学历和 PyTorch 背景有优势，需用作品证明 LLM 能力 |
| B | NLP/深度学习算法工程师 | 可投，但部分岗位较看论文、实习与垂域经验 |
| B | 模型部署/推理工程师 | 学完部署与优化后可投；需要补 Linux/CUDA/服务性能 |
| C | 纯研究型算法岗 | 一年路线不会以顶会论文或大规模预训练为目标 |

不要追求“适配所有岗位”。T 型能力结构是：横向掌握通用 AI 全链路，纵向把 **LLM 应用＋评测＋工程交付** 做深。

---

## 2. 执行规则

### 每天 4 小时模板

- 前 16 周：理论/课程 120 分钟，跟敲与练习 90 分钟，复盘 30 分钟。
- 第 17～32 周：理论 75 分钟，编码 105 分钟，项目 45 分钟，复盘 15 分钟。
- 第 33～52 周：理论 45 分钟，项目 150 分钟，面试/复盘 45 分钟。
- 每学习 50 分钟休息 10 分钟；休息不计入 4 小时。
- 周日默认完全休息。只有当周缺课不超过 2 天时才补；超过 2 天则整体顺延，禁止周日通宵追赶。

### 每日完成定义（DoD）

每天必须留下至少一种证据：可运行代码、测试、图表、实验表、200 字笔记、口述录音或 Git commit。视频“看完”不算完成；能够闭卷解释＋修改代码＋得到预期结果才算。

### 防完美主义协议

1. 单个报错独立排查 45 分钟后，记录“现象/尝试/最小复现”，再查文档或求助。
2. 笔记每主题最多一页；README 首版最多 90 分钟，先可用再美化。
3. 当天达到 80% DoD 即可前进；疑问进 `BACKLOG.md`，每月统一清理。
4. 同一主题最多使用一个主课程＋一个补充资料，禁止不断换课。
5. 项目先做最小闭环，再做优化；不因 UI、命名或调参拖延核心交付。

### 建议仓库结构

```text
ai-roadmap/
  notes/              # 每周和论文笔记
  exercises/          # NumPy、ML、PyTorch、算法题
  projects/           # 5 个作品
  interview/          # 面试题与错题
  weekly-review.md    # 周复盘
  BACKLOG.md           # 暂不阻塞主线的问题
```

---

## 3. 资源索引（下文用编号引用）

### 基础、机器学习与深度学习

- **R01** [AI for Everyone（Andrew Ng，建立知识地图）](https://www.coursera.org/learn/ai-for-everyone)；B站关键词：`吴恩达 AI For Everyone 中文字幕`。
- **R02** [Stanford CS221 官方课程页](https://stanford-cs221.github.io/autumn2025/)；若学期页变化，使用[课程归档](https://web.stanford.edu/class/archive/cs/cs221/cs221.1186/)。B站关键词：`CS221 2025 人工智能原理 中文字幕`。
- **R03** [NumPy Learn](https://numpy.org/learn/) 与 [pandas Getting Started](https://pandas.pydata.org/docs/getting_started/index.html)。
- **R04** [scikit-learn 免费官方 MOOC](https://inria.github.io/scikit-learn-mooc/)；练习带答案且持续更新。
- **R05** [scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html)。
- **R06** [《动手学深度学习》中文站](https://zh.d2l.ai/)；B站关键词：`李沐 动手学深度学习 PyTorch 第二版`。
- **R07** [PyTorch Learn the Basics](https://docs.pytorch.org/tutorials/beginner/basics/) 与 [PyTorch Tutorials](https://docs.pytorch.org/tutorials/)。
- **R08** [fast.ai Practical Deep Learning](https://course.fast.ai/)；作为实践补充，不要求全刷。
- **R09** [CS231n 课程笔记](https://cs231n.github.io/)；B站关键词：`CS231n 中文字幕`。
- **R10** [CS224N 官方课程](https://web.stanford.edu/class/cs224n/)；B站关键词：`CS224N 2024 中文字幕`。

### LLM、微调、RAG 与 Agent

- **R11** [Hugging Face LLM Course](https://huggingface.co/learn/llm-course/chapter1/1)（免费）。
- **R12** [Andrej Karpathy Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html)；B站关键词：`Karpathy Zero to Hero 中文字幕`。
- **R13** [nanoGPT](https://github.com/karpathy/nanoGPT) 与 [build-nanogpt](https://github.com/karpathy/build-nanogpt)。
- **R14** [Transformers 官方文档](https://huggingface.co/docs/transformers/index)。
- **R15** [PEFT 官方文档](https://huggingface.co/docs/peft/index) 与 [LoRA 指南](https://huggingface.co/docs/peft/main/conceptual_guides/lora)。
- **R16** [TRL 官方文档](https://huggingface.co/docs/trl/index)。
- **R17** [Full Stack Deep Learning LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/)；B站关键词：`FSDL LLM Bootcamp 中文字幕`。
- **R18** [Hugging Face Agents Course](https://huggingface.co/learn/agents-course/unit0/introduction)（免费，含项目）。
- **R19** [LangGraph 官方教程](https://langchain-ai.github.io/langgraph/tutorials/)。
- **R20** [LlamaIndex RAG 文档](https://docs.llamaindex.ai/en/stable/understanding/rag/)。
- **R21** [RAGAS 文档](https://docs.ragas.io/)；用于 RAG 评测。

### 工程、部署与算法题

- **R22** [Hello 算法](https://www.hello-algo.com/)；目标 150 题，不走竞赛路线。
- **R23** [MIT Missing Semester 中文版](https://missing-semester-cn.github.io/)；命令行、Git、调试。
- **R24** [Pro Git 中文版](https://git-scm.com/book/zh/v2)。
- **R25** [SQLBolt](https://sqlbolt.com/)；交互式 SQL。
- **R26** [FastAPI 官方教程](https://fastapi.tiangolo.com/tutorial/)。
- **R27** [Docker Get Started](https://docs.docker.com/get-started/)。
- **R28** [Gradio Quickstart](https://www.gradio.app/guides/quickstart)。
- **R29** [MLflow 文档](https://mlflow.org/docs/latest/ml/) 与 [Weights & Biases 免费教程](https://docs.wandb.ai/tutorials/)（二选一，默认 MLflow）。
- **R30** [Kaggle Learn](https://www.kaggle.com/learn)；完成 Pandas、Intro ML、Intermediate ML、Explainability。
- **R31** [Google Colab FAQ](https://research.google.com/colaboratory/faq.html) 与 [Kaggle Notebooks 文档](https://www.kaggle.com/docs/notebooks)。
- **R32** [ONNX Runtime 文档](https://onnxruntime.ai/docs/)；Linux 环境可再看 [vLLM 文档](https://docs.vllm.ai/)。

### 核心论文

- **P01** [Attention Is All You Need](https://arxiv.org/abs/1706.03762)
- **P02** [BERT](https://arxiv.org/abs/1810.04805)
- **P03** [GPT-3](https://arxiv.org/abs/2005.14165)
- **P04** [Scaling Laws for Neural Language Models](https://arxiv.org/abs/2001.08361)
- **P05** [Chinchilla / Compute-Optimal LLM Training](https://arxiv.org/abs/2203.15556)
- **P06** [InstructGPT](https://arxiv.org/abs/2203.02155)
- **P07** [LoRA](https://arxiv.org/abs/2106.09685)
- **P08** [QLoRA](https://arxiv.org/abs/2305.14314)
- **P09** [RAG](https://arxiv.org/abs/2005.11401)
- **P10** [Sentence-BERT](https://arxiv.org/abs/1908.10084)
- **P11** [ReAct](https://arxiv.org/abs/2210.03629)
- **P12** [DPO](https://arxiv.org/abs/2305.18290)
- **P13** [FlashAttention](https://arxiv.org/abs/2205.14135)

论文阅读只要求：问题、核心方法、关键公式/图、实验结论、局限各写 1～3 句；第一遍不逐字翻译。

---

## 4. 365 天逐日计划

说明：每周从周三到周二；第 5 天固定为周日休息。`题`是累计算法题目标。每周最后一天完成复盘与一次 Git push。

### 阶段 A：建立 AI 地图与数据/工程基础（W1–W8）

#### W1（2026-09-23 ～ 2026-09-29）｜认识 AI 全景与环境体检

| 日 | 4 小时任务与交付物 |
|---|---|
| D1 | R01 前半：AI/ML/DL/数据科学关系；画一张知识地图；写下目标岗位假设与一年终点。 |
| D2 | R01 后半：监督/非监督/强化学习、AI 项目流程；用 500 字解释“模型不是产品”。 |
| D3 | 安装/核验 Python、Git、CUDA、PyTorch；运行 GPU 张量和反向传播；保存 `env_check.py`。 |
| D4 | R31：学会新建 Colab/Kaggle Notebook、挂载数据、切换 GPU；各跑一个最小 Notebook。 |
| D5 | **休息**；若 D1–D4 均完成，不得补充新课程。 |
| D6 | 建 `ai-roadmap` 仓库与目录；R24 学 add/commit/branch/log；完成 5 次有意义提交。 |
| D7 | R02 CS221 Lecture 1–2（Overview、Learning I）；闭卷重画 AI 地图；题 1～2。若看 B 站，以课程标题和讲次搜索。 |

#### W2（2026-09-30 ～ 2026-10-06）｜Python、NumPy 与可复现代码

| 日 | 任务 |
|---|---|
| D8 | Python 函数、类、迭代器、上下文管理器复习；写数据批处理小程序和 5 个测试。 |
| D9 | R03 NumPy：shape、dtype、索引、广播；完成 20 个小操作并标注输出形状。 |
| D10 | NumPy 向量化、矩阵乘法、随机数；比较循环与向量化耗时。 |
| D11 | 用 NumPy 实现标准化、softmax（数值稳定）、交叉熵；做极端值测试。 |
| D12 | **休息**。 |
| D13 | R23 Shell 1：路径、管道、重定向、环境变量；在 PowerShell 与 Colab/Linux 对照练习。 |
| D14 | R02 CS221 Lecture 3–4（Learning II–III）；整理监督学习、特征与优化关系；题 3～5。 |

#### W3（2026-10-07 ～ 2026-10-13）｜pandas 与数据分析

| 日 | 任务 |
|---|---|
| D15 | R03/R30 Pandas：Series、DataFrame、读写、索引；完成 Kaggle Pandas 1～2 节。 |
| D16 | 缺失值、重复值、类型、异常值；对 Titanic 做数据质量报告。 |
| D17 | groupby、merge、pivot；回答 10 个业务式数据问题。 |
| D18 | Matplotlib/Seaborn：分布、相关、类别对比；输出 6 张有标题和结论的图。 |
| D19 | **休息**。 |
| D20 | 写一个 `clean_data(df)` 管道和 pytest；保留原始/处理后数据及数据字典。 |
| D21 | R02 CS221 Lecture 5–6（Search I–II）；实现 DFS/BFS/UCS/A* 最小例子；题 6～8。 |

#### W4（2026-10-14 ～ 2026-10-20）｜数学与 ML 问题定义

| 日 | 任务 |
|---|---|
| D22 | R06 2.3：向量、矩阵、范数、特征值/SVD；手算＋NumPy 验证。 |
| D23 | R06 2.4/2.5：梯度、链式法则、自动微分；手推二元函数梯度。 |
| D24 | 概率、期望、方差、条件概率、MLE/MAP；写一页概念卡。 |
| D25 | 训练/验证/测试、偏差方差、数据泄漏、指标选择；为 3 个业务案例定义任务和指标。 |
| D26 | **休息**。 |
| D27 | R02 CS221 Lecture 7–8（MDP I–II）；画状态/动作/转移/奖励图，手算 2 次 value iteration。 |
| D28 | **月考 1**；题 9～11；整理错题，答案见第 6 节。 |

#### W5（2026-10-21 ～ 2026-10-27）｜传统机器学习 I

| 日 | 任务 |
|---|---|
| D29 | R04 Module 1：表格数据、pipeline、交叉验证；跑第一个分类基线。 |
| D30 | 线性/逻辑回归：损失、正则化、决策边界；从零实现 logistic 回归。 |
| D31 | 指标：precision/recall/F1/ROC-AUC/PR-AUC；构造类别不平衡例子。 |
| D32 | R04 数值/类别预处理；ColumnTransformer＋Pipeline，证明无泄漏。 |
| D33 | **休息**。 |
| D34 | Kaggle Intro ML 1～4；建立验证集、决策树、随机森林基线。 |
| D35 | R02 CS221 Lecture 9–10（MDP III、Games I）；实现 toy value iteration/minimax；题 12～14。 |

#### W6（2026-10-28 ～ 2026-11-03）｜传统机器学习 II

| 日 | 任务 |
|---|---|
| D36 | 决策树：划分、熵/Gini、过拟合；手工计算一次划分。 |
| D37 | Bagging、随机森林、GBDT 原理；用 sklearn 比较并画学习曲线。 |
| D38 | XGBoost/LightGBM 只学核心思想；用 sklearn HistGradientBoosting 建基线。 |
| D39 | 超参数搜索、交叉验证、nested CV 概念；RandomizedSearchCV 实验。 |
| D40 | **休息**。 |
| D41 | Kaggle Intermediate ML：缺失、类别、pipeline、CV；完成练习。 |
| D42 | R02 CS221 Lecture 11–12（Games II、Bayesian Networks I）；画一个 Bayes net 并做一次条件概率推断；题 15～17。 |

#### W7（2026-11-04 ～ 2026-11-10）｜无监督学习与可解释性

| 日 | 任务 |
|---|---|
| D43 | k-means、层次聚类、DBSCAN：假设与差异；在合成数据可视化。 |
| D44 | PCA：方差最大化与 SVD 直觉；从零实现 PCA 并与 sklearn 对比。 |
| D45 | 特征选择、置换重要性、PDP；说明“重要性不等于因果”。 |
| D46 | R30 Explainability：完成 SHAP/特征重要性练习。 |
| D47 | **休息**。 |
| D48 | Mini Project 1 选题与 EDA：公开表格数据分类/回归，写任务卡和基线。 |
| D49 | R02 CS221 Lecture 13–14（Bayesian Networks II–III）；项目数据管道＋3 个模型；题 18～20。 |

#### W8（2026-11-11 ～ 2026-11-17）｜项目 1：端到端传统 ML

| 日 | 任务 |
|---|---|
| D50 | 项目调参与交叉验证；锁定主指标，记录所有实验而非挑最好结果。 |
| D51 | 类别/回归错误分析、校准或阈值选择；分析至少 30 个失败样本。 |
| D52 | 用 FastAPI 做最小预测接口（先照 R26 前 3 节）；写请求/响应 schema。 |
| D53 | 写 pytest、requirements/pyproject、启动说明；在新环境复现。 |
| D54 | **休息**。 |
| D55 | 完成 README：问题、数据、方法、指标、局限、复现；录 3 分钟演示。 |
| D56 | R02 CS221 Lecture 15–16（Logic I–II）；**里程碑 1 答辩**＋题 21～23；发布项目 1。 |

### 阶段 B：深度学习与 PyTorch 扎实重建（W9–W18）

#### W9（2026-11-18 ～ 2026-11-24）｜D2L 预备与线性网络

| 日 | 任务 |
|---|---|
| D57 | R06 第 1～2 章快速复习；只做薄弱练习，建立张量 shape 调试清单。 |
| D58 | R06 3.1～3.3：线性回归从零；独立重写数据、模型、loss、SGD。 |
| D59 | R06 3.4～3.7：softmax 回归、交叉熵；推导并做 Fashion-MNIST。 |
| D60 | R07 Dataset/DataLoader/Transforms；自定义 Dataset 并检查 batch。 |
| D61 | **休息**。 |
| D62 | 写通用 train/evaluate，含 device、seed、checkpoint、指标。 |
| D63 | R02 CS221 Lecture 17–18（Language Models、AI & Society）；不看代码重建 softmax；题 24～26。 |

#### W10（2026-11-25 ～ 2026-12-01）｜MLP、反向传播与优化

| 日 | 任务 |
|---|---|
| D64 | R06 第 4 章：MLP、激活函数；从零和 nn.Module 各实现一次。 |
| D65 | 手推两层网络反向传播；做有限差分 gradient check。 |
| D66 | 初始化、梯度消失/爆炸；记录不同初始化的梯度分布。 |
| D67 | SGD/Momentum/Adam/AdamW；在同任务对比收敛与泛化。 |
| D68 | **休息**。 |
| D69 | weight decay、dropout、early stopping；设计控制变量实验。 |
| D70 | R02 CS221 Lecture 19–20（AI Supply Chains、Conclusion）；月考 2；题 27～29；输出“AI 全景第二版”。 |

#### W11（2026-12-02 ～ 2026-12-08）｜CNN 基础

| 日 | 任务 |
|---|---|
| D71 | R06 6.1～6.3：卷积、padding、stride；手算输出尺寸。 |
| D72 | 从零实现 im2col/简化二维卷积，与 PyTorch 对比数值。 |
| D73 | LeNet/AlexNet：结构演进；在 CIFAR-10 训练小 CNN。 |
| D74 | BatchNorm 原理、train/eval 差异；构造错误使用案例。 |
| D75 | **休息**。 |
| D76 | 数据增强与正则；做无增强/有增强对照实验。 |
| D77 | 题 30～32；写 CNN shape 单元测试；周复盘。 |

#### W12（2026-12-09 ～ 2026-12-15）｜现代 CNN 与迁移学习

| 日 | 任务 |
|---|---|
| D78 | VGG/Inception 读结构；解释 1×1 卷积作用。 |
| D79 | ResNet：残差为何易优化；从零实现 Residual block。 |
| D80 | R07 transfer learning tutorial；冻结/解冻比较。 |
| D81 | 学习率调度、mixed precision、梯度累积；记录显存和耗时。 |
| D82 | **休息**。 |
| D83 | TensorBoard 或 MLflow 记录指标、超参、artifact。 |
| D84 | 复现实验并比较两次结果；题 33～35；周复盘。 |

#### W13（2026-12-16 ～ 2026-12-22）｜视觉任务概览

| 日 | 任务 |
|---|---|
| D85 | R09 分类/定位/检测/分割地图；理解 IoU、mAP、NMS。 |
| D86 | 目标检测两阶段/单阶段直觉；运行 torchvision detection 示例。 |
| D87 | FCN/U-Net 分割原理；用小数据跑语义分割。 |
| D88 | 数据标注、类别不平衡、增强；设计视觉数据质量清单。 |
| D89 | **休息**。 |
| D90 | Mini Project 2 选题：图像分类或分割；写任务卡、数据卡、基线。 |
| D91 | 完成训练管线与首个结果；题 36～38；周复盘。 |

#### W14（2026-12-23 ～ 2026-12-29）｜项目 2：视觉模型与服务

| 日 | 任务 |
|---|---|
| D92 | 项目迁移学习、增广和调参；只允许 3 组有假设的实验。 |
| D93 | 混淆矩阵＋30 个错误样本，按错误类型分组。 |
| D94 | Grad-CAM 或显著图；判断模型是否学到伪相关。 |
| D95 | FastAPI/Gradio 推理界面；验证图片、异常输入和延迟。 |
| D96 | **休息**。 |
| D97 | README、模型卡、演示；记录显存、训练时长、局限。 |
| D98 | **里程碑 2 答辩**；题 39～41；发布项目 2。 |

#### W15（2026-12-30 ～ 2027-01-05）｜序列模型

| 日 | 任务 |
|---|---|
| D99 | R06 第 8 章：语言模型、n-gram、困惑度；实现字符统计模型。 |
| D100 | RNN 展开、BPTT、梯度问题；手推一个时间步。 |
| D101 | 从零字符级 RNN；训练、采样并分析失败。 |
| D102 | GRU/LSTM 门控；用 PyTorch 实现并比较长期依赖。 |
| D103 | **休息**。 |
| D104 | 序列 padding、packing、mask；写 batch shape 测试。 |
| D105 | 月考 3；题 42～44；写“RNN 为什么被 Transformer 取代但仍有用”。 |

#### W16（2027-01-06 ～ 2027-01-12）｜Attention 与 Seq2Seq

| 日 | 任务 |
|---|---|
| D106 | encoder-decoder、teacher forcing、beam search；画数据流。 |
| D107 | additive/dot-product attention；从零写 scaled dot-product attention。 |
| D108 | mask：padding vs causal；做可视化验证不偷看未来。 |
| D109 | multi-head attention：拆分/拼接 shape；实现并测试。 |
| D110 | **休息**。 |
| D111 | 用 `nn.MultiheadAttention` 对齐自实现，检查最大误差。 |
| D112 | 题 45～47；用 5 分钟讲清 Q/K/V；周复盘。 |

#### W17（2027-01-13 ～ 2027-01-19）｜Transformer 从零

| 日 | 任务 |
|---|---|
| D113 | 精读 P01 摘要、图 1、3.2、实验与结论；写一页论文卡。 |
| D114 | positional encoding、残差、LayerNorm；实现组件测试。 |
| D115 | 实现 Transformer encoder block；打印每层 shape/参数量。 |
| D116 | 实现 decoder block 与 causal mask；写“不泄漏未来”测试。 |
| D117 | **休息**。 |
| D118 | 拼装小 Transformer 完成 toy copy/翻译任务。 |
| D119 | 题 48～50；画 Transformer 全图并闭卷解释；周复盘。 |

#### W18（2027-01-20 ～ 2027-01-26）｜深度学习综合诊断

| 日 | 任务 |
|---|---|
| D120 | 过拟合一个 batch、梯度/激活监控、loss 异常排查。 |
| D121 | profiler、DataLoader 瓶颈、AMP；比较吞吐与显存。 |
| D122 | 可复现性：seed、deterministic、依赖/数据/模型版本。 |
| D123 | 整理 `pytorch-training-template`，加入 config/log/test/checkpoint。 |
| D124 | **休息**。 |
| D125 | 深度学习模拟面试 30 题，口述并记录不会项。 |
| D126 | **里程碑 3**：两小时闭卷搭训练管线；题 51～53；补错。 |

### 阶段 C：NLP、LLM 原理与从零预训练（W19–W28）

#### W19（2027-01-27 ～ 2027-02-02）｜NLP 基础与文本分类

| 日 | 任务 |
|---|---|
| D127 | R10 NLP 任务地图、tokenization、词表、OOV；实现 whitespace/字符 tokenizer。 |
| D128 | one-hot、BoW、TF-IDF；用 sklearn 做中文或英文文本分类基线。 |
| D129 | word2vec/负采样直觉；训练小词向量并观察近邻。 |
| D130 | embedding、padding、mask；用 PyTorch 做平均池化分类器。 |
| D131 | **休息**。 |
| D132 | 与 RNN/CNN 文本分类比较；记录速度、参数、F1。 |
| D133 | 错误分析 30 条；题 54～56；周复盘。 |

#### W20（2027-02-03 ～ 2027-02-09）｜BERT 与预训练范式

| 日 | 任务 |
|---|---|
| D134 | 精读 P02：MLM、NSP、预训练/微调；论文卡。 |
| D135 | encoder-only/decoder-only/encoder-decoder 对比；为 8 个任务选架构。 |
| D136 | R11 Chapter 1：pipeline、模型、tokenizer；运行 5 类任务。 |
| D137 | R11 Chapter 2：AutoModel/Tokenizer、batch、padding/truncation。 |
| D138 | **休息**。 |
| D139 | 微调小型 BERT 文本分类；保存指标与混淆矩阵。 |
| D140 | 月考 4；题 57～59；解释“预训练为何能迁移”。 |

#### W21（2027-02-10 ～ 2027-02-16）｜Tokenizer 与数据管道

| 日 | 任务 |
|---|---|
| D141 | BPE/WordPiece/Unigram 原理；手工做 3 轮 BPE merge。 |
| D142 | R11 Tokenizers：训练一个小 BPE tokenizer，检查特殊 token。 |
| D143 | R11 Datasets：load/map/filter/batch/cache；制作文本数据集。 |
| D144 | 数据去重、污染、质量、许可证与隐私；写数据卡。 |
| D145 | **休息**。 |
| D146 | 写 streaming/动态 padding collator，测 tokens/s。 |
| D147 | tokenizer 单测：Unicode、长文本、空串；题 60～62；复盘。 |

#### W22（2027-02-17 ～ 2027-02-23）｜生成式语言模型

| 日 | 任务 |
|---|---|
| D148 | GPT decoder-only、next-token loss；对比 BERT 目标。 |
| D149 | greedy/temperature/top-k/top-p；用固定 logits 验证采样。 |
| D150 | KV cache 原理、prefill/decode；计算缓存形状和显存。 |
| D151 | P03 选读：in-context learning、few-shot；论文卡。 |
| D152 | **休息**。 |
| D153 | R12 makemore 前两讲：bigram 与 MLP language model，跟敲后重写。 |
| D154 | 题 63～65；实现生成器并比较策略；周复盘。 |

#### W23（2027-02-24 ～ 2027-03-02）｜从零网络：micrograd 与语言模型

| 日 | 任务 |
|---|---|
| D155 | R12 micrograd：标量自动微分；从零实现 Value 与拓扑反传。 |
| D156 | gradient check、计算图可视化；为加乘、tanh、ReLU 写测试。 |
| D157 | R12 makemore MLP：embedding/context；独立复现。 |
| D158 | BatchNorm 训练/推理细节；复现统计量 bug。 |
| D159 | **休息**。 |
| D160 | 把 NumPy/PyTorch/autograd 三种实现关系写成教程。 |
| D161 | 题 66～68；闭卷实现一个最小 MLP 训练；周复盘。 |

#### W24（2027-03-03 ～ 2027-03-09）｜从零 GPT I

| 日 | 任务 |
|---|---|
| D162 | R12 GPT 相关讲解或 build-nanogpt：数据、batch、bigram baseline。 |
| D163 | self-attention 从单头到多头；逐行写 shape 注释。 |
| D164 | causal self-attention＋mask 测试；证明 token t 不依赖未来。 |
| D165 | block/MLP/residual/LayerNorm；搭最小 GPT。 |
| D166 | **休息**。 |
| D167 | 在 Tiny Shakespeare/中文小语料训练，记录 loss/样本/耗时。 |
| D168 | 月考 5；题 69～71；解释训练 loss 与生成质量不等价。 |

#### W25（2027-03-10 ～ 2027-03-16）｜从零 GPT II：严谨训练

| 日 | 任务 |
|---|---|
| D169 | 数据切分、tokenizer、context length；避免 train/val 泄漏。 |
| D170 | AdamW、warmup、cosine decay、梯度裁剪；做控制变量实验。 |
| D171 | P04/P05：scaling law 与 compute-optimal 直觉；各写半页。 |
| D172 | 参数量/FLOPs/tokens/显存估算；为 16GB 卡制定可行配置。 |
| D173 | **休息**。 |
| D174 | AMP、梯度累积、checkpoint/resume；中断后恢复并验证。 |
| D175 | 题 72～74；实验报告：配置、曲线、样本、限制。 |

#### W26（2027-03-17 ～ 2027-03-23）｜项目 3：小型 GPT 预训练

| 日 | 任务 |
|---|---|
| D176 | 定义项目：公开小语料、许可、tokenizer、模型规模、预算和指标。 |
| D177 | 完成数据下载/清洗/切分/数据卡；统计 tokens 与重复率。 |
| D178 | 训练 tokenizer＋baseline GPT；保存首个可恢复 checkpoint。 |
| D179 | 运行 2～3 个可解释实验（context/width/lr 中选一变量）。 |
| D180 | **休息**。 |
| D181 | 评测 perplexity、吞吐、显存；固定 prompts 比较样本。 |
| D182 | 题 75～77；写中期报告与失败分析；周复盘。 |

#### W27（2027-03-24 ～ 2027-03-30）｜项目 3 完成与论文理解

| 日 | 任务 |
|---|---|
| D183 | 最终训练/早停；禁止为漂亮结果无限加算力。 |
| D184 | 消融：去位置编码/改变 head 或深度；解释结果。 |
| D185 | README：从数据到生成的全流程、一键命令、硬件与时长。 |
| D186 | 写模型卡：用途、不可用场景、偏差、训练数据、指标。 |
| D187 | **休息**。 |
| D188 | 录 5 分钟讲解：tokenizer→batch→attention→loss→sampling。 |
| D189 | **里程碑 4 答辩**；题 78～80；发布项目 3。 |

#### W28（2027-03-31 ～ 2027-04-06）｜Hugging Face 生态

| 日 | 任务 |
|---|---|
| D190 | R11 Chapter 3：Trainer 与纯 PyTorch fine-tune 对比。 |
| D191 | R11 Chapter 4：Hub、模型卡、上传/下载（可设公开仓库）。 |
| D192 | R14 generation config、stopping、logits processor；做采样实验。 |
| D193 | Accelerate 基础与 device_map；观察模型加载显存。 |
| D194 | **休息**。 |
| D195 | 用小开源模型完成分类/摘要/生成三个 Notebook。 |
| D196 | 月考 6；题 81～83；整理 Transformers 常见坑。 |

### 阶段 D：后训练、微调、评测与 RAG（W29–W38）

#### W29（2027-04-07 ～ 2027-04-13）｜指令微调与对齐概念

| 日 | 任务 |
|---|---|
| D197 | P06：SFT、reward model、PPO/RLHF 流程；画流程图。 |
| D198 | chat template、system/user/assistant、loss mask；检查模板 token。 |
| D199 | 指令数据质量、格式、去重、拒答与安全；制定样本 rubric。 |
| D200 | R16 SFTTrainer：用极小数据跑通 SFT，全程记录显存。 |
| D201 | **休息**。 |
| D202 | 建 100～300 条高质量小数据或使用许可清晰的公开子集。 |
| D203 | 题 84～86；人工评估 base vs SFT 20 个样本。 |

#### W30（2027-04-14 ～ 2027-04-20）｜LoRA / QLoRA

| 日 | 任务 |
|---|---|
| D204 | P07：低秩更新推导、rank/alpha/target modules；论文卡。 |
| D205 | R15 PEFT quicktour；给小模型加 LoRA，打印可训练参数比例。 |
| D206 | P08：NF4、double quantization、paged optimizer 直觉；论文卡。 |
| D207 | 4-bit QLoRA 尝试；若 Windows/bitsandbytes 不稳则用 Colab/Kaggle。 |
| D208 | **休息**。 |
| D209 | 比较 full/LoRA/QLoRA 的显存、时长、checkpoint、质量。 |
| D210 | 月考 7；题 87～89；写微调选择决策树。 |

#### W31（2027-04-21 ～ 2027-04-27）｜LLM 评测

| 日 | 任务 |
|---|---|
| D211 | 区分训练 loss、自动指标、任务指标、人工评测、LLM-as-judge。 |
| D212 | 建 50 条冻结 eval set 与 rubric；严禁用评测集调训练。 |
| D213 | exact match/F1/ROUGE/BERTScore 概念；为任务选指标。 |
| D214 | judge 偏差、位置偏差、泄漏；双盲/顺序交换小实验。 |
| D215 | **休息**。 |
| D216 | 对 base/SFT/LoRA 运行统一评测，输出置信区间或逐例表。 |
| D217 | 题 90～92；写结果与反例，不只报平均分。 |

#### W32（2027-04-28 ～ 2027-05-04）｜偏好优化、安全与微调项目

| 日 | 任务 |
|---|---|
| D218 | P12：DPO 目标直觉及相对 SFT/RLHF 的位置；论文卡。 |
| D219 | R16 DPOTrainer 文档；在 toy/small 数据跑通或读代码并画流程。 |
| D220 | 幻觉、越狱、提示注入、数据隐私、许可证；写威胁模型。 |
| D221 | 项目 4 定稿：本地小模型领域指令微调＋评测；整理代码。 |
| D222 | **休息**。 |
| D223 | README、训练配置、数据卡、模型卡、评测集与结果表。 |
| D224 | **里程碑 5 答辩**；题 93～95；发布项目 4。 |

#### W33（2027-05-05 ～ 2027-05-11）｜Embedding 与检索基础

| 日 | 任务 |
|---|---|
| D225 | sparse vs dense retrieval、BM25、bi-encoder/cross-encoder；画检索链路。 |
| D226 | P10：Sentence-BERT；理解对比学习与 cosine similarity。 |
| D227 | chunking：固定、递归、语义；在同文档比较召回。 |
| D228 | FAISS/Chroma 任选其一；实现 ingest→embed→search 最小闭环。 |
| D229 | **休息**。 |
| D230 | 构建 30 问的检索评测集，计算 Recall@k/MRR。 |
| D231 | 题 96～98；比较 BM25/dense/hybrid；周复盘。 |

#### W34（2027-05-12 ～ 2027-05-18）｜RAG 基础

| 日 | 任务 |
|---|---|
| D232 | P09：parametric/non-parametric memory；论文卡。 |
| D233 | R20 RAG 流程；不用框架先用 Python 写 retrieve→prompt→generate。 |
| D234 | prompt 引用、上下文排序、拒答；设计可追溯答案格式。 |
| D235 | reranker、query rewrite、metadata filter；各做一次对照。 |
| D236 | **休息**。 |
| D237 | 文档解析：PDF/Markdown/网页；处理页码、表格与重复页眉。 |
| D238 | 月考 8；题 99～101；写 RAG 失败分类法。 |

#### W35（2027-05-19 ～ 2027-05-25）｜RAG 评测与调优

| 日 | 任务 |
|---|---|
| D239 | 拆分检索质量与生成质量；定义 faithfulness/relevance/citation。 |
| D240 | R21 跑 RAGAS 或自建评测脚本；人工抽检自动分数。 |
| D241 | 建 80～100 条问题集：事实、多跳、无答案、对抗输入。 |
| D242 | chunk size/overlap/top-k/rerank 消融；只改一个变量。 |
| D243 | **休息**。 |
| D244 | 提示注入测试、权限/数据隔离设计；加入拒绝策略。 |
| D245 | 题 102～104；输出 RAG 实验报告；周复盘。 |

#### W36（2027-05-26 ～ 2027-06-01）｜项目 5：可评测知识库 I

| 日 | 任务 |
|---|---|
| D246 | 选公开、许可明确文档；写用户故事、验收指标与架构图。 |
| D247 | 实现增量 ingest、清洗、chunk、metadata、向量索引。 |
| D248 | 实现 hybrid search/rerank，输出引用和原文定位。 |
| D249 | 实现 answer/abstain、对话历史边界；写 10 个集成测试。 |
| D250 | **休息**。 |
| D251 | FastAPI：上传/索引/查询/健康检查；异常与日志。 |
| D252 | 题 105～107；中期演示与风险清单。 |

#### W37（2027-06-02 ～ 2027-06-08）｜项目 5：可评测知识库 II

| 日 | 任务 |
|---|---|
| D253 | Gradio UI：来源、分数、耗时；核心逻辑不得写进 UI。 |
| D254 | 运行冻结评测集，输出 retrieval/generation 分层指标。 |
| D255 | 错误分析 30 例，修复最高频一类并复测。 |
| D256 | 性能：缓存、批量 embedding、并发基础；测 p50/p95。 |
| D257 | **休息**。 |
| D258 | Dockerfile、环境变量、持久卷；本机全新启动验证。 |
| D259 | README/设计文档/演示视频；题 108～110；准备答辩。 |

#### W38（2027-06-09 ～ 2027-06-15）｜RAG 答辩与真实约束

| 日 | 任务 |
|---|---|
| D260 | **里程碑 6 答辩**：为什么此 embedding/chunk/top-k/指标？ |
| D261 | 多租户、权限、删除、更新、审计日志的系统设计。 |
| D262 | 成本/延迟/质量权衡；即使本地模型也估算资源成本。 |
| D263 | 比较 naive RAG 与改进版，形成简历 STAR 描述。 |
| D264 | **休息**。 |
| D265 | 修复答辩暴露问题，发布项目 5 v1.0。 |
| D266 | 月考 9；题 111～113；汇总 RAG 面试题。 |

### 阶段 E：Agent、AI 工程与部署（W39–W47）

#### W39（2027-06-16 ～ 2027-06-22）｜Agent 原理：先不用框架

| 日 | 任务 |
|---|---|
| D267 | R18 Unit 1：model/tool/action/observation；画 agent loop。 |
| D268 | P11 ReAct：reasoning＋acting 思路、实验与局限；论文卡。 |
| D269 | Python 手写 tool registry、JSON schema、dispatcher，不用框架。 |
| D270 | 加 observation、max steps、timeout、错误重试与终止条件。 |
| D271 | **休息**。 |
| D272 | 写 calculator/search/local-file 三个安全工具及单元测试。 |
| D273 | 题 114～116；用 20 个任务测成功率，归类失败。 |

#### W40（2027-06-23 ～ 2027-06-29）｜Agent 框架与状态

| 日 | 任务 |
|---|---|
| D274 | R18 Unit 2：smolagents/LlamaIndex/LangGraph 只比较抽象与用途。 |
| D275 | R19 LangGraph quickstart：state/node/edge/conditional edge。 |
| D276 | 实现带 checkpoint 的单 Agent 工作流，可中断恢复。 |
| D277 | memory：短期状态、长期存储、摘要；明确什么不该记。 |
| D278 | **休息**。 |
| D279 | human-in-the-loop：高风险工具执行前审批，记录审计日志。 |
| D280 | 月考 10；题 117～119；画 Agent 状态机。 |

#### W41（2027-06-30 ～ 2027-07-06）｜Agent 评测、安全与可观测

| 日 | 任务 |
|---|---|
| D281 | 为 Agent 定义 task success、tool accuracy、steps、latency 指标。 |
| D282 | 建 50 个正常/失败/对抗任务，运行可重复评测。 |
| D283 | prompt injection、工具参数注入、越权；设计 allowlist/sandbox 思路。 |
| D284 | tracing：保存每步输入、调用、观察、错误，但不记录秘密。 |
| D285 | **休息**。 |
| D286 | 比较固定 workflow 与 agent；写“何时不该用 Agent”。 |
| D287 | 题 120～122；修复最常见失败并复测。 |

#### W42（2027-07-07 ～ 2027-07-13）｜Agent 项目原型

| 日 | 任务 |
|---|---|
| D288 | 选择场景：研究助手/文档审查/数据分析助手；写用户故事与非目标。 |
| D289 | 先做 deterministic workflow baseline，再加 Agent 决策。 |
| D290 | 工具 schema、输入验证、timeout/retry/idempotency。 |
| D291 | 加 RAG 或 SQL 工具；所有写操作默认模拟/需人工批准。 |
| D292 | **休息**。 |
| D293 | 评测集、tracing、错误分类；跑第一版基线。 |
| D294 | 题 123～125；中期演示，决定保留/删除哪些复杂性。 |

#### W43（2027-07-14 ～ 2027-07-20）｜后端基础

| 日 | 任务 |
|---|---|
| D295 | HTTP/REST、JSON、状态码、同步/异步；用 curl/Postman 调 API。 |
| D296 | R26 FastAPI path/query/body、Pydantic、异常；写 5 个 endpoint。 |
| D297 | dependency injection、配置与 secret；`.env.example` 不提交密钥。 |
| D298 | SQL 基础 R25：SELECT/JOIN/GROUP BY/子查询；完成前 12 课。 |
| D299 | **休息**。 |
| D300 | SQLite/PostgreSQL 概念；为对话、文档、评测设计 schema。 |
| D301 | 月考 11；题 126～128；API＋数据库集成测试。 |

#### W44（2027-07-21 ～ 2027-07-27）｜软件质量与协作

| 日 | 任务 |
|---|---|
| D302 | pytest fixture/mock/parametrize；给项目关键路径补测试。 |
| D303 | typing、ruff/formatter、pre-commit；修静态检查。 |
| D304 | Git branch/rebase/merge/PR/code review；模拟 feature PR。 |
| D305 | CI：GitHub Actions 跑 lint＋test（若不便则本地脚本等价验证）。 |
| D306 | **休息**。 |
| D307 | 日志、错误码、健康检查、指标；禁止日志泄漏 prompt/密钥。 |
| D308 | 题 129～131；从空目录复现项目；周复盘。 |

#### W45（2027-07-28 ～ 2027-08-03）｜Docker 与服务化

| 日 | 任务 |
|---|---|
| D309 | R27 image/container/layer/volume/network；完成官方入门。 |
| D310 | 为 FastAPI 写 Dockerfile、`.dockerignore`、非 root 用户。 |
| D311 | Compose 启 API＋数据库/向量库；健康检查和持久化。 |
| D312 | CPU/GPU 容器差异、NVIDIA Container Toolkit 概念；Windows 用 WSL2。 |
| D313 | **休息**。 |
| D314 | 负载测试：并发、p50/p95、吞吐、错误率；生成报告。 |
| D315 | 题 132～134；月度依赖更新与漏洞检查；复盘。 |

#### W46（2027-08-04 ～ 2027-08-10）｜推理性能、量化与 ONNX

| 日 | 任务 |
|---|---|
| D316 | 量化 PTQ/QAT、INT8/INT4、精度/速度/显存权衡。 |
| D317 | Transformers bitsandbytes/torchao 任选可用方案，比较显存与质量。 |
| D318 | R32 导出一个模型到 ONNX Runtime，对齐输出误差。 |
| D319 | batching、continuous batching、KV cache；计算吞吐/延迟权衡。 |
| D320 | **休息**。 |
| D321 | P13：FlashAttention 的 IO-awareness 直觉；论文卡。 |
| D322 | 题 135～137；性能表：PyTorch/量化/ONNX（可运行项）。 |

#### W47（2027-08-11 ～ 2027-08-17）｜Agent 项目发布

| 日 | 任务 |
|---|---|
| D323 | 完成 Agent 项目核心功能，删除不稳定的“炫技”功能。 |
| D324 | 冻结评测集运行，报告成功率、步骤、延迟和失败案例。 |
| D325 | 安全测试：提示注入、越权工具、恶意参数、无限循环。 |
| D326 | Docker Compose、一键启动、API 文档和简单 UI。 |
| D327 | **休息**。 |
| D328 | README/架构/威胁模型/演示视频/简历描述。 |
| D329 | **里程碑 7 答辩**；题 138～140；发布项目 6。 |

### 阶段 F：作品集、面试与求职闭环（W48–W53）

#### W48（2027-08-18 ～ 2027-08-24）｜MLOps/LLMOps 最小闭环

| 日 | 任务 |
|---|---|
| D330 | 数据/代码/模型版本，experiment→registry→deployment 流程图。 |
| D331 | R29 MLflow：tracking、artifact、model registry；接入一个项目。 |
| D332 | 模型/Prompt/RAG 版本与回滚；写 release checklist。 |
| D333 | 线上监控：延迟、错误、漂移、质量反馈、成本；定义告警。 |
| D334 | **休息**。 |
| D335 | 为项目实现最小 CI/CD 设计（无需购买云服务）。 |
| D336 | 月考 12；题 141～143；写事故复盘模板。 |

#### W49（2027-08-25 ～ 2027-08-31）｜毕业项目选题与设计

| 日 | 任务 |
|---|---|
| D337 | 审计 6 个项目，按岗位价值/深度/完成度打分；选 1 个升级为毕业项目。 |
| D338 | 阅读 20 条真实 AI 岗 JD，统计技能频率；调整但不追热点重写全年。 |
| D339 | 写 PRD：用户、痛点、场景、非目标、成功指标、风险。 |
| D340 | 架构设计：数据、模型/RAG/Agent、API、存储、评测、监控。 |
| D341 | **休息**。 |
| D342 | 建 backlog，切分 Must/Should/Could；完成可运行骨架。 |
| D343 | 题 144～145；设计评测集与 baseline；设计评审。 |

#### W50（2027-09-01 ～ 2027-09-07）｜毕业项目冲刺 I

| 日 | 任务 |
|---|---|
| D344 | 完成数据/ingest/模型接口主链路；当天必须端到端跑通。 |
| D345 | 完成核心 AI 能力与 baseline；保存首份评测结果。 |
| D346 | 加评测、tracing、错误处理；至少 20 个自动测试。 |
| D347 | 做一次性能/质量消融，依据结果而非感觉优化。 |
| D348 | **休息**。 |
| D349 | 完成 API/UI/Docker；全新环境一键启动。 |
| D350 | 题 146～147；同行视角自评：删掉无法解释的功能。 |

#### W51（2027-09-08 ～ 2027-09-14）｜毕业项目冲刺 II

| 日 | 任务 |
|---|---|
| D351 | 冻结 eval set；最终运行质量、延迟、吞吐、显存与失败分析。 |
| D352 | 红队：注入、越权、隐私、异常文件、并发、断网/模型失败。 |
| D353 | 修最高风险问题；回归测试，禁止临近发布大改架构。 |
| D354 | 完成 README、架构图、API 文档、模型/数据卡。 |
| D355 | **休息**。 |
| D356 | 录 8 分钟演示＋技术讲解；发布 v1.0。 |
| D357 | **毕业答辩**：30 分钟陈述＋30 分钟自问自答；题 148。 |

#### W52（2027-09-15 ～ 2027-09-21）｜求职材料与模拟面试

| 日 | 任务 |
|---|---|
| D358 | 一页中文简历：教育/技能/3 个强项目；每条写动作＋方法＋量化结果。 |
| D359 | GitHub 清理：置顶 4～6 个项目，统一 README、截图、许可和启动命令。 |
| D360 | ML/DL 模拟面试 60 分钟；回放并补 10 个薄弱点。 |
| D361 | LLM/RAG/Agent/系统设计模拟面试 90 分钟；书面复盘。 |
| D362 | **休息**。 |
| D363 | 编程模拟：2 题/90 分钟；项目深挖模拟：30 分钟。 |
| D364 | 题 149～150；月考 13；做岗位清单与投递节奏。 |

#### W53（2027-09-22）｜D365 年度验收

| 日 | 任务 |
|---|---|
| D365 | 上午/晚间分块完成：重画 AI 全景图；现场搭一个最小 RAG 或模型 API；复盘 365 天证据；用第 7 节评分表决定“开始投递/补 4 周/调整岗位”。 |

---

## 5. 150 道算法题分布与题型

以 R22 为知识主线，在 LeetCode 中国站或同类平台练习。题号不是指定平台编号，而是你的累计计数。

| 累计题数 | 重点 |
|---:|---|
| 1～20 | 数组、字符串、哈希、双指针、复杂度 |
| 21～41 | 链表、栈、队列、二分、排序 |
| 42～62 | 树、DFS/BFS、堆、递归 |
| 63～83 | 回溯、贪心、区间、前缀和 |
| 84～104 | 动态规划基础、图、拓扑排序 |
| 105～125 | 高频综合题与错题二刷 |
| 126～140 | 限时面试题，每题先口述复杂度和测试 |
| 141～150 | 模拟面试：45 分钟内沟通、编码、测试、优化 |

每题记录：题意压缩、第一思路、正确解、时间/空间复杂度、错因、二刷日期。连续 20 分钟无思路可看提示，禁止为了“独立做出”耗掉整晚。

---

## 6. 月考、答辩题与参考答案

### 月考 1（D28）：AI/数据/数学

1. **训练集、验证集、测试集分别做什么？** 参考：训练拟合参数；验证选择模型/超参/阈值；测试只用于最终无偏估计，不能反复据其调参。
2. **为什么 softmax 要减最大 logit？** 参考：平移不改变概率，减最大值可避免 `exp` 上溢并改善数值稳定性。
3. **什么是数据泄漏？** 参考：训练阶段直接或间接用了推理时不可获得的信息；包括全数据预处理、目标编码越界、时间穿越等。

### 月考 2（D70）：MLP/优化

1. **反向传播是什么？** 参考：在计算图上应用链式法则，反向累积每个参数对标量损失的梯度。
2. **AdamW 与 Adam＋L2 的关键区别？** 参考：AdamW 将权重衰减从自适应梯度更新中解耦。
3. **训练 loss 不降如何排查？** 参考：先过拟合单 batch，再查标签/shape/loss/梯度/lr/数据范围/train 模式；每次只改一项。

### 月考 3（D105）：CNN/RNN

1. **残差连接为何有效？** 参考：提供恒等捷径、改善梯度传播，让层学习残差函数；不能简单回答“防止梯度消失”。
2. **BatchNorm 的 train/eval 差异？** 参考：训练用 batch 统计并更新 running stats；推理使用累积统计。
3. **LSTM 比普通 RNN 改进何处？** 参考：通过 cell state 与门控控制写入/遗忘/输出，形成更稳定的长期梯度路径。

### 月考 4（D140）：NLP/BERT

1. **BERT 与 GPT 的 mask/目标差异？** 参考：BERT 双向 encoder＋MLM；GPT causal decoder＋next-token prediction。
2. **subword tokenizer 的价值？** 参考：在词表大小和序列长度之间折中，并缓解 OOV；不等于真正理解词义。
3. **文本分类为何优先建 TF-IDF 基线？** 参考：便宜、快速、可解释，能暴露数据和切分问题，为复杂模型提供比较下限。

### 月考 5（D168）：Transformer

1. **为何除以 `sqrt(d_k)`？** 参考：维度增大时点积方差增大，缩放避免 softmax 饱和、梯度过小。
2. **causal mask 做什么？** 参考：使位置 t 只能关注不晚于 t 的 token，保持自回归因果性。
3. **多头的价值？** 参考：在不同投影子空间并行学习不同关系；不是简单重复同一 attention。

### 月考 6（D196）：预训练/HF

1. **perplexity 是什么？** 参考：平均负对数似然的指数；越低表示在同 tokenizer/数据定义下预测性更好，跨 tokenizer 不宜直接比。
2. **为什么小型 GPT 项目有价值但不是“大模型预训练经验”？** 参考：流程和核心原理一致，但数据、算力、分布式、稳定性和规模工程完全不同，简历必须诚实表述。
3. **checkpoint 应保存什么？** 参考：模型、优化器、scheduler、scaler、step/epoch、RNG 状态和配置，确保真正恢复。

### 月考 7（D210）：微调

1. **LoRA 为什么省显存？** 参考：冻结基座，仅训练低秩增量矩阵，显著减少梯度和优化器状态；激活仍占显存。
2. **QLoRA 的核心？** 参考：量化冻结基座并训练 LoRA，结合 NF4 等技术降低显存；量化误差需评测。
3. **何时不该微调？** 参考：知识需要频繁更新、问题可由检索/提示解决、数据少且质量差、无可靠评测时。

### 月考 8（D238）：RAG

1. **RAG 失败应先看哪里？** 参考：先判检索是否召回答案，再判上下文下生成是否忠实；分层诊断。
2. **chunk 越小越好吗？** 参考：小块更精确但上下文可能破碎；大块信息完整但噪声与成本更高，必须在冻结评测集上选。
3. **无答案问题怎么处理？** 参考：检索阈值/证据充分性判断、明确拒答、引用支持，评测 abstention precision/recall。

### 月考 9（D266）：高级 RAG

1. **hybrid search 的动机？** 参考：稀疏检索擅长精确词/编号，稠密检索擅长语义；融合提高互补召回。
2. **reranker 放在哪里？** 参考：初检取较多候选后，用更贵的交叉编码器重排，再送少量上下文给生成器。
3. **如何防文档提示注入？** 参考：把文档视为不可信数据，分隔指令与内容、权限隔离、工具 allowlist、检测与评测；不能只靠一句 system prompt。

### 月考 10（D280）：Agent

1. **Agent 与 workflow 区别？** 参考：workflow 路径预定义、可控；Agent 根据状态动态选择动作，灵活但更难评测和约束。
2. **工具为什么需要 schema？** 参考：约束名称、参数类型与含义，便于验证、解析和拒绝非法调用。
3. **如何避免无限循环？** 参考：max steps/time/token budget、重复动作检测、明确终止状态、失败降级和人工介入。

### 月考 11（D301）：后端

1. **异步何时有用？** 参考：等待网络/磁盘等 I/O 时提高并发；不会让 CPU/GPU 密集计算自动变快。
2. **幂等性是什么？** 参考：同一请求执行多次与一次的外部效果一致；重试型工具尤其重要。
3. **密钥如何管理？** 参考：环境变量/secret manager、最小权限、轮换、日志脱敏；绝不提交仓库或写进镜像。

### 月考 12（D336）：部署/MLOps

1. **p50 与 p95 为什么都要看？** 参考：p50 代表典型体验，p95 暴露尾延迟；平均值可能掩盖坏体验。
2. **量化的代价？** 参考：可能降低精度或改变输出，算子/硬件支持不同；必须按任务质量和真实延迟验证。
3. **发生质量回退如何回滚？** 参考：版本化模型/Prompt/索引/数据，保留前一稳定制品与兼容 schema，以指标触发或人工切回。

### 月考 13（D364）：综合

1. 从业务目标到 AI 系统上线说完整流程。评分点：问题/指标→数据→baseline→训练/检索→离线评测→错误分析→服务→安全→监控→反馈/回滚。
2. 设计一个企业知识助手。评分点：权限、解析、索引、混合召回、重排、引用/拒答、评测、注入防护、日志与更新删除。
3. 微调、RAG、Prompt 如何选择？评分点：行为/格式稳定改变偏微调；动态/私有知识偏 RAG；简单任务先 Prompt；组合前必须有 baseline 与 eval。

### 项目统一答辩问题（每次都回答）

1. 用户是谁，为什么需要它？不用 AI 的 baseline 是什么？
2. 数据来自哪里，许可和泄漏风险是什么？
3. 主指标为什么匹配目标？结果是否可复现？
4. 你亲自做了什么？最难的 bug、失败实验和取舍是什么？
5. 线上会怎么失败？如何监控、降级、回滚？
6. 如果多给一周，最高收益的改进是什么？证据是什么？

---

## 7. 最终评分表与求职门槛

每项 0～4 分：0 不会；1 能复述；2 能照教程完成；3 能独立完成并解释；4 能评测、排错、权衡和改进。

| 能力 | 权重 | 最低目标 |
|---|---:|---:|
| Python/数据/Git/Linux/SQL | 10% | 3 |
| 经典 ML 与评测 | 10% | 3 |
| PyTorch/DL/Transformer 原理 | 15% | 3 |
| LLM 预训练/微调/评测 | 20% | 3 |
| RAG/Agent | 20% | 3 |
| API/Docker/测试/性能/MLOps | 15% | 3 |
| 项目表达/算法题/面试 | 10% | 3 |

- 加权分 ≥3.2，且所有核心项目可运行：开始主投 A 类岗位。
- 2.7～3.19：开始试投，同时用 4 周补最低两项。
- <2.7：不要再刷新课程；用 6～8 周补作品闭环和独立实现能力。

---

## 8. 每周复盘模板

```markdown
## Week N Review
- 本周计划完成率：__/6
- 可验证产物（链接/commit）：
- 我现在能闭卷解释：
- 最重要的实验结论：
- 最高频错误及根因：
- 算法题累计：__/150
- 下周只调整一件事：
- BACKLOG（不阻塞主线）：
```

## 9. 反馈后如何滚动修改

每 4 周向路线图维护者反馈：实际有效时长、完成天数、项目链接、月考得分、最难主题、最喜欢/最排斥任务。修改规则：

1. 完成率 85%～110%：保持节奏，只替换失效资源。
2. 完成率 65%～84%：下一周期删 20% 补充阅读，不删核心编码与项目验收。
3. 完成率 <65%：整体顺延，不压缩休息，不用倍速视频“补进度”。
4. 连续两个月超前：增加项目深度/评测，不盲目新增方向。
5. 市场变化：只在 W49 的 JD 审计或每季度复盘调整技术栈；基础、评测和工程能力不追热点。

---

## 10. 重要现实边界

- 4060 Ti 16GB 足够完成 PyTorch、CV、小型 GPT 从零训练、小模型 LoRA/QLoRA、本地 RAG 与量化实验；不适合真正工业规模的大模型预训练。
- “从零预训练”在本路线中指完整掌握数据、tokenizer、Transformer、优化、checkpoint、评测和生成流程，简历应写“小型 GPT 预训练实验”，不能写成大模型训练经验。
- Windows 可完成多数任务；Docker/GPU 推理或部分量化库遇到兼容问题时，优先 WSL2、Colab 或 Kaggle 免费环境，不在环境问题上耗费一整周。
- 免费 Colab/Kaggle 的 GPU 类型、时长和配额会变化；任何长训练都要支持 checkpoint/resume，不把免费资源可用性当作项目成功前提。
- 课程链接与框架版本会变化。遇到 API 变化时以同一项目的最新官方文档为准，并在月度复盘更新链接。

> 这份路线图不是“必须完美执行的合同”，而是一套可验证的训练系统。真正的目标不是第 365 天把所有方框打勾，而是能独立把一个 AI 问题做成可靠、可评测、可部署、讲得清楚的作品。
