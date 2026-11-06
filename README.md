# Academic Style Intelligence

A **lightweight, Codex-native skill** for research-led academic figures and scholarly writing. It is **not** a collection of fixed diagrams: Codex reads the actual research and selects the expression that best serves the purpose. A reference image and target journal are independent **optional** inputs.

## Install

### Install through Codex (recommended)

In Codex, ask the built-in installer to install the skill from its exact directory:

```text
$skill-installer Install academic-style-intelligence from this GitHub repository's .agents/skills/academic-style-intelligence directory: <repository-url>
```

Replace `<repository-url>` with this repository's GitHub URL. You can copy it from your browser; do not use the placeholder literally. Alternatively, supply the full directory URL: `<repository-url>/tree/main/.agents/skills/academic-style-intelligence`.

Start a new turn after installation. If the skill does not appear, restart Codex and select it by typing `$academic-style-intelligence`.

### Manual installation

Copy the **whole** `.agents/skills/academic-style-intelligence/` folder, including `references/`, into your project's `.agents/skills/` or your personal `~/.agents/skills/` directory. The resulting path must end in `academic-style-intelligence/SKILL.md`. Opening this repository in Codex also makes its repository-scoped skill discoverable.

No Python packages, separate CLI, JSON configuration, or separate vision API are required by this instruction-only skill. The built-in installer may use its own existing runtime; figure generation, browsing, and file export depend on your Codex tools and permissions.

See the [official Codex skill documentation](https://developers.openai.com/codex/skills/).

## Use with natural language

Once installed, describe your task normally, for example: “Read my Methods section and design an editable figure appropriate to this study.” Codex can select this skill when the request matches its description. Include `$academic-style-intelligence` to invoke it explicitly. Provide the research content or data needed for the task; a reference image and target journal are optional.

## Example prompts

```text
Use $academic-style-intelligence. Read my Methods section and choose a figure that accurately communicates this study. Don't assume a predetermined variable diagram or pipeline. Make it editable if possible.
```

```text
Use $academic-style-intelligence. Reference the attached figure's visual organization, but reconstruct the diagram from my own research content rather than copying it.
```

```text
Use $academic-style-intelligence. I am targeting [journal]. Inspect accessible official instructions and methodologically similar published figures before selecting a visual style. Differentiate rules from observations.
```

```text
Use $academic-style-intelligence. Revise this paragraph for its academic discipline and target journal without altering source claims or inventing citations.
```

Read [Chinese README](README.zh-CN.md) and [more examples](.agents/skills/academic-style-intelligence/references/examples.md).

## Principles and boundaries

- No language-to-template rule (Chinese empirical ≠ necessarily IV → DV boxes).
- Research semantics matter more than aesthetic mimicry.
- Reference images and target journals are optional, separately or together.
- Journal mandates, inspected examples, and model suggestions are distinct.
- Do not fabricate references, methods, variables, paths or statistical results.
- No maintainer-funded API service exists; users are responsible for usage under their Codex environment.

## Repository structure

```text
.agents/skills/academic-style-intelligence/
  SKILL.md                 Skill metadata and instructions
  references/examples.md   Varied natural-language examples
README.md                  English installation and usage
README.zh-CN.md            Chinese installation and usage
LICENSE                    MIT license
tests/manual-evaluation.md
```

The manual evaluation scenarios document suggested behavioral checks; they are not an automated test suite or a claim that every scenario has been run. This edition contains instructions and reference material, with no mandatory renderer or package dependencies.

Licensed MIT — see [LICENSE](LICENSE).
