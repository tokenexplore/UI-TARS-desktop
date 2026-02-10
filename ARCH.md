# UI-TARS-desktop 项目工程架构分析

## 项目概述
UI-TARS-desktop 是一个基于 Electron 的桌面应用程序，采用 monorepo 架构，使用 pnpm 进行包管理，Turbo 作为构建系统。

## 主要目录结构

### 1. 根目录结构
```
UI-TARS-desktop/
├── apps/                 # 应用程序源码
│   └── ui-tars/          # 主应用
├── packages/             # 共享包
│   ├── agent-infra/      # 代理基础设施包
│   ├── common/           # 公共库
│   └── ui-tars/          # UI相关的共享组件
├── docs/                 # 文档
├── examples/             # 示例代码
├── images/               # 图片资源
├── infra/                # 基础设施相关
├── multimodal/           # 多模态相关组件
├── rfcs/                 # RFC 文档
├── scripts/              # 脚本
└── .github/              # GitHub 相关配置
```

### 2. Apps 目录 - 主应用程序 (apps/ui-tars/)
主应用程序包涵以下关键部分：
- `src/` - 源代码
- `electron.vite.config.ts` - Electron Vite 配置
- `electron-builder.yml` - Electron 打包配置
- `forge.config.ts` - Electron Forge 配置
- `playwright.config.ts` - Playwright 测试配置
- `e2e/` - 端到端测试
- `resources/` - 资源文件（图标、图片等）
- `static/` - 静态文件
- `build/` - 构建相关配置
- `images/` - 各种应用场景的图片

### 3. Packages 目录 - 共享包
- `agent-infra/` - 可能包含代理服务器或后端基础设施代码
- `common/` - 可能是公共工具函数、类型定义和通用组件
- `ui-tars/` - UI 组件库或其他 UI 相关的共享代码

### 4. 配置文件
- `package.json` - 项目配置
- `pnpm-workspace.yaml` - pnpm 工作区配置
- `turbo.json` - Turbo 构建系统配置
- `tsconfig.json` - TypeScript 配置
- `vitest.config.mts` - Vitest 测试配置
- `.eslintrc.cjs` - ESLint 配置
- `.prettierrc.mjs` - Prettier 配置

### 5. 开发工具配置
- `.husky/` - Git hooks
- `.changeset/` - 版本变更管理
- `.github/` - GitHub Actions 工作流

### 6. 文档和资源
- `README.md` - 项目说明
- `CONTRIBUTING.md` - 贡献指南
- `CODE_OF_CONDUCT.md` - 行为准则
- `LICENSE` - 许可证

## 技术栈
- **框架**: Electron（桌面应用）
- **构建工具**: Vite, Turbo
- **包管理**: pnpm
- **语言**: TypeScript
- **测试**: Vitest, Playwright (e2e)
- **代码质量**: ESLint, Prettier
- **CI/CD**: GitHub Actions

## 架构特点
1. **Monorepo 结构**: 使用 pnpm workspace 管理多个包
2. **模块化设计**: apps 和 packages 分离，便于复用
3. **现代前端技术栈**: TypeScript + 适当的构建工具链
4. **完整开发生命周期**: 包含单元测试、端到端测试和质量保证工具
5. **多平台支持**: Electron 支持 Windows、Mac、Linux 平台

## 应用特性
- 支持 Windows, Mac 等多平台
- 包含自动化安装流程
- 提供设置界面和控制功能
- 具备预设功能（import/export presets）
- 支持多种部署方式（HuggingFace, VolcEngine API 等）

这是一个结构清晰、维护良好且具有专业级开发规范的现代化桌面应用项目。