# 上传到GitHub并进行落地页部署

一个 Codex 技能：将已完成作品的完整代码公开到 GitHub，并通过 GitHub Pages 展示产品。已有网页就部署现有页面，没有网页则根据作品内容补充 HTML 落地页。

## 工作流程

1. 确认作品、目标账号及仓库，检查待公开内容。
2. 上传完整源码、必要资源与运行说明。
3. 使用现有网页，或为非网页作品制作介绍页。
4. 部署到 GitHub Pages，验证访问结果并交付链接。

最终发布产物必须包含 `index.html`。需要后端的作品可以展示介绍页；GitHub Pages 不代替后端运行环境。

## 安装到项目

将仓库中的 `github-open-source-pages/` 文件夹复制到你的项目 `.agents/skills/` 下，最终路径为：

```text
你的项目/.agents/skills/github-open-source-pages/SKILL.md
```

也可以在 Codex 中提供仓库链接，要求安装此技能到当前项目。源码位于 `github-open-source-pages/`；`.agents/skills/` 中有当前项目使用的同内容副本。

## 使用

```text
$github-open-source-pages 请把这个作品完整开源到 GitHub，并部署 HTML 展示页。
```

提供作品所在目录、目标仓库（如已有）及产品说明。技能会根据作品的实际形式选择展示路径，发布操作需要明确授权及可用的 GitHub 权限。

## 展示页

`docs/index.html` 是本技能的静态介绍页，不需要安装依赖或执行构建。可直接打开，或从项目根目录启动静态服务器：

```sh
python3 -m http.server 8765 --directory docs
```

打开 `http://localhost:8765`。在 GitHub 仓库的 Settings → Pages 中选择从 `main` 分支的 `/docs` 目录发布。

## 文件

- `github-open-source-pages/SKILL.md`：技能工作流。
- `github-open-source-pages/agents/openai.yaml`：中文界面名称及默认提示。
- `.agents/skills/github-open-source-pages/`：项目内安装副本。
- `docs/`：落地页以及可下载的技能文件。

本项目采用 [MIT 许可证](LICENSE)。再分发时须保留版权声明及许可文本。

公开展示页：https://3220164775-byte.github.io/github-open-source-pages/
