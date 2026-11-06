# Academic Style Intelligence

一个**Codex 原生、轻量、无额外依赖**的学术绘图与写作 Skill。

核心不是提供固定图表模板，而是让 Codex **先理解具体论文，再决定怎样绘图或修改文字**。例如，同为中文实证研究，也可能需要理论框架、研究设计、SEM 路径、变量关系、识别策略、系数可视化或其他形式；不一概套用自变量—因变量图。

## 安装

### 通过 Codex 安装（推荐）

在 Codex 中直接输入，要求内置安装器安装仓库中的准确子目录：

```text
$skill-installer 请从 <repository-url> 仓库的 .agents/skills/academic-style-intelligence 目录安装 academic-style-intelligence。
```

将 `<repository-url>` 替换为本仓库的 GitHub 地址（可从浏览器复制），不要直接使用占位符。也可以提供完整的目录地址：`<repository-url>/tree/main/.agents/skills/academic-style-intelligence`。

安装后在下一轮对话中调用；若没有显示，重新启动 Codex，再输入 `$academic-style-intelligence` 选择 Skill。

### 手动安装

把 `.agents/skills/academic-style-intelligence/` **整个目录**（包括 `references/`）复制到你的项目 `.agents/skills/` 下，或个人目录 `~/.agents/skills/` 下。安装后的文件路径必须以 `academic-style-intelligence/SKILL.md` 结尾。直接在 Codex 中打开本仓库，也可以发现仓库内的 Skill。

Skill 本身无需 Python 包、独立 CLI、JSON 配置或额外视觉 API；内置安装器可能使用其已有运行环境。具体绘图、浏览期刊和文件导出能力取决于 Codex 当前可用的工具和权限。

参见 [Codex 官方 Skill 文档](https://developers.openai.com/codex/skills/)。

## 直接输入自然语言

安装后可以直接描述任务，例如“阅读我的研究方法，为这项研究设计可编辑图形”。Codex 可以根据描述自动选择此 Skill；若希望明确调用，在指令中加入 `$academic-style-intelligence`。请提供任务需要的论文内容或数据。

```text
使用 $academic-style-intelligence，阅读我的论文研究内容，自主判断最能表达研究逻辑的图形，生成可编辑的版本。不要预设某种模板。
```

```text
使用 $academic-style-intelligence，参考我上传的图片的布局与信息组织方式，为我的论文重新作图。研究事实和关系以我提供的内容为准。
```

```text
使用 $academic-style-intelligence，针对目标期刊和我的研究方法寻找适合的图表示例，并区分官方要求、论文范例与设计建议。
```

```text
使用 $academic-style-intelligence，改写我的论文研究背景，让学术表达适应具体学科及目标期刊，不改变事实和结论。
```

参考图和目标期刊均为可选；可以同时给，也可以都不给。系统不得编造期刊要求、引用、变量和假设。

## 项目结构

```text
.agents/skills/academic-style-intelligence/
  SKILL.md                 Skill 元数据和核心指令
  references/examples.md   不同研究场景的调用示例
README.md                  英文安装与使用说明
README.zh-CN.md            中文安装与使用说明
LICENSE                    MIT 许可证
tests/manual-evaluation.md 手动行为评估场景
```

本版本仅包含指令与参考资料，无强制渲染后端或包依赖。手动评估场景用于检查研究判断能力，不表示所有场景已经实际测试。用户自己的 Codex 账户/API 用量取决于其使用方式。

## License

MIT，见 [LICENSE](LICENSE)。
