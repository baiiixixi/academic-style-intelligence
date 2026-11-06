# Academic Style Intelligence

**一个面向中文学术用户的 Codex 原生 Skill，让学术绘图与写作更贴合研究内容、学科语境和真实期刊范例。**

> **先理解研究，再选择表达方式。** 不把中文论文默认画成自变量—因变量框图，也不把英文算法论文默认画成神经网络架构图。

[使用示例](.agents/skills/academic-style-intelligence/references/examples.md)

## 这个 Skill 能做什么？

- **学术图表设计**：阅读研究问题、理论框架、研究方法、数据或结果，判断是否适合使用研究框架图、变量关系图、研究设计图、统计结果图、算法示意图等形式。上述类型仅为示例，**不是固定模板**。
- **参考图适配（可选）**：分析你提供的参考图片，借鉴布局、层次和视觉表达方式，再用你自己的研究内容重新组织，不照搬原图的文字、数据或独特设计。
- **目标期刊适配（可选）**：在允许联网且能访问相关材料时，核查期刊的官方图表规范与同类研究中的实际范例，据此提出设计建议。
- **学术写作辅助**：结合学科、语言和投稿语境调整段落、图注及术语表达，保留原有事实、数据与引用含义。
- **可编辑文件输出**：根据任务和当前环境，尽量提供 SVG、draw.io 等可编辑格式；如果工具或权限不支持，会说明限制，不假装已生成。

**参考图和目标期刊都不是必填项**：可以只提供研究内容，也可以提供其中一个，或同时提供两个。

## 安装

你需要一个可以使用 Skill 的 **Codex 环境**。这是指令型 Skill，**安装本身不需要 Python、JSON 配置、单独购买视觉模型 API，也无需部署后端服务**。实际执行会使用你自己的 Codex 环境及其可用工具。

### 方法一：让 Codex 从 GitHub 安装（推荐）

在 Codex 中输入：

```text
$skill-installer 请从以下 GitHub 目录安装 academic-style-intelligence：
https://github.com/baiiixixi/academic-style-intelligence/tree/main/.agents/skills/academic-style-intelligence
```


安装后按 Codex 的提示重新打开会话或重启 Codex（如有必要），即可使用 `$academic-style-intelligence`。

### 方法二：手动复制 Skill

将仓库中的整个 `academic-style-intelligence` Skill 文件夹复制到以下任意位置：

```text
# 当前项目可用
你的项目/.agents/skills/academic-style-intelligence/

# 当前用户的多个项目可用
~/.agents/skills/academic-style-intelligence/
```

文件夹中至少要有 `SKILL.md`；本项目还包含 `references/examples.md`，建议一并保留。macOS Finder 中可使用 `Command + Shift + .` 显示隐藏的 `.agents` 文件夹。

## 直接使用：不需要填写配置表

### ① 根据论文内容决定绘制什么图

```text
使用 $academic-style-intelligence。阅读我提供的研究问题和研究方法，
判断哪种图最能准确表达研究逻辑，不要套用固定模板。
请先确认图中关系与论文一致，再生成适合论文使用的可编辑图。
```

### ② 参考上传的图片重新绘图

```text
使用 $academic-style-intelligence，参考我上传图片的布局、信息层次和视觉风格，
结合我的论文内容重新设计图表。不要复制原图内容，也不要新增我没有提出的变量和关系。
如当前环境支持，请提供 SVG 或 draw.io 文件。
```

### ③ 按目标期刊的实际范例适配

```text
使用 $academic-style-intelligence，我准备投稿《[目标期刊名称]》。
请先核实可访问的官方图表要求，并参考研究方法相近的已发表论文，
为我的研究设计合适的图表。请区分期刊硬性要求、论文中的常见做法和你的设计建议。
无法核实时请如实说明，不要编造期刊规范。
```

### ④ 修改学术文字或图注

```text
使用 $academic-style-intelligence，结合我的研究领域和目标读者，
修改这段论文文字及图注，使表达更符合学术写作习惯。
保持事实、数据、研究结论和已有参考文献不变，不要添加虚构引用。
```

## 核心原则

1. **内容优先**：图的类型、箭头、变量、模块及文字由实际研究决定，而非由中文/英文或学科标签机械决定。
2. **参考可选**：没有参考图或期刊时仍可工作；有参考材料时也只提取与任务有关的有效信息。
3. **证据可追溯**：将期刊正式要求、已查看论文的特征和一般设计建议分开描述；仅有论文标题或 DOI 不代表已经分析其图形。
4. **不编造研究内容**：不自行添加变量、假设、因果关系、实验结果、参考文献或期刊规定。
5. **可编辑优先**：尽可能交付可进一步修改的文件，并检查明显的文字遮挡、错误连线和排版问题。

## 使用前需要知道

- **是否需要 API Key？** 安装此 Skill 不需要提供项目开发者的 API Key，也不需要额外注册独立视觉 API。Codex 本身的使用可能受到你所在账户的额度或 API 计费方式影响。
- **能否保证生成 SVG / draw.io？** 不能无条件保证。Skill 提供工作方法，实际读取参考图、联网查期刊、生成和保存文件，取决于 Codex 当前拥有的工具及文件权限。


## 仓库结构

```text
academic-style-intelligence/
├── README.md                         # 中文主文档
├── README.en.md                      # 英文说明
├── LICENSE
├── tests/
│   └── manual-evaluation.md         # 人工评测场景（非自动化结果）
└── .agents/
    └── skills/
        └── academic-style-intelligence/
            ├── SKILL.md             # Codex Skill 核心说明
            └── references/
                └── examples.md      # 更多调用示例
```


## 反馈与贡献

欢迎通过 GitHub Issues 提交使用问题、学科场景或改进建议，也欢迎贡献经过核验的示例。请勿在 Issue 中公开未授权的论文全文、账号密钥或个人信息。

## 开源协议

本项目采用 [MIT License](LICENSE)。
