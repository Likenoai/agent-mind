# 维护、更新与淘汰｜独立分区 V5

## 本轮目标
彻底解决更新、淘汰标签与上方设备/其他画面元素发生空间冲突的问题。

## 版式决策
采用“方案 A：三个独立的纵向处理区域”。

每个区域统一采用：
1. 顶部标签；
2. 固定间距；
3. 对应设备插画；
4. 与分流路径相接的设备输入锚点。

三个标签统一宽度 300×46，中心 x=1325。
三个设备素材统一为 360×170 透明画布，统一视觉中心、顶部留白和底部基线。

关键空间关系：
- 标签到所属设备可见顶部：约 15px
- 上一台设备可见底部到下一标签顶部：约 35px

因此标签明显更靠近它所属的设备，而不是上方设备。

## 动画修订
器件运动改为 JavaScript requestAnimationFrame 驱动：
- 通过 SVG path.getPointAtLength() 计算沿路径的位置；
- 每个器件有独立的行程时长、等待间隔和相位；
- 行程期间持续可见；
- 只有抵达终点后才进入间隔隐藏；
- 在 20.4 秒镜头播放期间持续重复。

播放、暂停、继续、重新播放与对齐辅助线均已测试。

## 文件
- `maintenance-update-retirement-aligned-v5.html`：可编辑版本，引用 assets 目录。
- `maintenance-update-retirement-aligned-v5-standalone.html`：所有 PNG 已内嵌，单文件预览。
- `layout-anchors-v5.json`：三组区域、图像锚点、素材归一化规范。
- `station-assets-v5-contact-sheet.png`：三台设备归一化素材总览。
- `preview-v5-opening.png` / `preview-v5-mid.png` / `preview-v5-end.png`：关键时刻预览。
- `preview-v5-grid.png`：对齐辅助线预览。

## 验收范围
- 1600×900 浏览器渲染；
- 无 JavaScript 页面异常；
- 标签、设备各自成组，避免标签贴近上方设备；
- 器件在完整路径行程中保持可见；
- 暂停时位置冻结，重新播放后时间轴重置；
- 对齐辅助线开关正常。

## 尚未执行
没有修改总片 `lecture-unified.html`，没有部署 GitHub Pages。
本版本仍是等待确认的独立镜头。