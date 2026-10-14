# RecentsNoClear

RecentsNoClear 是一个基于 **libxposed API 102** 的 ColorOS 桌面模块，用于移除最近任务列表底部的清除按钮
## 功能

| 功能                 | 处理方式                   |
|----------------------|----------------------------|
| 移除最近任务清除按钮 | 将按钮字段置为不可见 `GONE` |

按钮位于「全部清除」面板内。模块在面板 inflate 完成后与 `setAlpha` 之后各隐藏一次，避免按钮被重新显示。

## 兼容性与安装

| 项目        | 要求                                       |
|-------------|--------------------------------------------|
| Android     | Android 12 及以上（`minSdk 31`）           |
| Xposed 框架 | 支持 libxposed API 101 及以上的框架        |
| 目标应用    | ColorOS 桌面，包名 `com.android.launcher`、`com.oppo.launcher` |

安装步骤：

1. 安装 APK。
2. 在兼容的 Xposed 框架中启用模块，并将桌面（`com.android.launcher`、`com.oppo.launcher`）加入作用域。
3. 重启桌面。

模块没有独立设置界面，功能默认启用。模块声明了静态作用域，作用域已随模块写入，通常无需手动勾选。

## 已知限制

- 仅适用于 ColorOS 桌面，不适用于其他启动器。
- 依赖 ColorOS 私有类；桌面更新后，类名、方法签名或字段结构可能变化，需要重新适配。
- 不适用于仅支持 legacy API 82 的旧框架。

功能未生效时，请检查模块是否启用、桌面是否加入作用域、桌面是否已重启。

## 许可证与免责声明

本模块以 **GNU General Public License v3.0** 发布，许可证全文见 [LICENSE](LICENSE)。
部分实现思路参考了同样采用 GPL-3.0 的 [LuckyTool](https://github.com/luckyzyx/LuckyTool)。

本模块仅供个人学习与自用。使用本模块产生的任何后果由使用者自行承担。
