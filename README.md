# XCXParkourMaster 精选关卡集

这是一个为 [XCX Parkour Master](https://github.com/XCXParkourMaster/) 收集的官方精选关卡集。

## 如何使用

**方式 1 — 游戏内一键下载**

游戏主菜单 → `精选关卡` → `下载并安装`。

**方式 2 — 手动下载**

点击右上角 `Code` → `Download ZIP`，解压后把里面的系列文件夹
（如 `classic/`、`hardcore/`）复制到游戏目录下的 `maps/` 中。

## 系列列表

<!-- | 文件夹 | 名称 | 关卡数 | 作者 | -->
<!-- |---|---|---|---| -->
<!-- | classic | 经典挑战 | 5 | 内置 | -->
<!-- | hardcore | 极限挑战 | 3 | 你的名字 | -->
*请在游戏内查看*

## 提交你的关卡

1. 在游戏里用 `editor.py` 编辑好关卡
2. 把整个 `maps/<你的系列>/` 文件夹打包成压缩包
3. 提交至xxx

> Tip: 不一定不会被选中

## 关卡格式

目录结构：

    maps/
      <系列ID>/
        info.toml        系列信息（可选，缺字段用文件夹名兜底）
        introd.txt       系列介绍（可选，也支持 introd.md / introd.html）
        L1.json          第一关
        L2.json          第二关
        ...

关卡 JSON 格式：
```JSON
{
  "name":    "关卡名（顶栏显示）",
  "hint":    "开局 2 秒飘字提示（可选）",
  "time":    20,                      // 限时秒数
  "on_start":"start.xcs",             // 加载时执行的脚本（可选）
  "platforms": [[x, y, w, h], ...],
  "items":     [["coin", x, y, w, h], ["clock", x, y, w, h]],
  "spikes":    [["spike", x, y, w, h, "up|down|left|right"]],
  "boosts":    [["boost", x, y, w, h, "up|down|left|right"]],
  "goal":      [x, y, w, h]
}
```
坐标原点在左下角，单位是像素。

玩家出生点 (0, 100)，建议把平台铺满屏幕底部。

提示：
  - 尖刺 dir 决定三角形朝向，up = 从地面往上刺
  - 推进器 dir 决定把玩家推向哪边（推进距离 = 5 个玩家身位 = 200px）
  - 在系列文件夹放 coin.svg / clock.svg 会自动替换金币/时钟贴图
