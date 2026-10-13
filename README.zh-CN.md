# Academic Story Writing

**像科研作者一样组织论证，而不是提前回应一个想象中的审稿人。**

面向 **计算机科学 / 人工智能 / 机器学习研究者** 的 Codex 学术写作 Skill：将研究笔记整理成论文正文，强化有证据支持的科学论点，也可以只优化选中的一句话、一段文字或 LaTeX 片段。

**Scientist-first · Story-driven · Evidence-calibrated**

[English](README.md) · [快速开始](#快速开始) · [修改前后对比](#修改前后对比受控实验) · [工作流程](#工作流程) · [核心能力](#核心能力) · [示例](#示例)

## 快速开始

在本仓库的本地目录中，将 Skill 复制到论文项目：

```bash
mkdir -p /path/to/paper/.agents/skills
cp -R skills/academic-story-writing /path/to/paper/.agents/skills/
```

Windows 用户可以通过文件资源管理器或 PowerShell，将 `skills/academic-story-writing/` 复制到 `<论文项目>/.agents/skills/academic-story-writing/`。安装后重新启动或刷新 Codex 会话。

**从实验笔记生成 Results：**

```text
$academic-story-writing
PRESERVE + WRITER. 根据以下笔记撰写简洁的 Results 段落。
清楚说明受控比较的发现，以及它如何支持论文主线。
结论限定在实际测试范围内；不要虚构数值或想象审稿意见。

[粘贴实验笔记]
```

**仅优化指定 LaTeX 段落：**

```text
$academic-story-writing
PRESERVE + EDITOR. 仅 POLISH 以下 LaTeX 段落。
保留公式、引用、数值、技术含义和已有依据的主张力度。

[粘贴选中段落]
```

## 为什么需要它？

学术写作的核心是**阐述论文贡献，以及证据为什么支持这些贡献**。但 AI 容易在写作时预设 Reviewer：把已经成立的结论写弱，为使用标准组件反复辩解，不断声明理论没有证明什么，或者不区分实验目标就要求更多 seeds、datasets 和 ablations。

Academic Story Writing 将**科研论证的构建**与**审稿式批评**分开。它既不因想象中的质疑而自动弱化贡献，也不允许无依据地宣称创新性、理论保证或实验优势。目标是写出清晰、连贯、经得起实际证据检查的 scientific story。

## 修改前后对比：受控实验

*以下完全是虚构示例，不代表真实论文或 Skill 效果评测。* 在数据集 D 上进行消融实验，固定数据划分、训练协议、评估指标和随机种子，唯一指定的区别是是否启用模块 X。准确率分别为 **81.2%（启用 X）** 和 **79.8%（不启用 X）**。

**过度防御的写法：**
> 观察到的提升可能与数据集特性有关，因此在更多数据集和随机种子上实验之前，我们无法得出结论。

**基于证据的写法：**
> 在数据集 D 的一致评估协议下，启用模块 X 将准确率从 79.8% 提高至 81.2%，提升 1.4 个百分点。该结果支持 X 在所测试配置下对性能的贡献。

这个结果可以直接说明**当前受控设置中的观察**，但不等于已经证明跨随机种子稳定或跨数据集泛化。只有提出这些更强的主张时，才需要与之匹配的进一步证据。[查看完整实验示例 →](examples/experimental-writing.md)

## 工作流程

**从用户指定的修改范围出发，经过写作和必要的科学检查，但不自动切换成 Reviewer 模式。**

![Academic Story Writing 工作流程：输入范围、写作原则、模式选择、规划、撰写、科学检查与交付](assets/workflow.png)

[查看高清流程图](assets/workflow.png)

两个模式轴彼此独立：**Story Mode**（`PRESERVE` 默认、`DISCOVER`、`REFRAME`）决定是否允许改变论文主线；**Working Role**（`WRITER`、`EDITOR`、`REVIEWER`、`CALIBRATOR`）决定当前执行写作、编辑、评审还是证据校准。普通写作不会擅自启动审稿或重构论文故事。

## 核心能力

| 场景 | 重点能力 |
|---|---|
| **Experiments / Results** | 直接呈现受控比较，区分固定条件下的观察、随机性稳健性和跨数据集泛化。 |
| **Method** | 解释技术设计、计算流程与机制，不因使用标准组件而反复自我辩解。 |
| **Theory** | 正面陈述已证明的结论，保留必要假设、量词和证明边界。 |
| **Introduction / Related Work** | 围绕核心 scientific story 组织贡献，判断真实创新而非关键词相似。 |
| **草稿 → 正文** | 从笔记、公式、outline 和实验结果构建有证据支持的最强论点。 |
| **局部编辑** | 只在授权范围内润色、澄清、强化、精简、扩写或重写选中的文本与 LaTeX。 |

所有场景都共享 Claim Construction、Claim Downgrade、Experimental Necessity、Disclaimer 和 Novelty 判断规则。另有可选的 [D1–D10 防御性写作分类](skills/academic-story-writing/references/defensiveness-taxonomy.md)，用于识别无效免责声明、无依据 hedging、自我贬低、假想审稿人防御、不必要的实验要求、重复性防御，以及相关工作、Method、Theory 和整体 story 中的特定偏差；**它不会机械删除必要的科学限定**。**论文重点强调的优势必须服务于 central thesis。**

## 示例

- [Experiments：从受控消融到 Results 正文](examples/experimental-writing.md)
- [Method：标准 backbone 与新 formulation](examples/method-writing.md)
- [Theory：以已证明的定理结论为中心](examples/theory-writing.md)
- [局部编辑：只优化一个 LaTeX 段落](examples/local-editing.md)
- [D1–D10 防御性表达检查示例](examples/defensiveness-audit.md)

所有示例均为虚构教学材料。Skill 不能代替对数学证明、引用和统计分析的独立核查。如果某个 claim 的证据确实不足，应保留仍然成立的最强表述，并具体指出缺失的依据。

## 参与贡献

欢迎通过 [CONTRIBUTING.md](CONTRIBUTING.md) 提交建议和问题案例。最有帮助的反馈包括：原任务、支持材料、模型产生的不理想文本，以及科学上更准确的改写。提交时请避免公开未获授权的论文草稿和审稿材料。

## 开源许可证

本项目采用 [MIT License](LICENSE)。
