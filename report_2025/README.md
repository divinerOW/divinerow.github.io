# CNOWCS年度报告网页

这是一个交互式的年度报告网页，根据选手数据动态生成个性化的年度总结。

## 功能特性

- 📖 分页展示年度报告内容
- 🎯 根据选手ID动态替换数据
- 🖱️ 支持鼠标点击翻页（点击左侧上一页，点击右侧下一页）
- 📱 支持移动端上滑翻页
- ⌨️ 支持键盘方向键和空格键翻页
- 🎨 手写字体风格
- 🎵 背景音乐自动播放
- 🖼️ 统一背景图片

## 使用方法

1. **准备资源文件**（必需）：
   - `handwriting.ttf` - 手写字体文件
   - `bg.jpg` - 背景图片
   - `bgm.mp3` 或 `bgm.ogg` - 背景音乐文件
   - `text.txt` - 报告文本内容（已存在）
   - `player.csv` - 选手数据文件（已存在）

2. **运行网页**：
   - 使用本地服务器运行（推荐，避免CORS问题）：
     ```bash
     # 使用 Python 3
     python -m http.server 8000
     
     # 使用 Node.js (需要安装 http-server)
     npx http-server
     ```
   - 在浏览器中访问 `http://localhost:8000`

3. **使用流程**：
   - 打开网页后，首先显示欢迎语
   - 输入选手ID（例如：reclusive）
   - 点击"启程"按钮或按回车键
   - 通过点击、滑动或键盘操作翻页浏览报告

## 文件结构

```
.
├── README.md          # 项目说明文档
├── index.html        # 主网页文件
├── text.txt          # 报告文本内容
├── player.csv        # 选手数据（CSV格式，制表符分隔）
├── handwriting.ttf   # 手写字体文件（需要添加）
├── bg.jpg            # 背景图片（需要添加）
└── bgm.mp3           # 背景音乐（需要添加）
```

## 数据格式说明

### player.csv 格式
- 第一行为字段名（不包括player_name）
- 字段顺序：first_day, duration, stage, match, map, team, team_name, teammate, first_win, map_duplicate, most_map, hero, most_hero, hour, hero_stage1, hero_stage2, hero_stage3, kill, kill_date, team_kill, map_kill, kill_player, death, death_date, death_team, death_map, death_player, world_map, world_team, world_result, last_date, last_team, team_total
- 字段值为 "None" 或空字符串时，对应页面不会显示

### text.txt 格式
- 每行一个页面内容
- 使用 "x" 作为占位符，会被CSV中的字段按顺序替换
- 文本按空格分段显示

## 操作说明

- **鼠标点击**：点击屏幕左侧上一页，点击右侧下一页
- **移动端滑动**：向上滑动下一页，向下滑动上一页
- **键盘操作**：
  - 左/上方向键：上一页
  - 右/下方向键或空格键：下一页

## 技术栈

- HTML5
- CSS3（包含动画和响应式设计）
- JavaScript (原生，无依赖)
- Fetch API（读取文本和CSV文件）

## 注意事项

- 需要本地服务器运行，直接打开HTML文件可能会遇到CORS跨域问题
- 确保所有资源文件（字体、背景图、音乐）与HTML文件在同一目录
- CSV文件需要使用UTF-8编码保存，以避免中文乱码
- 如果字段值为None，对应的内容分段和整个页面都不会显示

## 许可证

MIT License
