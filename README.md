# 📝 My Personal Blog | 我的个人博客项目

> 🚀 本博客基于 **[Hexo](https://hexo.io/zh-cn/)** 框架构建。
> 🌐 在线预览地址: **[https://heisa.ltd](https://heisa.ltd)**
> 📂 项目源文件托管于此移动硬盘/仓库中。

---

## 📋 目录 (Table of Contents)

- [📝 My Personal Blog | 我的个人博客项目](#-my-personal-blog--我的个人博客项目)
  - [📋 目录 (Table of Contents)](#-目录-table-of-contents)
  - [💻 环境准备 (Prerequisites)](#-环境准备-prerequisites)
  - [⚙️ VS Code 推荐配置 (VS Code Setup)](#️-vs-code-推荐配置-vs-code-setup)
    - [📦 核心插件列表](#-核心插件列表)
    - [🔧 推荐设置](#-推荐设置)
  - [🛠️ 新电脑首次配置指南 (New Device Setup)](#️-新电脑首次配置指南-new-device-setup)
    - [第 1 步：安装 Hexo 全局工具](#第-1-步安装-hexo-全局工具)
    - [第 2 步：安装/恢复项目依赖](#第-2-步安装恢复项目依赖)
    - [第 3 步：配置 GitHub SSH 密钥 (关键!)](#第-3-步配置-github-ssh-密钥-关键)
      - [1. 设置Git用户信息：](#1-设置git用户信息)
      - [2. 生成新的SSH 密钥（一路回车即可）：](#2-生成新的ssh-密钥一路回车即可)
      - [3. 获取密钥内容：](#3-获取密钥内容)
      - [4. 添加到 GitHub:](#4-添加到-github)
      - [5. 验证连接:](#5-验证连接)
  - [📝 日常写作流程 (Daily Workflow)](#-日常写作流程-daily-workflow)
    - [1. 新建文章 (Create)](#1-新建文章-create)
    - [2. 写作与预览 (Write \& Preview)](#2-写作与预览-write--preview)
    - [3. 发布上线 (Deploy)](#3-发布上线-deploy)
  - [❓ 常见问题 (Troubleshooting)](#-常见问题-troubleshooting)

---

## 💻 环境准备 (Prerequisites)

在一台新的电脑上开始写作前，请确保已安装以下基础软件：

| 软件 | 说明 | 下载地址 |
| :--- | :--- | :--- |
| **Node.js** | Hexo 的运行环境 (推荐选择 LTS 长期支持版) | [官网下载](https://nodejs.org/) |
| **Git** | 用于版本控制和发布博客到 GitHub | [官网下载](https://git-scm.com/) |
| **VS Code** | 推荐的 Markdown 编辑器 | [官网下载](https://code.visualstudio.com/) |

---

## ⚙️ VS Code 推荐配置 (VS Code Setup)

为了获得最佳的写作体验，推荐安装以下 VS Code 插件：

### 📦 核心插件列表

1.  **Markdown All in One**
    * *作用*: 提供 Markdown 快捷键（如 `Ctrl+B` 加粗）、自动生成目录、列表自动补全等功能。
2.  **PicGo**
    * *作用*: 写作痛点解决者。支持截图后直接粘贴 (`Ctrl+Alt+U`)，自动上传图片到图床并生成 Markdown 链接。
    * *注意*: 需要单独配置图床服务商（如 GitHub, SM.MS, 阿里云等）。
3.  **Hexo Utils**
    * *作用*: 为 VS Code 侧边栏增加 Hexo 常用命令按钮（新建文章、启动服务器、部署等），免去敲命令行的烦恼。

### 🔧 推荐设置
在 VS Code 中打开博客项目文件夹后，建议使用 `Ctrl + ~` 调出内置终端，方便直接执行 Hexo 命令。

---

## 🛠️ 新电脑首次配置指南 (New Device Setup)

当你在一台新电脑上插上移动硬盘，准备开始工作时，请按顺序执行以下步骤：

### 第 1 步：安装 Hexo 全局工具
打开终端 (PowerShell / CMD / Git Bash)，执行：
```bash
npm install -g hexo-cli
```

### 第 2 步：安装/恢复项目依赖
```bash
npm install
```

### 第 3 步：配置 GitHub SSH 密钥 (关键!)
为了能在一台新电脑上成功发布 (hexo d)，必须让 GitHub 信任这台电脑。

#### 1. 设置Git用户信息：
```bash
git config --global user.name "你的GitHub用户名"
git config --global user.email "你的GitHub注册邮箱"
```

#### 2. 生成新的SSH 密钥（一路回车即可）：
```bash
ssh-keygen -t rsa -C "你的GitHub注册邮箱"
```

#### 3. 获取密钥内容：
```bash
# Windows PowerShell 执行:
cat ~/.ssh/id_rsa.pub
```

#### 4. 添加到 GitHub:
- 复制上一步输出的以 ssh-rsa 开头的所有内容。
- 打开 GitHub SSH 设置页面。
- 点击 New SSH key，粘贴并保存。
#### 5. 验证连接:
```bash
ssh -T git@github.com
# 如果看到 "Hi [用户名]! You've successfully authenticated..." 即为成功
```

## 📝 日常写作流程 (Daily Workflow)
### 1. 新建文章 (Create)
```bash
hexo new "文章标题"
```
- 执行后，在 source/_posts/ 目录下会生成对应的 .md 文件。
### 2. 写作与预览 (Write & Preview)
在 VS Code 中编辑 Markdown 文件。随时可以通过以下命令开启本地服务器预览：
```bash
hexo clean   # 建议每次预览前清除缓存
hexo s       # 启动本地服务器
```
- 👉 浏览器访问: http://localhost:4000
### 3. 发布上线 (Deploy)

确认无误后，执行“三连”命令发布到 GitHub：

**Windows (PowerShell) 用户推荐使用分号连接:**
```bash
hexo cl; hexo g; hexo d
```

## ❓ 常见问题 (Troubleshooting)
- Q: 部署时提示 Permission denied (publickey)?
  - A: 新电脑没有配置 SSH 密钥，请重新执行 新电脑首次配置指南 中的第 3 步。
- Q: 执行 hexo 命令提示“无法识别”?
  - A: 可能是 Node.js 未安装，或未安装全局 Hexo CLI。请重新执行 npm install -g hexo-cli。
- Q: 部署后自定义域名失效了 (变成了 github.io)?
  - A: 检查 source/CNAME 文件是否存在且内容正确。每次部署 Hexo 都会根据这个文件重置 GitHub Pages 的域名设置。