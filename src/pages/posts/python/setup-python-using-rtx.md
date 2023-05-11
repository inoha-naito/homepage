---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Python】rtxを用いたPythonの環境構築'
pubDate: 2023-05-11
description: 'バージョン管理ツール「rtx」を用いて、Pythonの実行環境を構築します。「pythonコマンドを実行できる」が本記事のゴールです。'
author: '玖堂いのは'
tags: ["Python"]
---

# 【Python】rtxを用いたPythonの環境構築
バージョン管理ツール「rtx」を用いて、Pythonの実行環境を構築します。  
「pythonコマンドを実行できる」が本記事のゴールです。

## 手順
インストール可能なプラグインを確認する。
```
rtx plugins ls-remote
```

Pythonのプラグインをインストールする。
```
rtx plugins install python
```

インストールされているプラグインを確認する。
```
rtx plugins ls
```

インストール可能なPythonのバージョンを確認する。
```
rtx ls-remote python
```

任意のバージョンのPythonをインストールする。
```
rtx install python@3.11.3
```

インストールされているPythonのバージョンを確認する。
```
rtx ls python
```

システム全体に対して(ディレクトリを限定せずに)使用するバージョンを指定する場合は、以下のコマンドを実行する。
```
rtx global python@3.11.3
```

現在のディレクトリに対して(ディレクトリごとに)使用するバージョンを指定する場合は、以下のコマンドを実行する。  
globalよりもlocalで指定したバージョンのほうが優先度は高い。
```
rtx local python@3.11.3
```

現在使用しているPythonのバージョンを確認する。
```
python -V
```

## 参考
- jdxcode/rtx: Runtime Executor (asdf rust clone)  
  https://github.com/jdxcode/rtx
