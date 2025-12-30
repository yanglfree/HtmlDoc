# 📚 技术知识快速查询手册库

本项目收集各知识领域的核心概念和常用知识点，以精美的 HTML 格式呈现，方便快速查阅和学习。

## 📖 文档目录

### 🤖 Android 开发

| 文档 | 描述 | 核心内容 |
|------|------|----------|
| [Android消息机制](android-message-mechanism.html) | Handler/Looper/MessageQueue | 消息循环、线程通信、Handler使用 |
| [Android系统启动流程](android-boot-process.html) | 从开机到桌面 | BootLoader→Kernel→Init→Zygote→SystemServer→Launcher |
| [Android视图渲染流程](android-view-rendering.html) | View绘制原理 | Measure→Layout→Draw、VSync、硬件加速、SurfaceFlinger |
| [Android内存优化指南](android-memory-optimization.html) | 内存管理最佳实践 | 内存泄漏、OOM、Bitmap优化、GC优化 |
| [Android四大组件](android-four-components.html) | 核心组件详解 | Activity、Service、BroadcastReceiver、ContentProvider |
| [Android多线程技术](android-multithreading.html) | 异步编程方案 | Thread、Handler、线程池、协程、RxJava、WorkManager |

### 🧠 AI / 大模型

| 文档 | 描述 | 核心内容 |
|------|------|----------|
| [大模型是如何工作的](llm-how-it-works.html) | LLM工作原理 | Transformer架构、注意力机制、分词、推理过程 |
| [Transformer架构详解](transformer-architecture.html) | 深度学习核心架构 | Attention机制、编码器/解码器、位置编码、变体架构 |
| [Agent意图理解与代码编写](agent-intent-and-coding.html) | AI Agent原理 | 意图理解、任务规划、工具调用、代码生成 |
| [如何训练一个大语言模型](llm-training-guide.html) | LLM训练流程 | 数据准备、预训练、SFT、RLHF、训练基础设施 |
| [Vibe Coding最佳实践](vibe-coding-guide.html) | AI辅助编程 | Prompt技巧、工作流程、工具选择、避坑指南 |

### 🛠️ 通用工具

| 文档 | 描述 | 核心内容 |
|------|------|----------|
| [正则表达式](regex-cheatsheet.html) | Regex速查 | 元字符、量词、分组、断言、各语言用法 |

---

## 🎨 HTML 生成规则

以下规则用于指导大模型生成统一风格的技术文档 HTML：

### 1. 整体设计风格

```
- 主题：深色模式 (Dark Theme)
- 背景色：#0d1117 (主背景), #161b22 (卡片), #21262d (高亮)
- 文字色：#e6edf3 (主文字), #8b949e (次要文字)
- 强调色：根据主题选择渐变色组合
  - 蓝紫系：#58a6ff, #a371f7
  - 绿蓝系：#3fb950, #58a6ff
  - 橙红系：#d29922, #f85149
- 边框色：#30363d
- 圆角：12px (卡片), 6-8px (小元素)
```

### 2. 页面结构

```html
1. 顶部 Hero 区域
   - 渐变背景 + 大标题 + 副标题
   - 标题使用 emoji + 渐变文字效果

2. 固定侧边目录导航 (TOC)
   - 位置：右上角固定
   - 响应式：移动端隐藏
   - 点击平滑滚动

3. 内容分区 (Section)
   - 每个 section 有锚点 id
   - 标题带左侧彩色竖条装饰

4. 知识点展示组件
   - 表格 (Table)：对比、参数说明
   - 卡片网格 (Cards)：概念分类
   - 代码块 (Pre/Code)：语法高亮
   - 提示框 (Tip)：注意事项
   - 流程图 (Flow)：步骤说明
   - 时间线 (Timeline)：顺序流程
```

### 3. 代码语法高亮

```css
.comment  { color: #8b949e; }  /* 注释 - 灰色 */
.keyword  { color: #a371f7; }  /* 关键字 - 紫色 */
.string   { color: #3fb950; }  /* 字符串 - 绿色 */
.type     { color: #39c5cf; }  /* 类型 - 青色 */
.number   { color: #d29922; }  /* 数字 - 橙色 */
```

### 4. 响应式设计

```css
- 最大宽度：1100px 居中
- 断点：1200px (隐藏TOC), 768px (移动端适配)
- 移动端：单列卡片、隐藏侧边栏、缩小字号
```

### 5. 内容组织原则

```
- 开篇概览：用卡片展示核心概念/分类
- 渐进深入：从基础到高级
- 代码示例：每个知识点配实际代码
- 对比表格：相似概念用表格对比
- 最佳实践：提供 ✅ 推荐 和 ❌ 避免
- 工具推荐：相关调试/开发工具
```

### 6. 文件命名规范

```
格式：{技术领域}-{具体主题}.html
示例：
  - android-message-mechanism.html
  - llm-how-it-works.html
  - regex-cheatsheet.html
```

### 7. 标准 HTML 模板

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{标题} - 快速查询手册</title>
    <style>
        /* CSS 变量定义 */
        :root {
            --bg: #0d1117;
            --bg2: #161b22;
            --bg3: #21262d;
            --text: #e6edf3;
            --text2: #8b949e;
            --accent1: #58a6ff;  /* 根据主题调整 */
            --accent2: #a371f7;
            --border: #30363d;
        }
        /* 基础样式、组件样式... */
    </style>
</head>
<body>
    <nav class="toc"><!-- 目录导航 --></nav>
    <div class="container">
        <div class="hero"><!-- 标题区 --></div>
        <section id="xxx" class="section"><!-- 内容分区 --></section>
    </div>
    <script>/* 目录平滑滚动 */</script>
</body>
</html>
```

---

## 📝 贡献新文档

生成新文档时，请遵循以下步骤：

1. **确定主题**：明确技术领域和具体知识点
2. **规划目录**：列出 5-8 个核心章节
3. **选择配色**：根据技术领域选择合适的渐变色
4. **编写内容**：遵循上述结构和组件规范
5. **测试响应式**：确保在不同屏幕尺寸下正常显示
6. **更新目录**：在本 README 中添加新文档链接

---

## 📄 License

MIT License - 自由使用和分发
