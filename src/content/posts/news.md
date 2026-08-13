---
title: 测试
published: 2026-08-03
description: 测试
image:  ./images/lv1.png
tags: [前端, 开发]
category: 测试
draft: false
---

# 以下是测试段
| 语言 | 后缀写法 |
|---|---|
| C | `c` |
| C++ | `cpp` |
| Python | `python` |
| JavaScript | `js` |
| TypeScript | `ts` |
| Java | `java` |
| HTML | `html` |
| CSS | `css` |
| Bash / Shell | `bash` |
| JSON | `json` |
| SQL | `sql` |
| Markdown | `markdown` |


---
好的，我把我们讨论的关于 **Markdown / Astro 中的文本颜色与高亮** 的核心知识整理成一份总结，你可以直接复制保存为 `.md` 文件使用。

---

# Markdown 文本颜色与高亮

## 1. 颜色表示方式

### 十六进制（HEX）
- 格式：`#RRGGBB`
- `#` 是标记符，后面紧跟红、绿、蓝三个通道的十六进制值（`00`-`FF`）
- 示例：`#E06C75` 表示红 `E0`、绿 `6C`、蓝 `75`
- 简写：`#E67` 等价于 `#EE6677`

### RGB 函数
- 格式：`rgb(R, G, B)`
- 每个通道取值 `0`-`255`
- 示例：`rgb(224, 108, 117)`

### 颜色关键字
- 如 `red`、`blue`、`yellow`，方便但选择有限

浏览器最终都会将各种表示方式转换为 RGB 像素显示。

---

## 2. 在 Markdown 中设置文字颜色

标准 Markdown 不支持直接改变文字颜色，需要借助 **内联 HTML**。

```markdown
<span style="color:#E06C75;">这是红色文字</span>
<span style="color:rgb(152, 195, 121);">这是绿色文字</span>
```

**注意：** GitHub 等平台会过滤内联样式，但 **Astro 博客默认支持**。

---

## 3. 在 Markdown 中设置背景高亮（荧光笔效果）

### 方法一：使用 `<mark>` 标签（推荐）

```markdown
<mark>默认黄色背景</mark>
```

自定义颜色：

```markdown
<mark style="background-color:#fff9c4;color:#f57f17;">自定义背景和文字颜色</mark>
```

### 方法二：使用 `==高亮==`（仅 Obsidian、Typora 等支持，Astro 不支持）

```markdown
==高亮文字==
```

---

## 4. 好看的配色方案

### 文字颜色（适合技术博客）

| 风格 | HEX | 示例写法 |
|---|---|---|
| 柔和水红 | `#E06C75` | `<span style="color:#E06C75;">文字</span>` |
| 清新绿 | `#98C379` | `<span style="color:#98C379;">文字</span>` |
| 天空蓝 | `#61AFEF` | `<span style="color:#61AFEF;">文字</span>` |
| 暖橙 | `#D19A66` | `<span style="color:#D19A66;">文字</span>` |
| 薰衣草紫 | `#C678DD` | `<span style="color:#C678DD;">文字</span>` |
| 静谧青 | `#56B6C2` | `<span style="color:#56B6C2;">文字</span>` |

### 背景高亮配色（背景色 + 文字色）

| 风格 | 背景色 | 文字色 | 示例写法 |
|---|---|---|---|
| 柔雾粉 | `#fce4ec` | `#880e4f` | `<mark style="background-color:#fce4ec;color:#880e4f;">文字</mark>` |
| 薄荷绿 | `#e8f5e9` | `#1b5e20` | `<mark style="background-color:#e8f5e9;color:#1b5e20;">文字</mark>` |
| 奶油黄 | `#fff9c4` | `#f57f17` | `<mark style="background-color:#fff9c4;color:#f57f17;">文字</mark>` |
| 婴儿蓝 | `#e3f2fd` | `#0d47a1` | `<mark style="background-color:#e3f2fd;color:#0d47a1;">文字</mark>` |
| 灰紫 | `#ede7f6` | `#4a148c` | `<mark style="background-color:#ede7f6;color:#4a148c;">文字</mark>` |
| 高级灰 | `#eceff1` | `#263238` | `<mark style="background-color:#eceff1;color:#263238;">文字</mark>` |

### 整体页面配色示例

#### 深色主题
- 背景：`#1e1e1e`
- 正文：`#d4d4d4`
- 标题：`#ffffff`
- 链接：`#61afef`
- 高亮：背景 `#2c2c2c` + 文字 `#e5c07b`

#### 浅色主题
- 背景：`#fafafa`
- 正文：`#2d2d2d`
- 标题：`#111111`
- 链接：`#0366d6`
- 高亮：背景 `#fff9c4` + 文字 `#333`

---

## 5. 在 Astro 中更好的实践方式

推荐在 **CSS 中定义类**，然后在 Markdown 中引用类名，而不是每次写内联样式。

在 `src/styles/global.css` 中添加：

```css
/* 文字颜色类 */
.text-red   { color: #E06C75; }
.text-green { color: #98C379; }
.text-blue  { color: #61AFEF; }
.text-orange{ color: #D19A66; }
.text-purple{ color: #C678DD; }
.text-cyan  { color: #56B6C2; }

/* 背景高亮类 */
.mark-pink   { background-color: #fce4ec; color: #880e4f; padding: 0 4px; border-radius: 4px; }
.mark-green  { background-color: #e8f5e9; color: #1b5e20; padding: 0 4px; border-radius: 4px; }
.mark-yellow { background-color: #fff9c4; color: #f57f17; padding: 0 4px; border-radius: 4px; }
.mark-blue   { background-color: #e3f2fd; color: #0d47a1; padding: 0 4px; border-radius: 4px; }
.mark-purple { background-color: #ede7f6; color: #4a148c; padding: 0 4px; border-radius: 4px; }
.mark-gray   { background-color: #eceff1; color: #263238; padding: 0 4px; border-radius: 4px; }
```

然后在 Markdown 中：

```markdown
这是一个 <span class="text-red">红色文字</span> 示例。
这是一个 <mark class="mark-yellow">黄色高亮</mark> 示例。
```

---

## 6. 小结

- 使用 `<span>` 或 `<mark>` 配合 `style` 属性可在 Markdown 中直接设置颜色。
- `#` 是十六进制颜色值的标记，不是数字本身。
- Astro 支持内联样式，但用 CSS 类更整洁、易维护。
- 选择颜色时建议使用低饱和度、高可读性的配色，避免刺眼。

---

这份总结可以保存为 `.md` 文件，方便日后查阅。如果你在 Astro 或 Markdown 中实际使用时还有问题，欢迎随时继续提问！