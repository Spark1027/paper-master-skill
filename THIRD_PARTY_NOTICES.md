# 来源、方法借鉴与第三方声明

## K-Dense Scientific Agent Skills

本项目参考了 [K-Dense-AI/scientific-agent-skills](https://github.com/K-Dense-AI/scientific-agent-skills) 的科学评议、来源核实和主题综述方法，结合中文论文阅读与证据边界需求重新组织指令。不能将这些方法思想全部归为本项目首创。

后续对照与四模块改造采用的固定版本为：

`c1ed16d97dd61ff50a3bd46dd353e4a55fd77f34`

| 上游文件 | 借鉴与本项目调整 |
| --- | --- |
| [scientific-critical-thinking / SKILL.md](https://github.com/K-Dense-AI/scientific-agent-skills/blob/c1ed16d97dd61ff50a3bd46dd353e4a55fd77f34/skills/scientific-critical-thinking/SKILL.md) | 证据与推断层级、替代解释；按具体研究问题评议，不把临床偏倚量表套用到所有脑模型论文 |
| [research-lookup / SKILL.md](https://github.com/K-Dense-AI/scientific-agent-skills/blob/c1ed16d97dd61ff50a3bd46dd353e4a55fd77f34/skills/research-lookup/SKILL.md) | 检索定位与实际读取分开、关键主张可追溯；使用当前可用工具，不复制专用 API 依赖或固定大篇数目标 |
| [literature-review / SKILL.md](https://github.com/K-Dense-AI/scientific-agent-skills/blob/c1ed16d97dd61ff50a3bd46dd353e4a55fd77f34/skills/literature-review/SKILL.md) | 先定范围、按主题综合证据；默认有限综合，不承诺系统综述、自动绘图或 PDF 制作 |

历史说明：早期构建曾读取上游 `main` 页面，不能把那次读取说成已核实同一固定快照；上述 commit 对应后续保存并校验过 Git blob 的比较材料。上游三个入口文件对应 blob SHA 分别为下列固定记录（不是本项目 Skill 的哈希）：

- scientific-critical-thinking：`e12cbea98525f5d728fa2ef74b72f9c09b9fef73`。
- research-lookup：`9011fd9ee078059a38dd19cc548fd2a100effd9b`。
- literature-review：`2f85676f1a06fd71d7f9c6ebfa6d2670c099a2e1`。

本发布包未包含上游完整 Skill 或脚本副本。为保留明确的来源与使用条件，附 [上游 MIT 原文](LICENSES/K-Dense-MIT.txt)：Copyright (c) 2025 K-Dense Inc.。其 [固定版本许可文件](https://github.com/K-Dense-AI/scientific-agent-skills/blob/c1ed16d97dd61ff50a3bd46dd353e4a55fd77f34/LICENSE.md) 保留全部声明。

## 论文案例

[E/I 案例](examples/ei-youth/README.md) 是对三篇原始研究的分析与比较，引用出处在各项主张附近。未收录论文全文、XML、原图、补充文件或数据集。论文题目、作者及研究发现仍归其原作者；本仓库报告的许可仅覆盖可由本项目授权的分析表达。

## 许可文本来源

- 本项目 MIT 文本采用标准 MIT 条款，版权署名为 Spark1027。
- [CC BY 4.0 标准全文](LICENSES/CC-BY-4.0.txt) 来源为 [Creative Commons 官方许可文本](https://creativecommons.org/licenses/by/4.0/legalcode.txt)。
