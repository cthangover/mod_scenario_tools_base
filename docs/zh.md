# 剧本工具基础 —— 供编辑器使用的剧本文件

`scenario_tools_base` 是读取或写入剧本文件的编辑器共用的库。它不添加窗口，会随需要它的编辑器一起安装。

## 谁在用它

剧本编辑器、场景编辑器、交互编辑器和光照编辑器，以及 RPG 地图编辑器。

## 它提供什么

- **`ScenarioFileService`** —— 找到所有模组的 `.scenario` 文件（`ScanScenarioFiles`），读写它们（仅限文件夹模组），解析文件头（场景、优先级），提取引用（场景切换、本地化键、任务、背景），为场景新建剧本（`CreateForScene`），并构建场景图（`BuildSceneGraph`，剧本编辑器中场景图的数据）。
- **`ScenarioSyntaxService`** —— 编辑器文本框中剧本语言的高亮（RPG 地图编辑器用它显示事件脚本），以及命令行的分词；交互编辑器借此找出是哪个剧本添加了某个交互物，光照编辑器则通过文件服务读取并改写 `light_set` 行。

语言本身来自对话引擎（`dialog_base`）；中立的文件和场景服务留在 `tools_base`，因此不涉及剧本的工具不会把对话引擎带进来。

## 依赖

`tools_base`、`dialog_base`。
