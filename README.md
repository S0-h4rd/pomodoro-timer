# 番茄钟 · 喫茶

一个采用日式喫茶店（Kissaten）美学风格的番茄钟计时器。

![风格预览](pomodoro-palette.svg)

## 在线体验

直接在浏览器中打开 `pomodoro.html` 即可使用，无需构建步骤。

## 设计理念

摒弃了常见的紫色渐变与玻璃拟态等"AI 通用审美"，转而从日本传统喫茶店中汲取灵感：

- **暖纸色背景** — 模拟和纸与木桌的温润质感
- **衬线体排版** — Noto Serif SC 传递沉稳与专注
- **手绘感圆角** — 不规则的 `border-radius` 打破数字世界的冰冷
- **柔和多层阴影** — 元素如纸张般轻轻浮起
- **细微噪点纹理** — 背景增添手作温度

## 功能特性

| 模式 | 时长 | 用途 |
|:---|:---|:---|
| 专注 | 25 分钟 | 深度工作时段 |
| 短休息 | 5 分钟 | 番茄之间的间隙 |
| 长休息 | 15 分钟 | 每 4 个番茄后的长休 |

- **自动切换**：专注结束后自动进入休息，每 4 个番茄后进入长休息
- **本地持久化**：今日完成数与专注分钟数保存在 `localStorage`，跨刷新不丢失
- **每日重置**：自动检测新的一天，重置当日统计
- **桌面通知**：计时结束时推送浏览器通知
- **键盘快捷键**：空格键快速开始/暂停
- **完成庆祝**：计时结束时触发弹性缩放动画

## 配色方案

```
番茄红  #C94A4A  — 专注时段
薄荷绿  #5A9E7A  — 短休息
静谧蓝  #5A8EAE  — 长休息
暖纸色  #F7F3EE  — 主背景
墨黑    #2C2420  — 主文字
木色    #8B7355  — 点缀与分隔
```

## 技术栈

- 纯 HTML / CSS / JavaScript，零依赖
- CSS 自定义属性（变量）管理主题色
- `conic-gradient` 实现进度圆环
- CSS 动画与 `cubic-bezier` 缓动曲线
- `localStorage` 持久化统计
- `Notification API` 桌面推送

## 文件结构

```
.
├── pomodoro.html      # 主应用（单文件）
├── pomodoro-palette.svg   # 配色方案参考图
├── index.html         # SPC 监控大屏（独立页面）
├── dashboard.js       # SPC 数据可视化
├── styles.css         # SPC 样式
└── README.md          # 本文件
```

## 本地运行

```bash
# 克隆仓库
git clone https://github.com/S0-h4rd/pomodoro-timer.git
cd pomodoro-timer

# 直接用浏览器打开
open pomodoro.html        # macOS
start pomodoro.html       # Windows
xdg-open pomodoro.html    # Linux

# 或启动本地服务器
python -m http.server 8080
# 然后访问 http://localhost:8080/pomodoro.html
```

## 浏览器支持

- Chrome / Edge / Firefox / Safari 最新版
- 支持 PWA 安装（添加到主屏幕）
- 响应式布局，适配手机与桌面

## 开源协议

MIT License
