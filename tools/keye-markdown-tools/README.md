# keye-markdown-tools

> **科爷的 Markdown 处理工具集** - 高效处理 YAML Front Matter、格式转换、文档生成

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Markdown](https://img.shields.io/badge/Markdown-MD-blue.svg)](https://commonmark.org/)

---

## 📚 关于这个项目

这是一套实用的 Markdown 处理工具，专注于：
- ✅ **YAML Front Matter 处理** - 验证、格式化、转换
- ✅ **格式转换** - Markdown ↔ HTML ↔ PDF
- ✅ **批量处理** - 批量操作 Markdown 文件
- ✅ **质量检查** - 语法检查、链接验证

**核心理念**：
- 🎯 **简单高效** - 一个命令完成复杂操作
- 📊 **数据驱动** - 支持元数据分析和提取
- 💡 **实用至上** - 解决真实文档处理需求

---

## 🚀 快速开始

### 安装
```bash
# 克隆仓库
git clone https://github.com/keyelifeai/keye-markdown-tools.git
cd keye-markdown-tools

# 安装依赖（如果有）
npm install  # 或 pip install -r requirements.txt
```

### 基本使用

#### 1. YAML Front Matter 验证
```bash
# 验证单个文件
./bin/yaml-validator.md path/to/file.md

# 验证整个目录
./bin/yaml-validator.md path/to/directory/
```

#### 2. Markdown 格式化
```bash
# 格式化单个文件
./bin/md-formatter path/to/file.md

# 批量格式化
./bin/md-formatter path/to/directory/
```

#### 3. 元数据提取
```bash
# 提取 YAML 元数据
./bin/meta-extractor path/to/file.md

# 批量提取并导出 JSON
./bin/meta-extractor path/to/directory/ --output meta.json
```

---

## 🛠️ 工具列表

### YAML Front Matter 工具

#### `yaml-validator` - YAML 验证器
验证 Markdown 文件的 YAML Front Matter 格式是否正确。

**特性**：
- ✅ 语法验证
- ✅ 必填字段检查
- ✅ 字段类型验证
- ✅ 自定义规则支持

**使用**：
```bash
./bin/yaml-validator path/to/file.md
```

#### `yaml-formatter` - YAML 格式化器
自动格式化 YAML Front Matter，确保一致性。

**特性**：
- ✅ 字段排序
- ✅ 缩进统一
- ✅ 引号规范化
- ✅ 多行字符串优化

**使用**：
```bash
./bin/yaml-formatter path/to/file.md
```

---

### 格式转换工具

#### `md-to-html` - Markdown 转 HTML
将 Markdown 文件转换为 HTML。

**特性**：
- ✅ 保留 YAML 元数据
- ✅ 自定义 CSS 样式
- ✅ 代码高亮
- ✅ 数学公式支持

**使用**：
```bash
./bin/md-to-html path/to/file.md --output path/to/output.html
```

#### `md-to-pdf` - Markdown 转 PDF
将 Markdown 文件转换为 PDF。

**特性**：
- ✅ 专业排版
- ✅ 自定义页眉页脚
- ✅ 目录生成
- ✅ 元数据嵌入

**使用**：
```bash
./bin/md-to-pdf path/to/file.md --output path/to/output.pdf
```

---

### 批量处理工具

#### `batch-processor` - 批量处理器
对整个目录的 Markdown 文件执行操作。

**特性**：
- ✅ 批量验证
- ✅ 批量格式化
- ✅ 批量转换
- ✅ 进度显示

**使用**：
```bash
./bin/batch-processor path/to/directory/ --operation format
```

---

### 质量检查工具

#### `md-linter` - Markdown 语法检查
检查 Markdown 文件的语法问题。

**特性**：
- ✅ 链接有效性
- ✅ 图片引用检查
- ✅ 标题层级验证
- ✅ 代码块语法

**使用**：
```bash
./bin/md-linter path/to/file.md
```

#### `link-validator` - 链接验证器
验证 Markdown 文件中的所有链接。

**特性**：
- ✅ 内部链接检查
- ✅ 外部链接验证
- ✅ 图片引用检查
- ✅ 锚点链接验证

**使用**：
```bash
./bin/link-validator path/to/file.md
```

---

## 📖 YAML Front Matter 规范

### 标准格式
```yaml
---
title: 文章标题
description: 文章描述
date: 2026-05-10
tags:
  - Tag1
  - Tag2
  - Tag3
author: 作者名
category: 分类
status: published # draft/published/archived
---
```

### 字段说明
- **title** (必填): 文章标题
- **description** (可选): 文章描述
- **date** (必填): 创建日期
- **tags** (可选): 标签数组
- **author** (可选): 作者
- **category** (可选): 分类
- **status** (可选): 状态

---

## 🎨 使用场景

### 场景 1: 内容发布前检查
```bash
# 1. 验证 YAML 格式
./bin/yaml-validator content/article.md

# 2. 检查链接
./bin/link-validator content/article.md

# 3. 转换为 HTML
./bin/md-to-html content/article.md --output dist/article.html
```

### 场景 2: 批量处理内容库
```bash
# 批量格式化
./bin/batch-processor content/ --operation format

# 批量验证
./bin/batch-processor content/ --operation validate

# 提取所有元数据
./bin/meta-extractor content/ --output metadata.json
```

### 场景 3: 生成文档网站
```bash
# 1. 转换所有文章为 HTML
./bin/batch-processor content/ --operation to-html --output dist/

# 2. 生成目录
./bin/sitemap-generator content/ --output dist/sitemap.xml

# 3. 优化图片
./bin/image-optimizer content/ --output dist/
```

---

## 📂 目录结构

```
keye-markdown-tools/
├── README.md                   # 本文件
├── bin/                        # 可执行脚本
│   ├── yaml-validator
│   ├── yaml-formatter
│   ├── md-to-html
│   ├── md-to-pdf
│   ├── batch-processor
│   ├── md-linter
│   └── link-validator
├── lib/                        # 核心库
│   ├── yaml-parser.js
│   ├── markdown-processor.js
│   └── format-validator.js
├── tests/                      # 测试
│   ├── yaml.test.js
│   └── markdown.test.js
├── examples/                   # 示例
│   ├── basic-usage.md
│   └── advanced-usage.md
├── docs/                       # 文档
│   ├── api.md
│   ├── configuration.md
│   └── troubleshooting.md
└── package.json                # 项目配置
```

---

## 🔧 配置

### 项目配置 (`.md-tools.json`)
```json
{
  "yaml": {
    "requiredFields": ["title", "date"],
    "fieldOrder": ["title", "description", "date", "tags", "author"],
    "tagFormat": "CamelCase"
  },
  "markdown": {
    "lineWidth": 80,
    "listIndent": 2,
    "codeBlockStyle": "fenced"
  },
  "output": {
    "htmlTemplate": "templates/default.html",
    "pdfOptions": {
      "format": "A4",
      "margin": "2cm"
    }
  }
}
```

---

## 🤝 贡献指南

欢迎贡献工具和改进！

### 贡献原则
1. **实用至上** - 解决真实问题
2. **简单高效** - 易于使用和维护
3. **文档完整** - 包含使用说明和示例
4. **测试充分** - 包含单元测试

详见 [CONTRIBUTING.md](CONTRIBUTING.md)

---

## 🔗 相关项目

- **[keye-open-prompts]** - 提示词库
- **[keye-open-skills]** - Useful Agent skills collection
- **[keye-markdown-mastery]** - Markdown 学习笔记与处理工具

---

## 📮 反馈与建议

- 🐦 **X (Twitter)**: [@keyelifeai](https://x.com/keyelifeai)
- 📧 **Email**: keyelifeai@gmail.com
- 💼 **GitHub Issues**: [提交问题](https://github.com/keyelifeai/keye-markdown-tools/issues)

---

## ⭐ 如果这个项目对你有帮助

请给个 ⭐ Star 支持一下！

---

## 📄 许可证

本项目采用 [MIT License](LICENSE) 开源许可证。

---

<div align="center">

**💡 简单高效，数据驱动，实用至上**

Made with ❤️ by [Keye (科爷)](https://github.com/keyelifeai)

</div>
