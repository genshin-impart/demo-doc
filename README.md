# mkdocs 文档

在线部署 URL: https://genshin-impart.github.io/demo-doc/

## Python venv configuration

使用 Python 自带的 venv 虚拟环境。

```shell
python3 -m venv ./venv
```

激活虚拟环境

- Linux

```shell
source venv/bin/activate
```

- Windows

```shell
.\venv\Scripts\Activate.ps1
```

## Requirements for mkdocs

```shell
pip install mkdocs mkdocstrings mkdocs-material mkdocs-glightbox
```

## Preview and deployment

### Preview local

在项目根目录下执行如下命令：

```shell
mkdocs serve
```

即可预览当前文档。

### Deploy online

在项目根目录下执行如下命令（非必须）：

```shell
mkdocs build
```

即可将 `docs` 目录下的 markdown 文档转换为网页代码并存放在 `site` 目录下。

执行命令

```shell
mkdocs gh-deploy
```

即可将网页发布到 `gh-deploy` 分支下的 github pages 中。
