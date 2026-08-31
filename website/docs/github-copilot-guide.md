# GitHub Copilot 使用指南

本文档介绍在 Visual Studio Code 中使用 GitHub Copilot 相关插件的最佳实践。

## GitHub Copilot 插件概述

在 Visual Studio Code 中，有两个主要的 GitHub Copilot 相关插件：

### 1. GitHub Copilot 插件

**主要功能：**
- 在编辑器中提供**实时代码自动补全**建议
- 根据上下文和注释自动生成代码
- 支持多行代码补全
- 以"幽灵文本"（ghost text）形式显示建议，可通过 Tab 键接受

**适用场景：**
- ✅ **编写代码**：在编写函数、类或方法时获得即时补全建议
- ✅ **实现算法**：根据注释或函数签名自动生成实现代码
- ✅ **编写测试**：快速生成单元测试代码
- ✅ **编写文档**：生成代码注释和文档字符串
- ✅ **重复性代码**：快速编写样板代码和重复模式

**工作方式：**
- 在您输入代码时自动激活
- 无需额外操作，建议会自动出现在光标位置
- 可以按 Tab 接受建议，或继续输入忽略建议

### 2. GitHub Copilot Chat 插件

**主要功能：**
- 提供**对话式交互界面**
- 可以提问并获得详细解释
- 支持代码解释、重构建议和问题解答
- 可以在侧边栏或编辑器内联使用
- 支持上下文感知的对话

**适用场景：**
- ✅ **阅读和理解开源代码**：询问代码的工作原理、设计模式、复杂算法的解释
- ✅ **代码审查**：请求代码改进建议、潜在 Bug 分析
- ✅ **学习新技术**：询问框架、库或编程概念的问题
- ✅ **调试协助**：讨论错误信息、寻求调试建议
- ✅ **重构建议**：获取代码优化和重构的具体方案
- ✅ **编写复杂文档**：讨论文档结构、获取写作建议

**工作方式：**
- 需要主动打开 Chat 面板或使用快捷键
- 通过自然语言与 AI 对话
- 可以选中代码后在 Chat 中询问相关问题

## 两者的主要区别

| 特性 | GitHub Copilot | GitHub Copilot Chat |
|------|---------------|---------------------|
| **交互方式** | 被动式自动补全 | 主动式对话交流 |
| **显示位置** | 编辑器内联 | 侧边栏 / 编辑器内联对话 |
| **响应类型** | 代码片段 | 详细解释 + 代码示例 |
| **适合任务** | 快速编码、自动补全 | 理解代码、学习、问题解答 |
| **工作流程** | 边写边补全 | 先问后做 |
| **上下文理解** | 当前文件及相关文件 | 可跨文件、跨项目讨论 |

## 使用场景建议

### 编写代码时

**推荐使用：GitHub Copilot 插件**
- 提供即时的代码补全
- 加快编码速度
- 减少语法错误

**示例：**
```cpp
// 在 Velox 项目中编写新函数时
// 输入注释后，Copilot 会自动建议实现
// Calculate the sum of two vectors
// [Copilot 会自动补全函数实现]
```

### 编写文档时

**推荐使用：GitHub Copilot 插件**（用于简单文档注释）
- 自动生成函数和类的文档字符串
- 快速补全常见文档格式

**推荐使用：GitHub Copilot Chat**（用于复杂文档）
- 讨论文档结构
- 获取写作建议和最佳实践
- 生成详细的技术说明

### 阅读开源代码时

**强烈推荐使用：GitHub Copilot Chat**
- 选中复杂代码片段，询问"这段代码是做什么的？"
- 询问"这个类的设计模式是什么？"
- 请求"解释这个算法的工作原理"
- 询问"这段代码有什么潜在问题吗？"

**示例对话：**
```
用户：选中一段 Velox 的向量处理代码
提问："这段代码如何处理 Dictionary 编码的向量？"

Copilot Chat：会提供详细解释，包括：
- Dictionary 编码的工作原理
- 这段代码的具体实现逻辑
- 性能考虑因素
```

## 计费方式

**重要说明：两个插件使用同一个订阅**

- GitHub Copilot 和 GitHub Copilot Chat 是**同一订阅服务**的不同功能
- 订阅 GitHub Copilot 后，自动包含 Chat 功能
- **无需单独付费**
- 定价选项：
  - **个人订阅**和**企业订阅**两种选项
  - 某些开源维护者和学生可免费使用
  - 具体价格请访问 [GitHub Copilot 官方定价页面](https://github.com/features/copilot#pricing)

## 在 Velox 项目中的最佳实践

### 1. 阅读 Velox 代码库时

使用 **GitHub Copilot Chat**：
```
选中代码 → 右键 → "Copilot: Explain This"
或在 Chat 中询问：
- "这个表达式求值引擎是如何工作的？"
- "解释 Vector 的内存布局"
- "这个 hash join 实现的优化策略是什么？"
```

### 2. 实现新的 Presto/Spark 函数时

使用 **GitHub Copilot**：
```cpp
// 1. 先写注释描述函数
// Implements the regexp_extract Presto function
// Extracts the first substring matched by regex pattern

// 2. Copilot 会根据注释自动建议实现
// 3. 按 Tab 接受建议或继续调整
```

配合 **GitHub Copilot Chat**：
- 询问函数的语义细节
- 请求边界情况处理建议
- 讨论性能优化方案

### 3. 编写测试代码时

使用 **GitHub Copilot**：
```cpp
// Test regexp_extract with various patterns
TEST_F(RegexpTest, testExtract) {
  // Copilot 会自动生成测试用例
}
```

### 4. 代码审查时

使用 **GitHub Copilot Chat**：
- 选中变更的代码
- 询问："这段代码有什么潜在问题？"
- 请求："建议如何改进这段代码的性能？"

## 快捷键

### GitHub Copilot
- `Tab`：接受建议
- `Esc`：拒绝建议
- `Alt + ]`：下一个建议
- `Alt + [`：上一个建议
- `Ctrl + Enter`：打开 Copilot 建议面板

### GitHub Copilot Chat
- `Ctrl + Shift + I`（Windows/Linux）或 `Cmd + Shift + I`（macOS）：打开内联 Chat
- 打开侧边栏 Chat：点击活动栏中的 Chat 图标，或在命令面板中搜索 "GitHub Copilot Chat"
- 提示：可以在 VS Code 设置中自定义键盘快捷键

## 隐私和安全考虑

在使用 GitHub Copilot 时：
- 代码片段会发送到 GitHub 服务器进行处理
- 建议的代码可能来自公开的代码库
- 对于敏感或专有代码，请谨慎使用
- 企业可以配置策略来控制使用范围

## 总结

| 任务 | 推荐工具 | 原因 |
|------|---------|------|
| 编写代码 | **GitHub Copilot** | 实时补全，提高效率 |
| 编写简单文档/注释 | **GitHub Copilot** | 自动生成文档字符串 |
| 编写复杂文档 | **GitHub Copilot Chat** | 讨论结构，获取建议 |
| 阅读开源代码 | **GitHub Copilot Chat** | 详细解释，深入理解 |
| 学习新概念 | **GitHub Copilot Chat** | 对话式学习 |
| 调试问题 | **GitHub Copilot Chat** | 分析错误，获取建议 |
| 代码审查 | **GitHub Copilot Chat** | 发现问题，改进建议 |

**最佳实践：** 两个工具结合使用，Copilot 用于快速编码，Chat 用于深入理解和学习。
