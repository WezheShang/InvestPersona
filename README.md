# InvestPersona

A 股投资领域的 LLM Skill 库：把「人物交易智慧」与「方法论体系」分别蒸馏成可直接挂载到 LLM agent 上的 skill。

## 仓库结构

```
InvestPersona/
├── README.md                  # 本文件
├── LICENSE                    # 代码/结构：AGPL-3.0
├── CONTENT_LICENSE            # 内容：CC BY-NC-SA 4.0
├── personas/                  # 人物 persona（多源调研产线）
│   ├── yangjia/               # 炒股养家
│   └── jiangzhi-qishui/       # 姜汁汽水（B 站时政/宏观 UP 主）
└── methods/                   # 方法论体系（书籍蒸馏产线）
    └── prism/                 # 多棱镜：多流派技术分析调度系统
```

## 两条产线

本仓库的 skill 来自两条不同的构建产线，按「对象是否含有人的要素」分流：

### 产线 1：人物 persona（personas/）

**对象是人**——表达风格、心智模型、决策记录、他人评价。素材是该人物的全部公开产出（帖子 / 视频 / 图文 / 演讲），产线为多源调研 → 心智模型 + 启发式 + 表达 DNA 提炼 → 可对话的 persona skill。

| Skill | 对象 | 产物 |
|---|---|---|
| [personas/yangjia](personas/yangjia/) | A 股游资「炒股养家」 | 6 心智模型 + 10 启发式 + 表达 DNA |
| [personas/jiangzhi-qishui](personas/jiangzhi-qishui/) | B 站时政/宏观 UP 主「战国时代_姜汁汽水」 | 5 心智模型 + 8 启发式 + 表达 DNA |

### 产线 2：方法论蒸馏（methods/）

**对象是体系**——经典技术分析著作的共识方法。素材是原书（OCR / 精读），产线为逐书精读 → 跨书交叉蒸馏成「专册」（多源共识标注，单源内容标 [单源]）→ 由调度器统一编排成可执行的判定规则。

| Skill | 内容 |
|---|---|
| [methods/prism](methods/prism/) | 多流派技术分析调度系统：道氏 / 威科夫 / Sperandeo / Murphy / Edwards & Magee / 量价六源共识 / 养家心法，7 本专册 |

### 为什么分两条产线

方法论没有「表达 DNA」「决策案例」「人格」这些人的要素，硬套 persona 模板只会稀释方法本身；反过来，一个人的交易智慧也无法只靠书籍共识还原。**同一对象可双形态并存**——养家既有 persona 版（personas/yangjia/），其心法也作为 prism 的第六柱专册（methods/prism/references/yangjia-xinfa.md）参与方法论调度。

## 使用方式

每个 skill 目录就是标准 skill 包（SKILL.md + 可选 references/），把对应目录复制到你的 agent skills 目录即可：

```
<your-agent>/skills/prism/               # methods/prism 的 SKILL.md + references/
<your-agent>/skills/yangjia/             # personas/yangjia 的 SKILL.md
```

各 skill 的依赖、数据接入、preconditions 见其目录下的 README.md。

## 通用 Limitations

- 所有 skill 的素材都有**时间窗口截止**，窗口之后的变化不在覆盖范围（各目录 README 标注具体截止日）
- persona skill 是**蒸馏复刻而非本人**，观点以原始素材为准
- 一手素材（书籍原文 / 视频转录 / OCR）因版权原因均**不随仓库分发**，仓库只含蒸馏产物
- 仅供学习研究，**不构成投资建议**

## License

- 代码与仓库结构：AGPL-3.0（见 [LICENSE](LICENSE)）
- 文档内容（SKILL.md / README / 专册）：CC BY-NC-SA 4.0（见 [CONTENT_LICENSE](CONTENT_LICENSE)）

## 致谢

感谢 **Irene** 对本项目产线设计与内容口径的把关。
