# 反馈与修正 V4｜时间轴对齐与嵌入验证

## 原始边界

- cue：20
- 全局时间：05:45.559–06:07.032
- cue 时长：21.472653s
- 原独立动画设计时长：22.000s
- 原口播、关键画面文字、cue 起止时间和字幕数据保持不变。

## 时间映射

采用全局线性时间映射，不逐项手工修改事件阈值：

`TIME_SCALE = 22000 / 21472.653 = 1.024559005354392`

动画内部时间：

`sourceSeconds = cueElapsedMs × TIME_SCALE / 1000`

结果：
- cue 起点 0ms 映射到设计时间 0ms。
- cue 终点 21472.653ms 映射到设计时间 22000ms。
- 所有原动画事件阈值同比例压缩，动作先后关系不变。
- 显示时钟仍显示 cue 时间，终点显示 00:21.5 / 00:21.5。

## 嵌入结构

- 嵌入文件：`feedback-correction-v4-embedded.html`
- 总片 iframe：`feedbackFrame`
- 总片视觉适配器：`feedbackv4`
- 同步接口：`window.__feedbackCorrectionV4.sync(ms)`
- 父页面将 cue 相对时间传入 iframe。
- 内嵌演示字幕、播放控件和辅助线隐藏；总片正式字幕不受影响。
- 嵌入模式不启动自己的 requestAnimationFrame。

## 自动化检查

| 检查项 | 结果 |
|---|---|
| 独立 HTML JavaScript 语法 | 通过 |
| 可编辑 HTML JavaScript 语法 | 通过 |
| 嵌入 HTML JavaScript 语法 | 通过 |
| 总片 JavaScript 语法 | 通过 |
| cue 20 时长 | 21.472653s，未修改 |
| cue 20 原口播与 keyline | 未修改 |
| cue 20 起止位置 | 未修改 |
| DATA 变化范围 | 仅 visual adapter：feedbacklab → feedbackv4 |
| 终点时间映射 | 21472.653ms → 22000ms |
| 终点显示 | 00:21.5 / 00:21.5 |
| 中段状态回放 | 10.736s cue 时间显示“反馈不等于修正” |
| 嵌入模式 requestAnimationFrame | 0 |
| 正式配音与字幕 | 未改写、未拉长 |

## 素材

嵌入版引用 `assets/` 下的 8 个唯一 PNG：生产系统、检测扫描器、警报灯、信号监测器、控制台、修正执行器、故障模块、修正模块。对应资产均在仓库目录中。

## 尚需实际浏览器验收

- 独立预览在 GitHub Pages 的画面加载与播放。
- 总片 cue 19→20→21 是否有黑帧、空档或重叠。
- 16:9 与 9:16 取景、画面裁切和字幕安全区。
- 总片暂停、继续、倍速、章节跳转与 seek。
- cue 20 末帧到 cue 21 首帧的视觉衔接。

静态代码检查和时间映射模拟不能替代实际浏览器视觉验收。
