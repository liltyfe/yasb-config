# YASB 2.0.5 动态强调色桌面状态栏配置

一套面向 Windows 11 的 [YASB Reborn](https://yasb.dev/) 配置，适配 **YASB 2.0.5**。整体采用半透明圆角和磨砂玻璃风格，并通过 YASB 的系统颜色服务读取 Windows 强调色、前景色和背景色，因此不需要手动切换深浅主题。

配置包含媒体控制、Quick Launch、应用启动器、窗口切换器、任务栏、壁纸选择与过渡、实时网速、Wi-Fi、CPU、内存、蓝牙、勿扰模式、GitHub 通知、音量和电源菜单。

## 功能亮点

- **Windows 动态配色**：启用 `system_colors: true`，自动生成并加载 `yasb_colors.css`，强调色及文字颜色跟随 Windows。
- **磨砂玻璃界面**：状态栏、Quick Launch、窗口切换器和多个弹出菜单使用透明背景、模糊、圆角及系统色边框。
- **Quick Launch**：搜索并启动应用、文件和系统设置，支持全局快捷键 `Alt + Space`。
- **窗口视图切换**：以图标视图浏览当前窗口，可作为轻量的 Alt-Tab 替代方案，支持 `Alt + W` 呼出。
- **壁纸选择器**：支持 `Alt + P` 呼出居中预览、键盘或滚轮翻页，以及圆形扩散壁纸过渡。
- **Windows 勿扰模式**：直接在状态栏切换关闭、仅优先通知和仅闹钟三种状态。
- **紧凑网速显示**：实时显示上传和下载速度，左键可打开详细网络信息。
- **多显示器支持**：默认通过 `screens: ["*"]` 在所有显示器创建状态栏，可按需改为仅主屏。

## 效果预览

### 深色桌面

![深色模式状态栏](img/效果图-深色模式.png)

![深色模式桌面效果](img/效果图-深色-整体桌面.png)

### 浅色桌面

文字颜色、强调色和容器颜色由 Windows 系统颜色提供，因此同一份配置也能搭配浅色壁纸使用。

![浅色壁纸下的状态栏](img/效果图-浅色模式.png)

![浅色桌面整体效果](img/效果图-浅色-整个桌面.png)

### 磨砂玻璃 Quick Launch

按 `Alt + Space` 打开 Quick Launch。

![Quick Launch 搜索效果](img/效果图-搜索功能.png)

### 窗口视图切换

按 `Alt + W` 打开窗口切换器。

![窗口视图切换效果](img/app视图切换效果.png)

### 电源菜单与任务栏菜单

![电源菜单](img/power-menu.png)

![任务栏应用右键菜单](img/taskbar-context-menu.png)

## 状态栏布局

- **左侧**：媒体信息与控制、活动窗口标题
- **中间**：日期时间、Quick Launch、常用应用启动器
- **右侧**：壁纸、GitHub 通知、窗口切换器、任务栏、实时网速、Wi-Fi、CPU、内存、蓝牙、勿扰模式、WHKD、音量和电源菜单

## 快捷键

| 快捷键 | 功能 | 弹窗内操作 |
| --- | --- | --- |
| `Alt + Space` | 打开或关闭 Quick Launch | `↑` / `↓` 选择，`Enter` 打开，`Esc` 关闭 |
| `Alt + W` | 打开或关闭窗口切换器 | `←` / `→` 选择，`Enter` / `Space` 切换，`Delete` 关闭窗口，`Esc` 退出 |
| `Alt + P` | 打开或关闭壁纸选择器 | `←` / `→` 或滚轮翻页，`Enter` 应用，`Esc` 退出 |

YASB 使用 Windows 全局热键机制。若快捷键无效，请检查是否已被 PowerToys、输入法、窗口管理器或其他程序占用。

## 组件操作

### 媒体控制

- 左键点击媒体信息：播放或暂停。
- 中键点击媒体信息：切换标题和艺术家的显示顺序。
- 右键点击媒体信息：打开详细媒体菜单。
- 媒体菜单支持封面、来源、播放控制和音量滑块。

### Quick Launch

点击状态栏中间的搜索图标，或按 `Alt + Space` 打开。当前界面使用独立的圆角搜索栏和结果面板，并通过 Windows 模糊效果透出壁纸颜色。

### 窗口切换器

点击窗口视图图标，或按 `Alt + W` 打开。选中窗口标题会显示在图标下方；键盘焦点和鼠标悬停使用 Windows 强调色高亮。

### 壁纸选择器

- 点击壁纸图标或按 `Alt + P` 打开壁纸库。
- 当前配置每页显示一张 `640 × 360` 横向预览，使焦点保持在中央。
- 使用方向键或滚轮切换，按 `Enter` 应用。
- 双击图片也可以应用壁纸；右键图片可选择显示器。
- 壁纸应用时使用 YASB 2.0.5 的 `circle` 圆形扩散过渡。

> YASB 原生画廊以填充方式绘制缩略图。16:9 壁纸基本能够完整显示，其他比例仍可能被居中裁切；原生组件不支持带左右预览的平滑居中轮播。

### 任务栏

- 点击后台或已最小化的应用图标：切换到对应窗口。
- 点击当前前台窗口的图标：最小化窗口。
- 右键点击图标：根据窗口状态显示固定、结束任务或关闭等操作。

### 实时网速

- 默认以字节单位显示当前下载和上传速度，并隐藏小数，减少状态栏占用宽度。
- 左键点击：打开网络接口和连接状态菜单。
- 右键点击：切换简洁标签和中文详细标签。

### 勿扰模式

- 左键点击：在关闭和最近使用的勿扰状态之间切换。
- 中键点击：显示或隐藏当前状态文字。
- 右键点击：依次循环 `disabled`、`priority` 和 `alarms`。

### 电源菜单

点击最右侧的电源图标，可选择关机、重启、退出登录、休眠或睡眠。执行电源操作前请保存正在进行的工作。

## 使用前准备

1. 安装 [YASB Reborn](https://docs.yasb.dev/latest/installation.html)。建议使用 2.0.5 或更高的兼容版本：

   ```powershell
   winget install --id AmN.yasb
   ```

2. 安装图标和中文回退字体。建议至少安装一款 Nerd Font：

   - ComicShannsMono Nerd Font
   - JetBrainsMono Nerd Font / JetBrainsMono NFP
   - Symbols Nerd Font Mono
   - LXGW WenKai Mono

3. 如果需要对应组件，请另外安装 Komorebi、WHKD，以及应用启动器中配置的软件。

4. 在 Windows 的“设置 → 个性化 → 颜色”中开启“透明效果”。省电模式或系统关闭透明效果时，磨砂玻璃可能退化为普通半透明背景。

## 安装配置

YASB 默认从 `%USERPROFILE%\.config\yasb\` 读取配置。将仓库中的配置和样式文件复制到该目录：

```powershell
$yasbConfigDir = Join-Path $env:USERPROFILE ".config\yasb"
New-Item -ItemType Directory -Force -Path $yasbConfigDir
Copy-Item .\config.yaml, .\styles.css -Destination $yasbConfigDir -Force
```

`config.yaml` 已启用 `system_colors: true`。YASB 启动后会自动生成 `yasb_colors.css`，`styles.css` 会通过 `@import "yasb_colors.css"` 使用其中的动态颜色。仓库中的 `yasb_colors.css` 只是一个初始快照，之后可能被 YASB 自动覆盖，不建议手动修改。

如需使用天气或 GitHub 通知，再复制环境变量模板：

```powershell
Copy-Item .\.env.example (Join-Path $yasbConfigDir ".env")
```

编辑生成的 `.env`：

```dotenv
YASB_WEATHER_API_KEY=YOUR_WEATHER_API_KEY
YASB_WEATHER_LOCATION=YOUR_CITY_OR_POSTAL_CODE
YASB_GITHUB_TOKEN=YOUR_GITHUB_TOKEN
```

`.env` 已被 `.gitignore` 排除。不要把真实 Token、API Key 或精确位置直接写入 `config.yaml`、README 或提交历史。

## 本地程序与壁纸路径

应用启动器当前使用以下程序名：

```text
wt
QQMusic.exe
Code.exe
firefox.exe
explorer
QQ.exe
Weixin.exe
CLASHN~1.EXE
```

只有已经加入 `PATH` 或能被 Windows 正确解析的程序名才能直接启动。如果程序无法打开，请在 `widgets.apps.options.app_list` 中替换为本机绝对路径；不使用的条目可以直接删除。

壁纸组件当前使用：

```yaml
image_path: "wallpapers"
```

请在 YASB 配置目录中准备 `wallpapers` 文件夹。如果相对路径在你的安装方式下无法识别，请将其替换为实际壁纸目录的绝对路径。

配置中还保留了一个未加载到状态栏的 AI 快捷入口，它默认调用 Firefox 打开 OpenAI Playground。不需要时可以删除 `widgets.ai`，需要使用时请修改其中的浏览器路径和网址。

## 多显示器

默认设置为：

```yaml
screens: ["*"]
```

这会在所有显示器上创建状态栏。只希望在主显示器显示时，改为：

```yaml
screens: ["primary"]
```

组件快捷键的 `screen` 可使用 `active`、`cursor` 或 `primary`，分别跟随活动窗口、鼠标或主显示器。多屏用户可根据使用习惯调整 Quick Launch、窗口切换器和壁纸选择器的弹出位置。

## 可选和未验证组件

配置中保留了天气、更新检查、Komorebi 工作区与布局，以及 AI 快捷入口的定义，但它们当前没有全部加载到状态栏，也没有在所有环境中完成验证。如需启用，请结合对应软件和 [YASB 2.0.5 官方文档](https://docs.yasb.dev/latest/)检查配置。

## 自定义

- 修改组件位置：编辑 `bars.primary-bar.widgets` 下的 `left`、`center` 和 `right`。
- 修改字体：编辑 `styles.css` 中的全局 `font-family`。
- 修改栏高和间距：调整 `bars.primary-bar.dimensions`、`padding` 及组件 CSS。
- 修改透明度：调整样式中的 `rgba(..., alpha)` 最后一个数值。
- 修改强调色：在 Windows“设置 → 个性化 → 颜色”中选择颜色，YASB 会更新 `yasb_colors.css`。
- 自动重载：`watch_config` 和 `watch_stylesheet` 已启用，保存文件后会自动应用。

## 安全提示

- `.gitignore` 只能阻止尚未提交的 `.env`；已经进入 Git 历史的密钥仍然可以被恢复。
- 如果曾经提交过真实密钥，应先在服务商后台撤销或轮换，再考虑使用 `git filter-repo` 清理历史。
- 上传截图前，请检查窗口标题、浏览器标签、账户头像、用户名、通知内容和桌面文件名。

## 参考与致谢

本主题的布局和视觉样式参考了 `amnweb/yasb-themes` 中由 [amnweb](https://github.com/amnweb) 发布的以下主题：

- [Acrylic](https://github.com/amnweb/yasb-themes/tree/main/themes/a93f1976-0c89-4593-b333-eaa374164c73)
- [Yasb 004](https://github.com/amnweb/yasb-themes/tree/main/themes/0892faae-d929-4c65-8689-4ef1de32f73d)

更多组件选项与样式类请参考：

- [YASB 2.0.5 文档](https://docs.yasb.dev/latest/)
- [系统颜色与样式](https://docs.yasb.dev/latest/styling)
- [Quick Launch](https://docs.yasb.dev/latest/widgets/quick-launch)
- [窗口切换器](https://docs.yasb.dev/latest/widgets/window-switcher)
- [壁纸组件](https://docs.yasb.dev/latest/widgets/wallpapers)
- [勿扰模式](https://docs.yasb.dev/latest/widgets/dnd)

感谢原作者及 YASB 社区分享这些配置与设计思路。
