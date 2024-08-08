+++
title = '使用Hugo搭建个人博客'
date = 2024-08-07T22:53:03+08:00
draft = true

+++

## 1. 安装 Hugo

Windows

```powershell
winget install Hugo.Hugo.Extended
```

MacOS

```shell
brew install hugo
```

Linux

```shell
sudo apt-get install hugo
```

## 2. 创建新项目

```shell
hugo new site my-hugo-site
```

```
cd my-hugo-site
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
```

## 3. 创建 GitHub 仓库

访问 [repo.new](https://repo.new/)，创建新的 GitHub 存储库，并将其推送到 GitHub。

```shell
git add .
git git commit -m "first commit"
git remote add origin https://github.com/<your-gh-username>/<repository-name>
git push -u origin main
```

## 4. 使用 Cloudflare Pages 进行部署

在 Cloudflare dashboard](https://dash.cloudflare.com/) 创建 Pager 应用程序，连接到 Git 选择刚才创建的 GitHub 仓库。

| 配置选项     | 值     |
| :----------- | :----- |
| 生产分支     | main   |
| 框架预设     | Hugo   |
| 构建命令     | hugo   |
| 构建输出目录 | public |

使用更新的 Hugo 版本，设置环境变量，例如：

| 变量名称     | 值      |
| :----------- | ------- |
| HUGO_VERSION | 0.131.0 |

完成部署配置后，点击**保存并部署**。
