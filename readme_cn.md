# Academic Pages
**Academic Pages 是一个用于个人与职业作品展示的 GitHub Pages 模板。**

![Academic Pages template example](images/themes/homepage-light.png "Academic Pages template example")

# 快速开始

1. 如果你还没有 GitHub 账号，请先注册并完成邮箱验证（必须）。
1. 点击右上角的 “Use this template” 按钮。
1. 在 “New repository” 页面中，将公开仓库名设置为 "[你的 GitHub 用户名].github.io"，这也会成为你的网站 URL。
1. 在 `_config.yml` 中编辑站点级配置，并再次确认 `url` 是你上一步设置的地址，`repository` 也要与你仓库路径一致。
1. 添加你的网站内容，并将附件（如 PDF、zip 等）上传到 `files/` 目录。之后可通过 https://[你的 GitHub 用户名].github.io/files/example.pdf 访问。
1. 到仓库 Settings 的 “GitHub Pages” 区域查看构建状态。
1. （可选）使用 `markdown_generator` 目录中的 Jupyter Notebook 或 Python 脚本，根据 TSV 文件自动生成论文与报告的 Markdown 页面。

更多信息请见：https://academicpages.github.io/

### 额外教程

可参考以下教程学习如何使用 Academic Pages 模板：
- https://jayrobwilliams.com/posts/2020/06/academic-website/

## 本地运行

在你开始建设网站时，先本地预览再推送到 GitHub 会非常有用。要在本地运行，你需要：

1. 克隆仓库，并按上文完成修改。

### 使用其他 IDE
1. 确保已安装 ruby-dev、bundler、nodejs。
    
    在大多数 Linux 发行版和 [Windows Subsystem Linux](https://learn.microsoft.com/en-us/windows/wsl/about) 中，可执行：
    ```bash
    sudo apt install ruby-dev ruby-bundler nodejs
    ```
    如果出现 `Unable to locate package ruby-bundler` 或 `Unable to locate package nodejs`，先执行：
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```
    然后再次执行 `sudo apt install ruby-dev ruby-bundler nodejs`。

    在 MacOS 中可执行：
    ```bash
    brew install ruby
    brew install node
    gem install bundler
    ```
1. 执行 `bundle install` 安装 Ruby 依赖。若报错，可删除 Gemfile.lock 后重试。

    如果出现权限错误，例如 `Fetching bundler-2.6.3.gem ERROR:  While executing gem (Gem::FilePermissionError) You don't have write permissions for the /var/lib/gems/3.2.0 directory.` 或 `Bundler::PermissionError: There was an error while trying to write to /usr/local/bin.`，
    推荐改为本地安装 Gems：
    ```bash
    bundle config set --local path 'vendor/bundle'
    ```
    然后再次执行 `bundle install`。成功后你会看到 `vendor` 和 `.bundle` 目录。

1. 执行 `jekyll serve -l -H localhost` 来生成 HTML，并在 `localhost:4000` 提供本地服务。修改 Markdown（*.md）和 HTML 文件时会自动重建与刷新；但修改核心模板或配置（例如 `_config.yml`）后，需要停止并重启 Jekyll。
   你也可以尝试 `bundle exec jekyll serve -l -H localhost`，确保 Jekyll 使用本机指定依赖。

如果你使用 Linux，可能还需先安装额外依赖：`sudo apt install build-essential gcc make`

## 使用 Docker

如果你使用不同操作系统，或不想在本机安装依赖，可使用仓库内提供的 `Dockerfile` 构建容器运行站点（前提是已安装 [Docker](https://www.docker.com/)）。

在仓库目录执行：

```bash
chmod -R 777 .
docker compose up
```

随后可通过 `localhost:4000` 访问网站。

### 在 VS Code 中使用 DevContainer

如果你使用 [Visual Studio Code](https://code.visualstudio.com/)，可以直接使用本仓库附带的 [Dev Container](https://code.visualstudio.com/docs/devcontainers/containers)。通常 VS Code 会自动检测并提示是否进入容器环境；若未提示，可手动执行 **F1->DevContainer: Reopen in Container**。这会在容器中重启 VS Code，并自动在 http://localhost:4000 本地托管页面。之后你的改动会在数秒内实时更新。

# 维护说明

模板相关的 Bug 报告和功能请求可通过 [GitHub Issues](https://github.com/academicpages/academicpages.github.io/issues/new/choose) 提交。关于模板样式问题，欢迎在 [GitHub Discussions](https://github.com/academicpages/academicpages.github.io/discussions) 发起讨论。

本仓库由 [Stuart Geiger](https://github.com/staeiou) 从 [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/) 分叉（后解除 fork 关系），该主题版权归 Michael Rose（© 2016），并遵循 MIT 许可证（见 LICENSE.md）。当前维护者为 [Robert Zupko](https://github.com/rjzupkoii)，也欢迎更多维护者加入。

## Bug 修复与增强

如果你希望通过 Pull Request 提交修复或增强，请先 [fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo) 本仓库，而不是直接使用模板创建仓库。这样也便于你后续 [同步模板更新](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork)。

Academic Pages 这类模板主题在同步上游修复时有一定复杂度：如果你已经大量定制，很可能在同步时遇到合并冲突。通常可通过 [rebase](https://git-scm.com/docs/git-rebase) 搭配手动 [cherry-pick](https://git-scm.com/docs/git-cherry-pick) 相关提交解决。如果你不熟悉 Git 命令行，也可以先备份各类 `.yml` 配置与 Markdown 文件，再删除仓库并重新 fork。

---
<div align="center">
    
![pages-build-deployment](https://github.com/academicpages/academicpages.github.io/actions/workflows/pages/pages-build-deployment/badge.svg)
[![GitHub contributors](https://img.shields.io/github/contributors/academicpages/academicpages.github.io.svg)](https://github.com/academicpages/academicpages.github.io/graphs/contributors)
[![GitHub release](https://img.shields.io/github/v/release/academicpages/academicpages.github.io)](https://github.com/academicpages/academicpages.github.io/releases/latest)
[![GitHub license](https://img.shields.io/github/license/academicpages/academicpages.github.io?color=blue)](https://github.com/academicpages/academicpages.github.io/blob/master/LICENSE)

[![GitHub stars](https://img.shields.io/github/stars/academicpages/academicpages.github.io)](https://github.com/academicpages/academicpages.github.io)
[![GitHub forks](https://img.shields.io/github/forks/academicpages/academicpages.github.io)](https://github.com/academicpages/academicpages.github.io/fork)
</div>
