# 句式与段落参考

以下英文均为原创示例；按实际方法、证据和术语改写，不逐句套用。

## 按句子任务选择骨架

| 任务 | 常用骨架 | 示例 |
|---|---|---|
| 声明设计 | We introduce/design … | We introduce a gated recurrent memory for long-horizon control. |
| 定义操作 | Module + verb + object | The encoder maps observations and instructions to contextualized features. |
| 交代目的 | To achieve X, we perform Y. | To preserve recent visual detail, we update the short-term state more frequently. |
| 解释机制 | Operation, followed by its role | The gate merges incoming evidence with the previous state to update the memory. |
| 说明时间或条件 | When/Every/At …, operation | At each consolidation step, the long-term state incorporates the short-term memory. |
| 交代设置 | Object + passive construction | The policy is trained to predict action sequences over a longer horizon. |
| 报告结果 | In setting X, method changes metric Y relative to baseline Z. | 在实际任务、指标和对照齐全后写出比较，不把示例补成虚构结果。 |

不同句子可以分别以作者、模块、输入或状态开头。根据叙述焦点选择主语，避免所有句子都以 We 或 This 开头。

## 信息承接

连续句子的对象有意复用，输出与下一步操作保持可追踪：

> A task-conditioned encoder processes visual observations and executed actions. A Q-Former compresses the resulting features into candidate memory tokens. Gated updates merge these candidates with the previous state. The policy reads the updated memory to predict actions.

该示例展示“输入 → 特征 → 候选表示 → 状态 → 动作”的阅读顺序。真实系统若异步读写，应改为读取最新可用状态，并准确交代提交与读取的时序。

复用术语前先分清对象。例如，history 表示原始历史，memory state 表示递归状态，memory tokens 表示其向量载体，memory encoder 表示计算模块。这些词可以相关，但不作为随意替换的同义词。

## 段落按功能组织

### 问题或局限

可采用“明确判断 → 具体情景或机制 → 对任务的后果 → 设计需求”。保留有助于建立因果关系的环节，不强行补齐四句话。

> A short observation window loses evidence once it leaves the context. In a search task, a previously explored route may then become indistinguishable from an unvisited one. The policy needs a compact state that preserves exploration progress.

具体例子用于解释信息需求；实验结论仍由当前论文的数据支撑。

### 方法概述

先明确改变了什么，再交代输入、核心操作、状态流与输出。引言选择足以理解设计的细节；超参数、完整公式和训练调度放到合适的方法小节。

> The memory module maintains a fixed-size recurrent state. An encoder compresses new observations and actions into candidate tokens, which gated updates integrate with the previous state. The action policy reads the latest available memory while the encoder processes incoming observations.

双时间尺度方法还需明确长期状态如何接收短期状态；不能只列出两组记忆的名称。

### 相关工作

围绕当前问题比较不同路线的表示、信息来源、更新方式和开销。每项比较对应具体论文及其实际设置；每段末尾收束到当前问题需要的能力。

### 结果

按“回答的问题 → 关键比较 → 结果范围或解释”组织。结论紧邻表格或图中的证据；组件消融、整体收益和因果解释分别陈述。

### 贡献列表

条目采用一致的句法起点，如全部用 We introduce …，或全部用名词短语。每项贡献写出不同的机制、监督或能力，避免三个条目反复改写“提高性能”。

## 动词与论断强度

优先让动词对应操作对象：

- encode observations / instructions；compress features / history。
- update states；retrieve entries；aggregate evidence。
- condition action prediction on memory；align representations / trajectories。
- optimize an objective；reduce a measured error；improve a named metric。

检查从动词到证据的距离：

- **实现**：使用门控、投影或异步调度等已确认的操作，可直接陈述。
- **训练目标**：用 is trained to retain … 或 receives supervision for …，明确这是监督目的。
- **观察**：用 retains …、improves … 时，对应实际评测。
- **解释**：当机制解释尚非直接证明时，用 suggests … 等与证据相称的表达。

## 容易改变技术含义的润色

| 输入表述 | 编辑判断 |
|---|---|
| “异步，所以没有任何额外延迟。” | 分别说明执行重叠和实际测得的关键路径影响。只有相应测量支持时再报告零增加。 |
| “SFT 对不同轨迹错误施加相同惩罚。” | 核实目标函数；若材料仅说明 token 级监督缺少轨迹目标，应表述为不直接优化轨迹误差。 |
| “压缩后没有信息损失。” | 区分理论无损保证、某项任务指标保持，以及训练时希望保留的信息。 |
| “提升若干百分比。” | 明确是百分比相对变化还是百分点绝对变化，并保留比较基线。 |
| “显著提升。” | 对应统计显著性检验或明确数值证据；根据论文原意选择准确用词。 |

## 语言节制

- 删除可省略的元叙述，如 It is important to note that …，以及反复介绍下一段要做什么的句子。
- 保留有作用的连接词：However 标记限制，Specifically 引出操作，Consequently 说明已经建立的因果结果。关系足够清楚时直接承接。
- 用技术属性替代无具体含义的自我评价，如 recurrent、task-conditioned、fixed-size；核实它们确实描述当前方法。
- 对必要限制、真实对比、行业标准词和长句逐项判断，不实施绝对禁词、固定句长、统一段数或标点配额。
