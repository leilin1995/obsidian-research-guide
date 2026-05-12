[Uploading README.md…]()
# obsidian-research-guide
面向科研人员的 Obsidian 使用指南：文献管理、项目追踪、知识地图与 AI Agent/MCP 工作流。An Obsidian workflow guide for researchers: literature notes, project tracking, knowledge maps, and AI Agent/MCP integration.
# Obsidian 科研人员使用指南

> 本教程面向在读博士生、科研工作者，帮助你用 Obsidian 建立一套 **文献管理 + 项目追踪 + 知识积累** 一体化的笔记系统。从零开始，约需 1 小时完成配置。

---

## 目录

1. [为什么科研人员需要 Obsidian](#1-为什么科研人员需要-obsidian)
2. [核心概念：PARA + Zettelkasten](#2-核心概念para--zettelkasten)
3. [推荐的 Vault 目录结构](#3-推荐的-vault-目录结构)
4. [必装插件及使用方法](#4-必装插件及使用方法)
5. [三个核心模板](#5-三个核心模板)
6. [用 Dataview 打造自动化主页](#6-用-dataview-打造自动化主页)
7. [MOC：知识地图的使用方法](#7-moc知识地图的使用方法)
8. [连接 AI Agent 与 Obsidian](#8-连接-ai-agent-与-obsidian)
9. [用 AI 自动整理 Inbox（Codex Prompt）](#9-用-ai-自动整理-inboxcodex-prompt)
10. [每周工作流](#10-每周工作流)
11. [常见问题](#11-常见问题)

---

## 1. 为什么科研人员需要 Obsidian

科研工作面临的典型问题：

- 文献越读越多，读过就忘，无法形成体系
- 进行中的论文、项目、基金分散在不同软件里
- 会议记录、实验日志、想法碎片没有统一的地方存放
- 知识之间缺少连接，难以触类旁通

**Obsidian 的核心优势：**

| 特性 | 说明 |
|---|---|
| 纯本地 Markdown | 文件永久属于你，不依赖任何云服务 |
| 双向链接 `[[]]` | 笔记之间像神经元一样互相关联 |
| 图谱视图 | 可视化知识网络，发现隐藏关联 |
| 插件生态 | 数百个社区插件，可深度定制 |
| 免费 | 个人使用完全免费 |

---

## 2. 核心概念：PARA + Zettelkasten

### 2.1 PARA 方法论

PARA 由 Tiago Forte 提出，把所有信息按**可执行性**分为四类：

```text
P - Projects（项目）   有明确目标和截止时间
A - Areas（领域）     长期持续维护，无明确终止点
R - Resources（资源） 未来某天可能用到的参考资料
A - Archive（归档）   已完成或暂时搁置的内容
```

**科研场景映射：**

| PARA | 科研对应内容 |
|---|---|
| Projects | 正在写的论文、申请中的基金、进行中的实验 |
| Areas | 文献阅读管理、教学事务、实验室事务 |
| Resources | 文献笔记库、学习资源、论文写作方法 |
| Archive | 已发表论文、已完成项目、历史材料 |

### 2.2 Zettelkasten（卡片笔记法）

德国社会学家卢曼发明的笔记方法，核心原则：

- **原子性**：一篇笔记只记一个想法
- **链接优先**：用 `[[]]` 连接相关笔记，而不是靠文件夹归类
- **永久笔记**：用自己的话复述，而不是摘抄原文

**在 Obsidian 中的实践：**

- 读完一篇文献，用自己的话写 1 页文献笔记
- 产生新想法，新建一个 atomic note，并用 `[[]]` 链接相关文献
- 不要过度纠结放哪个文件夹，链接比位置更重要

### 2.3 两者结合

```text
PARA         -> 解决“文件放哪里”的问题（宏观组织）
Zettelkasten -> 解决“笔记如何连接”的问题（知识增值）
```

---

## 3. 推荐的 Vault 目录结构

```text
Obsidian Vault/
│
├── 00 Inbox/              ← 所有新内容先到这里
│
├── 10 Projects/           ← 进行中的项目（每个项目一个子文件夹）
│   ├── Paper-Project-A/
│   ├── Grant-Proposal-A/
│   └── Collaboration-Project-A/
│
├── 20 Areas/              ← 长期维护的领域
│   ├── Literature-Reading/
│   ├── Teaching/
│   └── Lab-Admin/
│
├── 30 Resources/          ← 参考资料（按主题）
│   ├── Literature/
│   │   ├── 01 Research-Topic-A/
│   │   └── 02 Research-Topic-B/
│   ├── Learning-Notes/
│   ├── Academic-Writing/
│   ├── Templates/         ← 模板存放处
│   └── MOC/               ← 知识地图索引
│
├── 40 Archive/            ← 已完成/搁置
│   ├── Published-Papers/
│   └── Completed-Projects/
│
├── Attachments/           ← 图片、PDF
├── zz_To-Clean/           ← 定期清理（可选）
└── _Dashboard.md          ← 主页（下划线开头排最前）
```

**关键原则：**

- 层级不超过 3 层，越扁平越好
- 新内容**先进 Inbox**，每周整理一次
- 项目完成后整个文件夹**移入 Archive**

---

## 4. 必装插件及使用方法

在 Obsidian 中安装：**Settings → Community plugins → Browse → 搜索安装**。

### 4.1 Pixel Banner

**作用**：给笔记添加顶部横幅图片，让主页更美观。

**安装后使用**：在笔记 frontmatter 里加：

```yaml
---
banner: "https://images.unsplash.com/photo-1557683304-673a23048d34?w=1920&q=80"
banner_y: 0.5
banner_height: 200
---
```

支持本地图片 `![[image.jpg]]` 和网络 URL，`banner_y` 控制图片垂直位置（0=顶部，1=底部）。

### 4.2 Templater

**作用**：比内置模板更强大，支持动态日期、变量、自动触发。

**配置**：Settings → Templater → Template folder location → 填 `30 Resources/Templates`。

**使用**：新建笔记时按 `Ctrl/Cmd+P` → 输入 `Templater: Open Insert Template Modal` → 选择模板。

### 4.3 Dataview

**作用**：把笔记当数据库查询，自动生成动态列表和表格。

**无需配置**，装完即可用。在笔记里写代码块：

````markdown
```dataview
TABLE file.mtime AS "修改时间"
FROM "10 Projects"
SORT file.mtime DESC
```
````

### 4.4 Zotero Integration

**作用**：将 Zotero 文献库与 Obsidian 打通，一键导入文献笔记。

**前置条件**：Zotero 桌面端需安装 **Better BibTeX** 插件。

**使用**：`Ctrl/Cmd+P` → `Zotero Integration: Import literature note` → 搜索文献 → 自动建笔记。

### 4.5 Calendar

**作用**：侧边栏显示日历，点击日期直接创建/跳转 Daily Note。

**配置**：Settings → Daily notes → New file location 填 `00 Inbox`，Template 填 `30 Resources/Templates/Daily Note Template`。

### 4.6 Tasks

**作用**：跨笔记汇总 `- [ ] 待办事项`，可设截止日期。

**使用**：写任务时加日期：

```markdown
- [ ] 提交审稿意见 📅 2026-06-01
```

然后用查询汇总所有未完成任务：

````markdown
```tasks
not done
due before next month
```
````

### 4.7 Obsidian Git

**作用**：自动把 vault 备份到 GitHub，相当于版本控制。

**配置**：先在终端 `git init` 初始化 vault → 关联 GitHub 远程仓库 → Settings → Obsidian Git → Auto backup interval 设为 `30`（分钟）。

---

## 5. 三个核心模板

> 将以下模板保存到 `30 Resources/Templates/` 文件夹，配合 Templater 使用。

### 5.1 文献笔记模板

```markdown
---
tags: [literature]
title:
authors:
year:
journal:
doi:
status: unread   # unread / reading / read
topic:           # 研究方向，如：research-topic-a
---

# {{title}}

## 一句话摘要


## 关键贡献

-

## 方法核心

-

## 数据集 / 实验

-

## 与当前项目的关联

- 与 [[Project-A]] 相关：

## 可借鉴的图 / 公式 / 代码

-

## 待跟进

- [ ]
```

### 5.2 项目笔记模板

```markdown
---
tags: [project]
type:            # paper / grant / experiment / collaboration
status: active   # active / paused / completed
start:
deadline:
---

# {{项目名}}

## 目标 & 产出


## 关键节点

- [ ]
- [ ]

## 进度日志

### {{date}}


## 相关文献

- [[]]

## 相关代码 / 数据

-
```

### 5.3 Daily Note 模板

```markdown
---
tags: [daily]
date: {{date}}
---

# {{date:YYYY-MM-DD}}

## 今日重点

- [ ]

## 进展


## 想法（随手记）

-

## 明日待办

- [ ]
```

---

## 6. 用 Dataview 打造自动化主页

在 `_Dashboard.md` 里添加以下查询块，主页内容会**自动更新**，无需手动维护。

### 进行中项目（按最近修改排序）

````markdown
```dataview
TABLE rows.file.link AS "文件", dateformat(max(rows.file.mtime), "yyyy-MM-dd HH:mm") AS "最近修改"
FROM "10 Projects"
GROUP BY file.folder
SORT max(rows.file.mtime) DESC
```
````

### Inbox 待处理

````markdown
```dataview
LIST FROM "00 Inbox"
SORT file.ctime ASC
```
````

### 最近 7 天更新

````markdown
```dataview
TABLE file.folder AS "位置", dateformat(file.mtime, "MM-dd HH:mm") AS "修改时间"
FROM ""
WHERE file.mtime >= date(today) - dur(7 days)
AND !contains(file.path, "Attachments")
SORT file.mtime DESC
LIMIT 15
```
````

### 最新入库文献

````markdown
```dataview
TABLE file.folder AS "研究方向", dateformat(file.ctime, "yyyy-MM-dd") AS "入库时间"
FROM "30 Resources/Literature"
SORT file.ctime DESC
LIMIT 10
```
````

**进阶技巧**：在文献笔记 frontmatter 里加 `status: unread`，然后查询未读文献：

````markdown
```dataview
TABLE authors, year, journal
FROM "30 Resources/Literature"
WHERE status = "unread"
SORT file.ctime DESC
```
````

---

## 7. MOC：知识地图的使用方法

**MOC（Map of Content）** 是一种索引笔记，作用是把同一主题下分散的笔记汇聚成一张“地图”，方便导航和发现关联。

**与文件夹的区别：**

| 文件夹 | MOC |
|---|---|
| 物理容器，文件只能在一个地方 | 虚拟索引，同一笔记可出现在多个 MOC |
| 层级固定 | 可以跨文件夹、跨主题自由链接 |
| 靠位置组织 | 靠链接和标签组织 |

**创建方法：**

1. 在 `30 Resources/MOC/` 下新建 `Research-Topic-A-MOC.md`
2. 按逻辑分组，用 `[[]]` 链接相关笔记
3. 加上简短的说明和导读

**示例结构：**

```markdown
# Research Topic A MOC

## 研究背景
- [[Topic-A-Overview]] - 综述
- [[Topic-A-Key-Concepts]]

## 方法路线
- [[Method-A]]
- [[Method-B]]

## 数据与实验
- [[Dataset-A]]
- [[Experiment-Notes-A]]

## 与当前项目的关联
- [[Project-A]] 参考方法：Method-A + Evaluation-B
- [[Project-B]] 复用了数据处理流程
```

---

## 8. 连接 AI Agent 与 Obsidian

让 AI 直接读写你的 vault，是 Obsidian 最强大的进阶用法。目前有四种主流接入方式，按推荐程度排列：

| 方式 | 适合场景 | 难度 |
|---|---|---|
| **方式 A：MCP + Codex**（推荐） | 在 Codex 里对话式搜索、整理、修改 vault | ★★☆ |
| **方式 B：MCP + Claude Desktop** | Claude 桌面对话式操作 vault | ★★☆ |
| **方式 C：Claude Code CLI / Codex CLI 直接访问** | 自动化脚本、批量处理 | ★☆☆ |
| **方式 D：REST API + 自定义脚本** | 与 n8n / Python / 其他工具集成 | ★★★ |

### 方式 A：MCP + Codex（推荐）

**原理**：Obsidian 的 `Local REST API` 插件在本地开启一个 HTTP 服务，`obsidian-mcp-server` 把这个服务包装成 MCP 工具，Codex 再通过 MCP 调用这些工具。配置完成后，你就可以在 Codex 里直接说“搜索我的 Obsidian”“修改某篇笔记”“把 Inbox 整理成项目页”，Codex 会通过 MCP 读写 vault。

```text
Codex  ←→  obsidian-mcp-server（MCP）  ←→  Local REST API 插件  ←→  Obsidian Vault
```

#### 第一步：配置 Local REST API 插件

1. Obsidian → Settings → Community plugins，安装并启用 **Local REST API**。
2. 进入 Settings → **Local REST API**。
3. 复制 API Token。
4. 确认本地地址和端口，通常是 `https://127.0.0.1:27124`。
5. 保持 Obsidian 运行，否则 MCP 无法通过 REST API 访问 vault。

#### 第二步：安装 obsidian-mcp-server

建议把 MCP server 安装在 Codex 专用目录里：

```bash
mkdir -p ~/.codex/mcp/obsidian-mcp-server
cd ~/.codex/mcp/obsidian-mcp-server
npm init -y
npm install obsidian-mcp-server
```

安装完成后，入口文件通常在：

```text
~/.codex/mcp/obsidian-mcp-server/node_modules/obsidian-mcp-server/dist/index.js
```

#### 第三步：把 MCP server 添加到 Codex

方式一：使用 `codex mcp add` 命令：

```bash
codex mcp add obsidian \
  --env MCP_TRANSPORT_TYPE=stdio \
  --env MCP_LOG_LEVEL=info \
  --env OBSIDIAN_API_KEY=YOUR_OBSIDIAN_REST_TOKEN \
  --env OBSIDIAN_BASE_URL=https://127.0.0.1:27124 \
  --env OBSIDIAN_VERIFY_SSL=false \
  -- node ~/.codex/mcp/obsidian-mcp-server/node_modules/obsidian-mcp-server/dist/index.js
```

方式二：手动编辑 Codex 配置文件 `~/.codex/config.toml`，添加：

```toml
[mcp_servers.obsidian]
type = "stdio"
command = "node"
args = ["/Users/YOUR_LOCAL_USER/.codex/mcp/obsidian-mcp-server/node_modules/obsidian-mcp-server/dist/index.js"]
enabled = true

[mcp_servers.obsidian.env]
MCP_TRANSPORT_TYPE = "stdio"
MCP_LOG_LEVEL = "info"
OBSIDIAN_API_KEY = "YOUR_OBSIDIAN_REST_TOKEN"
OBSIDIAN_BASE_URL = "https://127.0.0.1:27124"
OBSIDIAN_VERIFY_SSL = "false"
```

> 注意：`OBSIDIAN_API_KEY` 不要写进公开仓库或截图里。它相当于访问整个 vault 的钥匙。

#### 第四步：检查连接

在终端运行：

```bash
codex mcp list
codex mcp get obsidian
```

如果能看到 `obsidian`，且状态是 `enabled`，说明 Codex 已经识别到这个 MCP server。之后重启 Codex，或重新打开一个 Codex 会话。

#### 第五步：在 Codex 中使用

配置完成后，就不需要每次手动运行命令了。你可以直接在 Codex 里说：

```text
在我的 Obsidian 里搜索所有提到 Model-A 的笔记，并总结共同点。

打开《Obsidian 科研人员使用指南》，把 AI Agent 连接方式补充 Codex 的 MCP 安装方法。

把 00 Inbox 里最近 7 天的零散想法整理成 3 个项目笔记，并保留原始链接。

读取某篇论文笔记，帮我生成一版可以放到周报里的进展摘要。
```

Codex 会自动调用 Obsidian MCP 工具进行搜索、读取、追加、替换或创建笔记。涉及大量文件或高风险修改时，可以先说“先列计划，不要直接改”。

### 方式 B：MCP + Claude Desktop

**原理**：Obsidian 的 `Local REST API` 插件在本地开启一个 HTTP 服务，MCP Server 把这个服务包装成 Claude 可调用的工具，Claude Desktop 就能直接操作你的 vault。

```text
Claude Desktop  ←→  mcp-obsidian（MCP Server）  ←→  Local REST API 插件  ←→  Obsidian Vault
```

#### 第一步：配置 Local REST API 插件

1. Obsidian → Settings → **Local REST API**
2. 复制 API Token
3. 确认端口号（默认 `27124`）
4. 确保插件处于**启用状态**，Obsidian 须保持运行

#### 第二步：安装 mcp-obsidian

打开终端，运行：

```bash
npm install -g mcp-obsidian
```

> 如果你的系统有 `uv`（Python 包管理器），也可以用 `uvx mcp-obsidian`，无需全局安装。

#### 第三步：配置 Claude Desktop

编辑 Claude Desktop 的配置文件：

- **macOS**：`~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**：`%APPDATA%\\Claude\\claude_desktop_config.json`

在文件中添加（如果 `mcpServers` 字段不存在则新建）：

```json
{
  "mcpServers": {
    "obsidian": {
      "command": "npx",
      "args": ["-y", "mcp-obsidian"],
      "env": {
        "OBSIDIAN_API_KEY": "YOUR_OBSIDIAN_REST_TOKEN",
        "OBSIDIAN_HOST": "127.0.0.1",
        "OBSIDIAN_PORT": "27124"
      }
    }
  }
}
```

#### 第四步：重启 Claude Desktop

重启后，在对话框里会出现工具图标，点开能看到 Obsidian 相关工具，说明连接成功。

#### 连接成功后可以做什么

```text
你：帮我在 Inbox 里新建一篇关于 Research Topic A 的文献笔记
Claude：（直接在你的 vault 里创建文件）

你：搜索我所有提到 Model-A 的笔记
Claude：（全文检索 vault，返回相关内容）

你：把“10 Projects/Project-A”里的进展日志整理成周报
Claude：（读取文件，生成总结，写入新笔记）
```

**MCP 提供的工具列表：**

| 工具 | 功能 |
|---|---|
| `list_files_in_vault` | 列出 vault 所有文件 |
| `list_files_in_dir` | 列出指定目录内容 |
| `get_file_contents` | 读取文件内容 |
| `search` | 全文搜索 |
| `patch_content` | 在指定位置插入内容 |
| `append_content` | 在文件末尾追加内容 |
| `delete_file` | 删除文件 |

### 方式 C：Claude Code CLI / Codex CLI 直接访问

**无需任何插件**，Claude Code 或 Codex CLI 在终端里运行时可以直接读写 vault 的 `.md` 文件，因为 Obsidian 的笔记本质上就是普通文本文件。

**使用方法**：在 vault 目录下启动对应工具：

```bash
cd /path/to/your/vault
claude
# 或
codex
```

启动后，它们就能直接用文件读写、搜索、编辑和终端工具操作笔记。

**适合场景：**

- 批量处理（给 100 篇文献笔记统一加 frontmatter）
- 自动化脚本（每周一整理 Inbox，见第 9 节）
- 复杂重构（重命名文件夹、合并笔记等）

**局限：** 需要手动在 vault 目录启动，更像“工程化批处理”。如果想在日常聊天里持续调用 Obsidian，更推荐方式 A 的 MCP 配置。

### 方式 D：REST API + 自定义脚本

`Local REST API` 插件提供了完整的 HTTP API，可以与任何支持 HTTP 请求的工具集成。

**常用接口：**

```bash
# 读取文件
curl -H "Authorization: Bearer YOUR_OBSIDIAN_REST_TOKEN" \
  http://127.0.0.1:27124/vault/path/to/note.md

# 创建/更新文件
curl -X PUT \
  -H "Authorization: Bearer YOUR_OBSIDIAN_REST_TOKEN" \
  -H "Content-Type: text/markdown" \
  --data-binary "# New note content" \
  http://127.0.0.1:27124/vault/00\ Inbox/new-note.md

# 全文搜索
curl -H "Authorization: Bearer YOUR_OBSIDIAN_REST_TOKEN" \
  "http://127.0.0.1:27124/search/simple/?query=Research%20Topic%20A"
```

**适合与以下工具集成：**

- **n8n / Make**：搭建无代码自动化工作流
- **Python 脚本**：用 `requests` 库操作 vault
- **快捷指令（iOS/macOS Shortcuts）**：手机端快速记录到 Inbox

### 四种方式对比

| | MCP + Codex | MCP + Claude Desktop | Claude Code / Codex CLI | REST API |
|---|---|---|---|---|
| 操作方式 | Codex 聊天调用工具 | Claude 桌面对话 | 命令行交互 | 代码调用 |
| 需要 Obsidian 运行 | 需要 | 需要 | 不需要 | 需要 |
| 实时性 | 即时 | 即时 | 手动触发 | 程序控制 |
| 上手难度 | 低 | 低 | 低 | 中 |
| 推荐用途 | 日常整理、检索、修改 | Claude 用户日常问答 | 批量自动化 | 与第三方工具集成 |

---

## 9. 用 AI 自动整理 Inbox（Codex Prompt）

每周把以下 Prompt 交给任意支持代码执行的 AI 助手（如 OpenAI Codex、Claude 等），让它自动扫描 Inbox 并归类。

> 使用前修改：将 `/Users/YOUR_LOCAL_USER/Documents/YOUR_VAULT_NAME` 替换为你自己的 vault 路径，并更新 `10 Projects/` 下的子目录列表。

```text
你是我的 Obsidian vault 整理助手。我的 vault 路径是：
/Users/YOUR_LOCAL_USER/Documents/YOUR_VAULT_NAME

## 你的任务
扫描 `00 Inbox/` 下的所有 .md 文件，逐一阅读内容，判断最合适的归档位置，然后用 shell 命令移动文件。最后输出一份整理报告。

## Vault 的 PARA 结构

### 10 Projects/（进行中项目）
现有子目录：（填写你的项目名称）
- Paper-Project-A
- Grant-Proposal-A

### 20 Areas/（长期责任领域）
现有子目录：（填写你的 Areas）
- Literature-Reading
- Teaching
- Lab-Admin

### 30 Resources/（参考资料）
现有子目录：
- Literature/（按研究方向细分）
- Learning-Notes/（工具、编程）
- Academic-Writing

### 40 Archive/（已完成）
现有子目录：（填写你的归档项目）

## 分类规则（按优先级）
1. 与进行中项目直接相关 → `10 Projects/对应项目/`
2. 文献阅读笔记 → `30 Resources/Literature/对应方向/`
3. 工具/代码/软件笔记 → `30 Resources/Learning-Notes/对应子目录/`
4. 科研新想法 → `30 Resources/Research-Ideas/`
5. 教学、管理、长期维护事项 → `20 Areas/` 对应子目录
6. 已完成事项 → `40 Archive/`
7. 内容明确但无合适目录 → 在最匹配的父目录下新建子目录，命名风格与同级目录保持一致
8. 内容极度模糊或空文件 → 保留在 `00 Inbox/`，报告中注明原因

## 执行步骤
1. `ls "00 Inbox/"` 列出所有文件
2. 逐一 `cat` 读取内容
3. 判断目标路径；需要新目录时先 `mkdir -p` 再移动
4. `mv` 移动文件
5. 结果追加写入 `20 Areas/Literature-Reading/inbox整理日志.md`

## 整理日志格式
---
### YYYY-MM-DD 整理
| 文件名 | 移动到 | 分类理由 | 是否新建目录 |
|---|---|---|---|
| xxx.md | 30 Resources/Literature/Research-Topic-A/ | Research Topic A 文献 | 新建 |
| yyy.md | 00 Inbox/（保留） | 内容仅有标题 | — |

共处理 N 个文件，移动 M 个（新建目录 X 个），保留 K 个。
---

现在开始执行，先列出 Inbox 内容。
```

---

## 10. 每周工作流

```text
周一早上（15 分钟）
├── 打开 _Dashboard.md 查看 Inbox 和最近更新
├── 把 Inbox 里的内容用 AI Prompt 一键整理
└── 检查整理日志，确认无误

周中随时
├── 新笔记 → 直接扔进 00 Inbox/，不纠结放哪里
├── 读新文献 → 用文献笔记模板，填完 frontmatter
└── 记录进展 → 在对应项目文件夹里追加

周五下午（10 分钟）
├── 项目笔记更新进度日志
├── 已完成的任务打勾 [x]
└── 已结束项目 → 整个文件夹移入 40 Archive/
```

---

## 11. 常见问题

**Q：文件放哪个文件夹，我总是纠结怎么办？**

先放 Inbox，周一再整理。或者放一个“感觉差不多”的地方，之后可以移动。Obsidian 的 `[[链接]]` 不依赖位置，移动文件不会断链。

**Q：同一篇文献和好几个项目都相关，怎么办？**

文件只放一个地方（文献库），在多个项目笔记里用 `[[文献名]]` 引用。这是 Zettelkasten 相比文件夹的核心优势。

**Q：Dataview 查询显示空白？**

1. 检查 Dataview 插件是否启用。
2. 检查 FROM 后面的路径是否和实际文件夹名一致，路径区分大小写。

**Q：banner 图片不显示？**

需要安装 Pixel Banner 插件。安装后重新打开笔记即可。

**Q：Obsidian 打开变慢了？**

1. 检查附件文件夹是否有过大的视频文件。
2. 在 Settings → Files & Links 里排除附件文件夹的索引。
3. 关闭不常用的插件。

**Q：用 Zotero 还是直接在 Obsidian 管理文献？**

两者互补：**Zotero 管 PDF + 引用格式**，**Obsidian 管阅读笔记和知识连接**。用 Zotero Integration 插件把两者打通是最佳实践。

---

## 延伸阅读

- [Obsidian 官方文档](https://help.obsidian.md)
- [PARA Method 原文 — Tiago Forte](https://fortelabs.com/blog/para/)
- [How to Take Smart Notes — Sönke Ahrens](https://takesmartnotes.com/)
- [Obsidian 论坛 Science Research Vault 模板](https://forum.obsidian.md/t/science-research-vault-a-structured-workflow-for-academics/95589)

---

*本教程基于通用科研工作流整理，适合理工科、人文社科、工程与跨学科研究人员参考。欢迎根据自身领域调整目录结构和分类规则。*
