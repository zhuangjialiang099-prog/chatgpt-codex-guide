# ChatGPT Images 2.6（GPT-Image-2.6）：GIF、表情包与 Flare／Sunburst 指南

> 本文依据 GPT-DUO 已发布页面整理，资料核对日：2026-11-06。原文：[ChatGPT Images 2.6 是什么？GIF 动图与 Flare／Sunburst 对比](https://www.gpt-duo.com/blog/chatgpt-images-2-6-guide)。本文由 GPT-DUO（AI DUO）维护；维护者经营 AI 订阅相关服务，相关链接可能包含商业信息。本仓库为独立中文资料，不是 OpenAI 官方文档。

## 先看结论

OpenAI 在 2026-11-04 发布 ChatGPT Images 2.6。ChatGPT 和 Codex 的各订阅档位可使用 Images 能力；开发者 API 提供 gpt-image-2.6-flare 与 gpt-image-2.6-sunburst。官方介绍了 GIF 动图生成、参考图复用和编辑能力。“一键生成表情包”是中文用户对 GIF 反应图玩法的描述，不是官方功能名称；GIF 也在逐步推送中，具体入口以账号页面为准。

## Images 2.6 与 GPT-Image-2.6

ChatGPT Images 2.6 是产品层称呼。开发者 API 中的两个模型 ID 是：

- gpt-image-2.6-flare：偏向快速迭代；官方称低质量档最快可在约 6 秒生成。
- gpt-image-2.6-sunburst：偏向更高细节与多轮编辑时的一致性。

社区常把它们统称为 GPT-Image-2.6。两者标准 API 单价相同，实际账单取决于输入、输出图像 token 与重试次数；不能把 API 单价直接换算成固定的单张费用。

## GIF 与表情包制作

官方举例包括循环 GIF、社交反应图和 meme。提示词最好写清主体、动作顺序、镜头与背景是否固定、循环起止状态，以及是否需要文字。示例：

~~~text
做一个无缝循环 GIF：圆眼睛猫咪盯着镜头，先眨眼，再慢慢抬起一边眉毛，最后回到起始姿势。纯色薄荷绿背景，镜头和背景固定，表情夸张，适合做社交反应贴纸。不要文字、水印或边框。
~~~

生成后可打开 GIF 调整播放速度，也可继续用自然语言修改。官方帮助文档说明，不能编辑用户上传的现成动画 GIF；可以继续编辑 ChatGPT 自己生成的 GIF。GIF 创建功能正逐步推送，未看到入口不代表账号或订阅异常。

## ChatGPT 中的基本步骤

1. 在 ChatGPT 网页、iOS、Android 或 Codex 中打开 Images 能力。
2. 描述主体与动作，并明确要求循环 GIF；需要参考角色时，先保存参考图再按产品内说明调用。
3. 检查循环是否自然、文字和主体是否稳定，再调整速度或继续编辑。

静态图片与 GIF 的每日精确次数没有统一公开数字，应以本人账号内提示为准。Images 的可用范围与 Work／Codex 的额度规则是不同问题。

## API 价格

OpenAI 定价页列出的 Images 2.6 Standard API 单价按每百万 token 计；Flare 与 Sunburst 相同：

| 类型 | 单价（美元／百万 token） |
| --- | ---: |
| 文本输入 | $5 |
| 文本缓存输入 | $1.25 |
| 图像输入 | $8 |
| 图像缓存输入 | $2 |
| 图像输出 | $30 |

这不是每张图片的固定价格。单次成本受图像尺寸、质量、输入内容和重试影响；实际调用前应查看实时定价页。

## 官方来源

- [OpenAI：Introducing Images 2.6](https://openai.com/index/introducing-images-2-6/)
- [Images in ChatGPT 帮助文档](https://help.openai.com/en/articles/11084440-images-in-chatgpt)
- [OpenAI API 定价](https://developers.openai.com/api/docs/pricing)
- [API Changelog](https://developers.openai.com/api/docs/changelog)
- [Image generation 指南](https://developers.openai.com/api/docs/guides/image-generation)
- [GPT-Image-2.6 Flare 模型说明](https://developers.openai.com/api/docs/models/gpt-image-2.6-flare)
- [GPT-Image-2.6 Sunburst 模型说明](https://developers.openai.com/api/docs/models/gpt-image-2.6-sunburst)

> 功能范围、开放进度与价格可能变化。请以官方当前说明和本人账号显示为准。GPT-DUO 的会员办理条件及人民币价格以对应商品页和结算页为准：[ChatGPT Plus／Pro 选择指南](https://www.gpt-duo.com/blog/chatgpt-plus-vs-pro-how-to-choose)。
