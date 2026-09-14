# paper-master

面向计算神经科学、脑建模与复杂系统研究读者的中文论文阅读 Skill。可以按需组合总结、科学论证评议、相关文献检索和主题综述，并明确公式、参数、来源及阅读边界。

**已公开发布：** [Spark1027/paper-master-skill](https://github.com/Spark1027/paper-master-skill)。本项目由 Spark1027 在 AI Harness 学习与真实论文阅读实践中整理，并借助 AI 辅助编写；方法借鉴及许可见 [第三方说明](THIRD_PARTY_NOTICES.md)。

它是一套由兼容的 AI 助手读取并执行的指令，不是独立运行的论文软件。效果依赖模型、输入材料和可用工具；结构检查或单次示例不能保证科学判断正确。

## 四个模块

| 模块 | 适用任务 | 交付 |
| --- | --- | --- |
| 1：summary | 阅读与总结、模型解析 | 七节通用总结，或六节技术／模型解析 |
| 2：critical-thinking | 主张、证据与科学论证评议 | 具体问题、影响及可执行的补证建议 |
| 3：research-lookup | 找相关论文、核实引文 | 有来源的文献记录、可比性与阅读优先级 |
| 4：literature-review | 按主题综合研究、检查初稿文献覆盖 | 一致证据、分歧、边界和研究缺口 |

四模块可以任意组合。只给论文要求阅读时默认模块 1；只要求 2+4 时不会附加完整总结或独立检索模块。需要核实来源时是否联网，仍按用户约束和当前工具能力处理。入口只路由到本次需要的说明。

## 安装

适用于能够识别 `SKILL.md` 及相对引用文件的 Codex 环境。先从 [GitHub 仓库](https://github.com/Spark1027/paper-master-skill) 下载 ZIP，或运行 `git clone https://github.com/Spark1027/paper-master-skill.git`，再进入 `paper-master-skill` 仓库根目录。以下命令仅复制 Skill 八个文件，不复制案例和文档，也不会覆盖已有安装：

```sh
(
  set -eu
  skill_root="${CODEX_HOME:-$HOME/.codex}/skills"
  skill_target="$skill_root/paper-master"
  if [ ! -f paper-master/SKILL.md ]; then
    echo '请先进入 paper-master-skill 仓库根目录。' >&2
    exit 1
  fi
  if [ -e "$skill_target" ] || [ -L "$skill_target" ]; then
    echo '已存在 paper-master；请先比较并备份现有版本，本命令不会覆盖。' >&2
    exit 1
  fi
  mkdir -p "$skill_root"
  cp -R paper-master "$skill_target"
  echo "已安装到 $skill_target"
)
```

在新任务中确认能选择 `paper-master` 后再使用；当前会话是否即时刷新由运行环境决定。本地安装不需要额外 API key。其他兼容客户端请按其 Skill 安装目录放置整个 `paper-master/`，本项目未逐一验证这些客户端。

## 调用示例

```text
使用 $paper-master，只做总结。只阅读下面粘贴的摘要，不联网、不写文件。
```

```text
使用 $paper-master，模块 1+2。模块 1 按技术／模型模式，重点解释核心方程、参数和证据边界：论文 DOI 或附件。
```

```text
使用 $paper-master，只做 critical-thinking 和 literature-review，审阅我的 Markdown 初稿。
不要修改原稿；外部查证只使用通用方法术语与已有公开引文。
```

```text
使用 $paper-master，四个模块全用。目标论文：10.1073/pnas.2318641121。
做有限的相关文献检索，标明实际读到的版本与范围；为 GitHub 输出 Markdown 数学格式。
```

默认提供中文分析及同内容 Markdown 文件；用户禁止写文件或只要一种形式时按用户要求。输出公式的默认定界符适合通用 Markdown 编辑流程，目标为 GitHub 时可明确要求 `$...$` / `$$...$$`；本仓库示例已使用 GitHub 格式。

## 运行环境与边界

- 文本／Markdown 输入可以只依赖当前助手的文件读取能力；粘贴内容不需要网络。
- 网页论文、文献检索与引文核实需要实际可用的联网工具。没有工具、页面受限或只读了摘要时，应交付受限结论，不补造全文细节。
- Word／PDF 支持表示指导助手调用现有文档工具读取；本仓库不附解析器。复杂公式、扫描页、修订和图像依赖环境的解析或渲染能力。
- 不自动安装依赖、不运行论文仿真、不启动付费服务或多 Agent。用户输入原稿保持不变，未公开稿件不会因普通阅读自动上传到转换网站或作为完整搜索词发送。
- 模型状态不是直接生理测量；相关关系不是因果；拟合良好不是机制证明。报告必须区分作者假设、报告结果、作者解释和分析者建议。
- 普通检索或主题综合不等于系统综述；真正的系统综述需要另定范围及筛选记录。

## 看两个例子

- [真实 E/I 论文：四模块组合](examples/ei-youth/README.md)：2026-09-13 真实阅读输出的公开整理版，含来源与覆盖限制；本次没有重跑论文分析。
- [离线合成材料：通用总结](examples/offline-synthetic/prompt.md)：自带教学输入和示范输出，可在无网络时试用；输入不是实际论文或实验。

这些案例帮助理解预期行为，不是综合质量基准。没有承诺任何固定模型、固定措辞或 token 改善幅度。

## 许可

- `paper-master/` 全部 Skill 指令和配置，以及 README 中的安装代码片段：**MIT**。
- README、案例输入与报告等独立原创文档：**CC BY 4.0**，署名 Spark1027。
- 第三方许可文本、引用论文及其链接内容保留各自权利；这里的许可不重新授权外部论文。

详见 [LICENSE.md](LICENSE.md) 和 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
