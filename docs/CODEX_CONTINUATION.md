# 吴疆宇个人学术主页：Codex 接续说明

更新时间：2026-09-12

这份文件用于在新的 Codex 任务中继续维护网站。新任务应先阅读本文件，再修改或发布内容。

## 1. 项目位置与线上地址

- 本机项目目录：`/Users/wu-jiangyudem3/Documents/proooooz-al-folio-publish`
- 正式源码仓库：`https://github.com/proooooz/proooooz.github.io`
- 线上网站：`https://proooooz.github.io/`
- 正式源码分支：`master`
- GitHub Pages 产物分支：`gh-pages`，由自动流程生成，不要手动修改
- 本地 Git 远程：`personal` 指向个人网站仓库；`origin` 指向 al-folio 上游模板

## 2. 新 Codex 任务如何继续

在新任务中选择或打开上述本机项目目录，然后发送：

> 继续维护我的个人学术主页。请先完整阅读 `AGENTS.md` 和 `docs/CODEX_CONTINUATION.md`，以远程仓库 `proooooz/proooooz.github.io` 的 `master` 分支为正式版本。保留当前所有本地修改，不要清理、重置或覆盖无关文件。完成修改后运行项目已有检查，通过 GitHub PR 合并到 `master`，等待部署成功，并核对线上页面。

如果仍在同一台电脑上，新 Codex 任务可以直接访问这个目录和说明文件，因此能够继续工作。若换到另一台电脑，应先从正式源码仓库克隆 `master` 分支，再让 Codex 阅读本文件。

## 3. 当前技术结构

- 网站框架：al-folio v1.x
- 静态站点生成器：Jekyll
- Markdown 处理：Kramdown（GFM）
- 样式系统：Tailwind CSS 4 + al-folio 主题变量
- 部署方式：GitHub Actions 构建后发布到 GitHub Pages
- 网站语言：简体中文（`zh-CN`）
- 当前正式域名：`https://proooooz.github.io`
- 自定义域名尚未启用；启用时需同时更新 `_config.yml` 的 `url`、添加根目录 `CNAME` 并配置 DNS

GitHub Actions 工作流位于 `.github/workflows/jekyll-build.yml`。它在 PR 中执行完整构建；合并到 `master` 后，会生成站点并部署到 `gh-pages`。

## 4. 主要内容文件

### 顶部导航页面

- 首页/关于：`_pages/about.md`
- 论文与研究成果：`_pages/publications.md`
- 学习笔记：`_pages/notes.md`
- 学习资源入口：`_pages/resources.md`
- 数据入口：`_pages/data.md`

### 学习资源分类

- QSE 模型：`_pages/resources-qse.md`
- 计量经济学：`_pages/resources-econometrics.md`
- 高级宏观经济学：`_pages/resources-advanced-macro.md`
- HANK：`_pages/resources-hank.md`
- 经济学家：`_pages/resources-economists.md`
- 会议：`_pages/resources-conferences.md`
- 数学：`_pages/resources-mathematics.md`

### 数据分类

- 地理遥感数据：`_pages/data-geospatial.md`
- 国际贸易数据：`_pages/data-international-trade.md`
- 量化历史经济数据：`_pages/data-quantitative-history.md`
- 如何使用：`_pages/data-how-to-use.md`
- 相关文献：`_pages/data-references.md`
- 数据页面图片：`assets/img/data/`

### 全站配置

- 站点名称、网址、语言、导航与功能开关：`_config.yml`
- Ruby 依赖：`Gemfile`、`Gemfile.lock`
- JavaScript 检查脚本：`package.json`

## 5. 现有页面约定

- 顶部主导航顺序：关于、论文与研究成果、学习笔记、学习资源、数据、明暗主题按钮。
- “学习资源”和“数据”使用分类卡片；具体条目放在独立分类页中。
- 数据库条目使用连续编号，标题链接到官方网站或正式数据记录。
- 数据库说明使用 `<details class="resource-details">` 与 `<summary>详细介绍</summary>`，默认收起。
- 数据图片使用 `<figure class="resource-figure">`，存放在 `assets/img/data/`，并填写准确的中文替代文本。
- 正文链接颜色跟随黑白主题的文字颜色；分类卡片中的操作文字可保留主题强调色。
- 新增数据或课程前，应优先核对官方网站、作者主页、正式论文或数据仓库，避免使用搜索结果页和带追踪参数的链接。
- 年份范围统一使用中文破折号，例如 `2003—2022`。

## 6. 本地目录的重要状态

当前本地工作树包含多次网站维护留下的已修改文件和未跟踪文件，但这些文件是现有网站内容的一部分。新任务必须遵守：

- 不运行 `git clean`、`git reset --hard` 或批量还原命令。
- 不删除不属于本次请求的文件。
- 不把 `origin` 当作个人网站发布目标；`origin` 是 al-folio 上游模板。
- 正式版本以 `personal/master` 或 GitHub 仓库 `proooooz/proooooz.github.io` 的 `master` 为准。
- 修改某个文件前，先比较本地文件与远程 `master` 中同一路径的内容或 Git blob SHA。
- 只提交本次请求涉及的文件，避免把其他本地改动一起带入 PR。

## 7. 修改后的检查

只对本次修改涉及的文件执行格式化和检查：

```bash
./node_modules/.bin/prettier --write <修改的文件>
./node_modules/.bin/prettier --check <修改的文件>
node test/style_contract.js
git diff --check -- <修改的文件>
```

完整构建要求 Ruby 3.3.5 与 Bundler 4.0.6。本机系统 Ruby 可能无法完成构建，因此必须以 PR 中的 GitHub Actions 构建结果作为完整构建验证，不能因本机 Ruby 版本问题改动依赖文件。

## 8. 安全发布流程

1. 检查 GitHub 登录状态，确认可以访问 `proooooz/proooooz.github.io`。
2. 获取远程 `master` 最新提交和目标文件的远程版本。
3. 从最新 `master` 创建以 `codex/` 开头的临时分支。
4. 仅把本次修改的文件提交到临时分支。
5. 创建以 `master` 为目标的 Pull Request。
6. 等待 `Build and deploy al-folio` 的 PR 构建通过。
7. 使用 squash 方式合并 PR，并删除临时分支。
8. 等待 `master` 的部署任务成功。
9. 打开对应线上页面，核对新文字、链接、编号、折叠说明和图片是否正确。

不要直接修改 `gh-pages`。如 PR 构建失败，应先查看该次 Actions 日志并修复源文件，不能跳过检查直接发布。

## 9. 接续任务的完成标准

一次网站维护只有在以下事项全部完成后才算结束：

- 内容和位置符合用户要求。
- 外部链接能够直达正确的官方网站或数据记录。
- 格式检查通过。
- PR 完整构建通过并已合并。
- `master` 部署成功。
- 线上页面已核对。
- 向用户提供可以直接打开的线上页面链接。
