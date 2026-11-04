# CVPR 2025–2026 VLA 写作实例

阅读依据：2026-11-04 查阅的六篇 CVF 正式版论文，重点为引言、方法组织、贡献列表与实验叙事。下列内容是写作观察；目标会议的强制要求应另查当届官方指南。

| 论文 | 发表记录与正文 | 可借鉴的组织方式 |
|---|---|---|
| CoT-VLA: Visual Chain-of-Thought Reasoning for Vision-Language-Action Models | CVPR 2025，1702–1713。[正文](https://openaccess.thecvf.com/content/CVPR2025/papers/Zhao_CoT-VLA_Visual_Chain-of-Thought_Reasoning_for_Vision-Language-Action_Models_CVPR_2025_paper.pdf) | 引言 §1 先确立子目标图像这一中间表示，再解释动作生成与视频数据利用；实验 §4 用问题串联整体比较、消融与能力分析。 |
| ShowUI: One Vision-Language-Action Model for GUI Visual Agent | CVPR 2025，19498–19508。[正文](https://openaccess.thecvf.com/content/CVPR2025/papers/Lin_ShowUI_One_Vision-Language-Action_Model_for_GUI_Visual_Agent_CVPR_2025_paper.pdf) | 引言 §1 将视觉开销、交错历史和数据选择拆开，对应 §2 的设计；反复使用相同模块名称，使问题与解法容易对应。 |
| MoManipVLA: Transferring Vision-language-action Models for General Mobile Manipulation | CVPR 2025，1714–1723。[正文](https://openaccess.thecvf.com/content/CVPR2025/papers/Wu_MoManipVLA_Transferring_Vision-language-action_Models_for_General_Mobile_Manipulation_CVPR_2025_paper.pdf) | 引言 §1 将缺口收束到固定底座策略的移动操作迁移；§3 按策略接口、物理约束、优化流程展开，贡献条目区分框架、目标与验证。 |
| Fast-ThinkAct: Efficient Vision-Language-Action Reasoning via Verbalizable Latent Planning | CVPR 2026，5070–5081。[正文](https://openaccess.thecvf.com/content/CVPR2026/papers/Huang_Fast-ThinkAct_Efficient_Vision-Language-Action_Reasoning_via_Verbalizable_Latent_Planning_CVPR_2026_paper.pdf) | 引言 §1 围绕推理收益与延迟形成张力；§3 把紧凑表示、蒸馏监督和动作策略衔接起来，操作动词说明各步职责。 |
| Global Prior Meets Local Consistency: Dual-Memory Augmented Vision-Language-Action Model for Efficient Robotic Manipulation（OptimusVLA） | CVPR 2026，35135–35145。[正文](https://openaccess.thecvf.com/content/CVPR2026/papers/Li_Global_Prior_Meets_Local_Consistency_Dual-Memory_Augmented_Vision-Language-Action_Model_for_CVPR_2026_paper.pdf) | 引言 §1 的两个限制分别对应 GPM、LCM；时间依赖的解释包含具体任务阶段与控制后果。§4 分别检查性能、效率与模块作用。 |
| ForeAct: Steering Your VLA with Efficient Visual Foresight Planning | CVPR 2026，37195–37205。[正文](https://openaccess.thecvf.com/content/CVPR2026/papers/Zhang_ForeAct_Steering_Your_VLA_with_Efficient_Visual_Foresight_Planning_CVPR_2026_paper.pdf) | 引言 §1 用清理桌面的情景解释分步视觉目标；方法与实验分别交代预测、策略接入及部署，效率结果附带硬件条件。 |

## 将实例转化为写作选择

- 学习问题与设计的对应、信息推进和证据安排；按用户偏好选择直接陈述或例子驱动的叙述。
- 句子主语通常承担计算职责，术语沿信息流复用。将模块的输入、操作、输出和作用交代清楚。
- 段落数量、贡献条目数量、相关工作的位置及开场方式随论文变化。六篇实例不能推出统一的强制格式。
- 对形容词、设问、宽泛开场和强创新措辞独立判断；正式发表不意味着每一处表达都适合当前稿件。
- 不把 VLA 的动作空间、记忆结构、推理机制等领域细节推广成其他学科的硬性写作要求。
