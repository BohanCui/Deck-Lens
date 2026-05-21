# Deck Lens

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

> 📖 For English, see [README.md](./README.md)

**做 PPT 之前，先想清楚这件事该怎么讲。**

同一个项目，面对不同的人，讲法完全不一样。给评委路演的逻辑，拿去跟领导汇报会显得像在表演；政府汇报的写法，放进比赛 deck 里会死气沉沉。

Deck Lens 做的事就是：**先帮你判断用哪套逻辑讲，再生成对应的 PPT 结构、演讲稿或完整幻灯片文件。**

Deck Lens 是一个 [Claude Skill](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)。

---

## 四种汇报方式

|模式|适合什么场合|核心思路|
|---|---|---|
|**Pitch**|比赛、融资、客户演示、产品发布|吸引注意 → 感受痛点 → 亮出方案 → 报价 → 推动行动|
|**内部汇报**|向领导、管理层或跨部门汇报|结论先行，再给依据（金字塔原则）|
|**体制内**|政府机关、事业单位、监管部门|有据可查 → 客观分析 → 方案可靠 → 成效可验证 → 风险可控|
|**技术交接**|开发人员、架构师、数据科学家、研究人员——各类领域专家|核心原则 + 领域分流（软件 / 数据 / 硬件 / 研究，或通用结构）|

每种模式都有独立文件，包含完整的段落结构、幻灯片数量参考和表达要点。

---

## 怎么用

触发后，Deck Lens 按以下流程走：

1. **读懂场景** — 搞清楚这个汇报给谁看、目的是什么
2. **推荐模式** — 自动判断最合适的选项，**确认后**再继续
3. **确认输出** — PPTX 文件、演讲稿，或者两者都要
4. **收集内容** — 主题、痛点、方案、亮点、延伸价值
5. **生成** — 按确认的模式逐段完成，需要 PPTX 时套用设计模板

逻辑和结构先走，视觉设计是最后一层。

---

## 目录结构

```
Deck-Lens/
├── SKILL.md              # 主文件（安装用；英文正文，中英双语触发词）
├── SKILL-en.md           # 纯英文版
├── SKILL-zh.md           # 纯中文版
├── modes/                # 四种模式的完整结构文件（中英文各一份）
│   ├── pitch.md          / pitch-zh.md
│   ├── internal.md       / internal-zh.md
│   ├── government.md     / government-zh.md
│   └── technical.md      / technical-zh.md
├── templates/            # 设计模板（可替换）
│   └── design-default.md / design-default-zh.md

```

> **说明：** 安装后系统只读取 `SKILL.md`。`SKILL-en.md` 和 `SKILL-zh.md` 是给人看的语言版本，想用哪个就把内容覆盖进 `SKILL.md` 即可。

---

## 设计风格

汇报的视觉设计和叙事结构是分开的，可以独立替换。

默认模板（`templates/design-default-zh.md`）采用宝蓝配色，**浅色背景**——深蓝只用于标题栏、强调色块和章节分隔，不会整页深色铺底。

换风格的方法：

1. 复制 `templates/design-default-zh.md`，改名为 `templates/design-<你的名字>.md`
2. 修改配色、字体和布局规则
3. 告诉 Deck Lens 使用你的模板文件

模板和模式可以任意组合，互不影响。

---

## 安装

Deck Lens 是一个 Claude Skill，安装步骤：

1. 下载或克隆本仓库
2. 按照 [Claude Skills 文档](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) 将其添加到你的 Claude 环境
3. 让 Claude 帮你做 PPT、写汇报或准备演讲稿，Deck Lens 会自动触发

---

## 后续计划

### 近期可优化

- **示例** — 目前计划添加四种模式的完整示例，正在写中。

### 未来可添加

- **新增模式** — 仅在确实有需求时考虑，比如教学/培训模式、或者大mode的sub-modes
- **模式选择流程图** — 在文档里加一张可视化决策图，方便不想跑 skill 也能自己选模式的人
- **更多设计模板** — 目前只有一套宝蓝色浅色主题，可以再加深色主题、极简学术风等预设
- **混合模式示例** — 比如一个技术型路演，用实例演示"从另一种模式借一个环节"具体怎么操作


## 随时欢迎提建议或贡献！
请提交 issue 或 pull request。

---

## 许可证

本项目采用 [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) 许可证 — 可自由分享和改编，但须署名，且不可用于商业目的。
