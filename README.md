# mkdocs 文档

在线部署 URL: https://genshin-impart.github.io/demo-doc/

## Python venv configuration

使用 Python 自带的 venv 虚拟环境。

```shell
python3 -m venv ./venv
cd venv
source ./bin/activate
```

## Requirements for mkdocs

```shell
pip install mkdocs mkdocstrings mkdocs-material mkdocs-glightbox
```

## Local preview

在项目根目录下执行如下命令：

```shell
mkdocs serve
```

即可预览当前文档。
