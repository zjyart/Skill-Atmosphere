<p align="center">
  <img src="public/skill-atmosphere-logo.png" width="112" alt="Skill Atmosphere 标志" />
</p>

<h1 align="center">Skill Atmosphere</h1>

<p align="center">
  面向 macOS 的安静、local-first AI Skill 工作空间。<br />
  将本机 Skills、研究意图、Prompt 编译与个人知识收藏组织成一个能力空间。
</p>

<p align="center">
  <a href="README.md">English</a> · <strong>简体中文</strong>
</p>

![Skill Atmosphere Research](screenshots/github-research.png)

## 项目简介

Skill Atmosphere 不是传统文件管理器，也不是聊天机器人外壳。它以 macOS 工作流为基础，将本机安装的 AI Skills 组织成可以浏览、选择与组合的个人能力空间。

用户可以从一句自然语言任务开始。应用会搜索本机 Skill 目录，推荐相关能力，允许用户调整 Skill 的角色，并在保留原始意图的前提下编译结构化 Prompt。本地确定性推荐不需要 API；只有用户自行填写凭据并明确允许传输后，模型增强才会启用。

## 核心体验

- **Research**：描述任务、匹配本机 Skills，并编译可执行 Prompt。
- **System Recommendations**：在空间轨道场景中查看推荐 Skill，并调整其角色。
- **Library**：扫描 macOS 上真实安装的 Codex 与 Agent Skills，不使用演示目录冒充本机数据。
- **Favorites**：在本机保存并编辑 Prompt、研究笔记和设计资料。
- **Settings**：控制氛围、动效、声音、模型连接、传输许可和 Skill 路径。
- **Offline Preview**：生成不依赖服务器和端口的独立 HTML 文件。

## 视觉方向

界面使用冷白留白、淡蓝与淡紫光场、浅桃环境光、雾化 Orb 和克制的空间动效。目标是接近 macOS 与 Vision Pro 工作空间的安静质感，而不是 dashboard、SaaS 后台或高饱和科技界面。

![本机 Skill Library](screenshots/github-library.png)

## API 与隐私

本仓库 **不包含任何内置 API Key 或开发者凭据**。

- 本机 Skill 扫描与确定性推荐无需 API。
- 用户可在 `Settings -> Model & API` 中填写自己的 OpenAI、DeepSeek 或 OpenAI-compatible 凭据。
- 设置导出与完整工作区备份会自动移除 API 凭据。
- 只有用户开启传输并主动开始 Research 后，Prompt 才会发送。
- 发布前可运行 `npm run security:check` 检查公开源码中的疑似凭据。

当前保护方式与限制请阅读[安全说明](SECURITY.zh-CN.md)。

## 技术栈

- React + TypeScript + Vite
- Motion for React
- Tauri 2 + Rust
- Lucide icons
- CSS 氛围材质与 reduced-motion 支持

## 本地运行

```bash
npm install
npm run dev
```

运行 macOS 开发版：

```bash
npm run desktop:dev
```

## 构建

```bash
# Web 正式构建
npm run build

# 独立离线 HTML
npm run build:local

# macOS App
npm run desktop:app
```

## 验证

```bash
npm run security:check
npm run test:recommendations
cd src-tauri && cargo test
```

## 项目结构

```text
src/components/       界面组件与工作空间页面
src/lib/              本机扫描、路由和模型适配层
src/data/             预览数据与 Research Skill 目录
src-tauri/            macOS 运行时与本机 Skill 扫描器
scripts/              发布、离线构建、图标和安全工具
tests/                推荐、Prompt 编译与凭据测试
```

## 当前状态

Skill Atmosphere 目前处于 beta 阶段。Web 构建主要用于视觉预览与快速调试，macOS App 是主要分发对象。正式公开分发仍需要 Apple Developer ID 签名与 notarization。

## 贡献

欢迎提交 Issue 或 Pull Request。涉及界面的修改应保持 calm、spatial、local-first 的设计原则，并同时检查完整动效与减少动态效果模式。

## License

项目尚未选择许可证。在正式添加许可证之前，源代码默认保留所有权利。
