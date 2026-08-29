# Publication-Centered Research Writing

一个面向 Codex 的科研写作 Skill，帮助研究者围绕**最强且可证实的学术贡献**组织论文，而不是把论文写成项目过程汇报或实验结果仓库。

它适用于论文起草、故事线重构、实验取舍、摘要与引言改写、弱结果处理，以及投稿前的主张—证据一致性检查。

## 核心思路

论文中的问题、方法、实验和结论应共同证明一个值得发表的核心价值。这个 Skill 会引导 Codex：

- 从现有材料中提取候选贡献并确定主线；
- 建立主张—证据矩阵，识别证据缺口和过度表述；
- 根据论证职责保留、删除、降级或补充实验；
- 在结果不占优时判断是否应重新定位、解释权衡、收缩主张或重构故事；
- 按“问题 → 缺口 → 解法 → 证据 → 意义”组织标题、摘要、引言和全文；
- 校准“证明”“导致”“显著”“普适”等高风险措辞；
- 在投稿前检查审稿风险和全文记忆点。

它不会虚构实验、指标、显著性、引用或机制解释，也不会建议隐藏足以改变论文结论的负面证据。

## 安装

### 使用 GitHub CLI

```bash
gh repo clone Matchayou/publication-centered-research-writing ~/.codex/skills/publication-centered-research-writing
```

该仓库目前为私有仓库，因此执行命令的 GitHub 账号需要拥有访问权限。

### 手动安装

下载或克隆本仓库后，将整个目录复制到：

```text
~/.codex/skills/publication-centered-research-writing/
```

安装后的关键文件应位于：

```text
~/.codex/skills/publication-centered-research-writing/SKILL.md
```

## 使用方式

在 Codex 中显式调用：

```text
使用 $publication-centered-research-writing 重构这篇论文的主张、证据链和叙事。
```

也可以针对具体任务调用：

```text
使用 $publication-centered-research-writing 检查这篇论文的核心主张是否被实验充分支持。
```

```text
使用 $publication-centered-research-writing 重写摘要和引言，让它们围绕最强贡献展开。
```

```text
使用 $publication-centered-research-writing 分析这些不占优的结果应该删除、解释、降级还是改变论文主线。
```

```text
使用 $publication-centered-research-writing 对全文进行投稿前审查，标出过度表述、证据缺口和无关实验。
```

为了得到可靠结果，建议同时提供论文正文、实验表格、比较基线、目标投稿方向，以及哪些结论已经被证据确认。

## 默认交付内容

未指定输出格式时，Skill 会优先给出：

1. 一句话中心主张；
2. 贡献排序及对应证据；
3. 实验的保留、删除、降级或补充建议；
4. 重构后的故事线或正文；
5. 尚存的证据缺口和安全措辞；
6. 投稿前风险检查。

短段落改写不会机械展开完整流程；全文重构和投稿前检查则会加载详细审查清单。

## 项目结构

```text
publication-centered-research-writing/
├── SKILL.md                       # Skill 入口、原则与执行流程
├── agents/
│   └── openai.yaml                # Codex 界面元数据与默认提示词
└── references/
    └── review-checklist.md         # 全文改稿与投稿前审查清单
```

## 设计边界

- 允许根据最强证据重新定义论文故事，但不允许选择性隐瞒关键结果。
- 鼓励缩小不受支持的主张，而不是用更强修辞掩盖证据不足。
- 实验数量不是目标；实验与主张的匹配度才是目标。
- 不把单项指标第一视为唯一贡献，合理的成本、效率、适用性和扩展性权衡同样可以构成价值。
- 仅在局限确实影响核心结论时进行具体、适度的说明，不主动扩大论文的攻击面。

## 文件说明

- [`SKILL.md`](SKILL.md)：Skill 的核心行为说明。
- [`references/review-checklist.md`](references/review-checklist.md)：用于全文改稿和投稿前审查的详细检查表。
- [`agents/openai.yaml`](agents/openai.yaml)：Codex 中显示名称、简介和默认调用提示。
