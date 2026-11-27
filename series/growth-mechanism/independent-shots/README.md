# 增长机制｜独立动画镜头资源库

本目录保存《人生机制与增长机制》视频的镜头级独立动画、可编辑源文件、实际使用的 PNG 素材及脚本核对资料。

制作规范：[人生系列动画制作技术规范](../../../production-methodology/ANIMATION-TECHNICAL-STANDARD.md)。

## 镜头清单

| 镜头 | 版本 | 状态 | 独立预览 | 可编辑源文件 | 素材 |
|---|---:|---|---|---|---|
| 反馈与修正 | V4 | 已确认 | [预览 HTML](feedback-correction/feedback-correction-v4-standalone.html) | [可编辑 HTML](feedback-correction/feedback-correction-v4-editable.html) | [PNG 素材](feedback-correction/assets/) |
| 维护、更新与淘汰 | V6 | 已确认并嵌入总片 | [V6 预览](maintenance-update-retirement/maintenance-update-retirement-v6-standalone.html) | [V6 可编辑 HTML](maintenance-update-retirement/maintenance-update-retirement-v6-editable.html) | [V6 嵌入版](maintenance-update-retirement/maintenance-update-retirement-v6-embedded.html)；[V5 PNG 素材](maintenance-update-retirement/assets/) |
| 增长的流入与流出 | V3 | 已确认并嵌入总片 | [V3 预览](inflow-outflow/flow-inflow-outflow-v3-standalone.html) | [V3 可编辑 HTML](inflow-outflow/flow-inflow-outflow-v3-editable.html) | [V3 嵌入版](inflow-outflow/flow-inflow-outflow-v3-embedded.html)；[PNG 素材](inflow-outflow/assets/) |
| 增长动态不是过程节点 | V3 | 已确认并嵌入总片 | [V3 预览](growth-dynamics/growth-dynamics-v3-standalone.html) | [V3 可编辑 HTML](growth-dynamics/growth-dynamics-v3-editable.html) | [V3 嵌入版](growth-dynamics/growth-dynamics-v3-embedded.html)；[PNG 素材](growth-dynamics/assets/) |
| 边际收益递减与瓶颈 | V5 | 主体已验收；三个收束标签上移 30px，待复核 | [V5 预览](marginal-returns-bottleneck/marginal-returns-v5-standalone.html) | [V5 可编辑 HTML](marginal-returns-bottleneck/marginal-returns-v5-editable.html) | [瓶颈连续动画 V3](marginal-returns-bottleneck/bottleneck-scene-v3-embedded.html)；[V4 历史版](marginal-returns-bottleneck/marginal-returns-v4-standalone.html) |

## 归档内容

- 每个已确认镜头均保存单文件独立预览 HTML。
- 已将四个插画镜头实际引用的 PNG 从单文件 HTML 中提取，按原素材名称存入各自的 `assets/` 目录。
- 同时保存可编辑 HTML：图片引用改为相对路径 `assets/...`，便于单独替换素材和调整布局。
- 每个镜头有 README、素材清单或原始脚本对应文档。
- 边际收益 V3 是纯 SVG/CSS/JavaScript 镜头；其中“瓶颈”部分仍需按新的视觉原则返工。

## 制作原则

1. 保留总片原始台词、字幕与脚本边界，不因动画制作改写讲解内容。
2. 独立镜头先完成、预览和验收；用户确认后再嵌入总片。
3. 总片正式音频时间轴驱动字幕与动画；独立预览控件只用于单镜头验收。
4. 镜头资源按版本归档；未确认镜头明确标记为 WIP。
5. 图片素材、可编辑源文件和单文件预览分开保存，避免只留下不可拆解的成品。

## 原始总片与脚本

- [总讲解 HTML](../lecture-unified.html)
- [视听同步脚本标注副本](../lecture-unified-annotated.md)
- [镜头制作标注副本](../人生机制与增长机制-视听同步脚本-制作标注副本.md)（如该文件尚未进入仓库，后续补入）
