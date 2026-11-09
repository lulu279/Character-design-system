# 二创角色设计 · GPT 提示词工程

在 GPT 对话中使用的角色设定、单幅插画和风格迁移工作流。角色卡锁定身份与身体结构，风格卡描述线条、光色与材质，单图任务单指定本图的衣装、动作、镜头和场景。

## 开始使用

1. 打开 [GPT 工作流与提示词手册](workflow/gpt-workflow-v1.0.md)，复制第 0 节的主控提示词，并附上手册。
2. 选择角色卡与所需风格卡。已有参考图时，注明每张图负责身份、服装或画法。
3. 发送一条任务指令，例如 `/逐张生成 HK433；04；先给提示词`。手册 A5 提供固定段和 04 增量段，A6 提供 Mesmer 侧后视提示词，B 节提供风格拆解与迁移模板。

| 目录 | 内容 |
|---|---|
| `workflow/` | 主控提示词、建档、单图生成、局部返工、风格分析和会话交接 |
| `characters/` | HK433、Mesmer、DeepSeek 鲸鱼娘、GPT 龙娘、玛利亚和摇摇，共 6 张角色卡 |
| `styles/` | 7 张风格卡及草案，确认状态见各卡 |
| `prompts/` | 蓝紫海洋系中英提示词、双语模板、厨房暖逆光示例提示词 |
| `examples/` | 3 张单幅示例，见下表 |

## 示例

| 示例图 | 演示内容 | 提示词位置 |
|---|---|---|
| [HK433 · 格里芬副官](examples/01-hk433-adjutant.jpg) | 换装后保留银发、耳机和颈部设备 | [手册](workflow/gpt-workflow-v1.0.md) A5 固定段＋04 增量段 |
| [Mesmer · 侧后设定](examples/02-mesmer-rear-three-quarter.jpg) | 观察宽袖、内衬和裙片在侧后视角的层叠 | [手册](workflow/gpt-workflow-v1.0.md) A6 的 02 侧后视 |
| [DeepSeek 鲸鱼娘 · 厨房暖逆光](examples/03-deepseek-warm-window.jpg) | 迁移窗边光色、边缘和景深，保留虎鲸角色识别 | [厨房示例提示词](prompts/deepseek-warm-window.md) |

示例选自既有单幅生成稿，以 JPEG 提供。表中提示词用于复用设计方法，原始生成参数未随图记录。HK433 图为《少女前线》同人。Mesmer 为《暗黑地牢》MOD The Mesmer Class 的同人图，背部细节属于同人演绎。[The Mesmer Class 作者发布页](https://www.patreon.com/GhastRiv/posts/mesmer-class-68109346)

鲸鱼娘的社区形象参考见 [DeepSeek 鲸鱼娘二创资产库](https://github.com/TreapGoGo/deepseek-whale-girl)。
