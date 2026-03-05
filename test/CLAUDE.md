 # CLAUDE.md

此文件为 Claude Code (claude.ai/code) 提供在本代码库中工作时的重要信息。

## 项目概述

这是一个独立的 HTML/CSS/JavaScript 待办事项应用 (todo.html)，界面使用中文。

## 架构

单文件应用，所有功能都包含在一个 HTML 文件中：
- **CSS**: 嵌入在 `<style>` 标签中（第 7-236 行）
- **HTML 结构**: 第 238-268 行
- **JavaScript 逻辑**: 第 270-400 行

## 数据存储

任务使用浏览器 `localStorage` 进行持久化存储，键值为 `'tasks'`。每个任务对象包含：
- `id`: 基于时间戳的唯一标识符
- `text`: 任务描述
- `completed`: 布尔状态
- `priority`: 字符串 ('high', 'medium', 'low')
- `createdAt`: ISO 时间戳字符串

## 核心函数

- `renderTasks()`: 主要渲染函数，用于过滤和显示任务
- `addTask()`: 创建新任务，可选择优先级
- `toggleTask(id)`: 标记任务为已完成/未完成
- `deleteTask(id)`: 从列表中删除任务
- `setFilter(filter)`: 按完成状态过滤（全部/未完成/已完成）
- `setPriorityFilter(priority)`: 按优先级级别过滤
- `updateStats()`: 更新顶部的统计数据
- `escapeHtml(text)`: 通过清理用户输入来防止 XSS 攻击

## 优先级系统

优先级级别使用颜色编码：
- **高** (high): 红色 (#ff4757)
- **中** (medium): 橙色 (#ffa502)
- **低** (low): 绿色 (#2ed573)

## 运行方式

无需构建过程或测试框架。运行应用的方法：
1. 在浏览器中直接打开 `todo.html`
2. 任务在 localStorage 中跨会话持久化存储

## 用户操作

- 按 Enter 键或点击"添加"按钮来添加任务
- 点击复选框切换完成状态
- 悬停在任务上以显示删除按钮
- 使用过滤按钮按状态或优先级查看任务

