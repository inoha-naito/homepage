---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】Node.jsのバージョンを自動で切り替える'
pubDate: 2023-05-11
description: '.node-versionというファイルにNode.jsのバージョンを指定することで、プロジェクト内で使用するNode.jsのバージョンに自動で切り替わります。.node-versionをサポートしているバージョン管理ツールと.node-versionで指定したバージョンのNode.jsがインストールされている想定です。'
author: '玖堂いのは'
tags: ["Node.js"]
---

# 【Node.js】Node.jsのバージョンを自動で切り替える
.node-versionというファイルにNode.jsのバージョンを指定することで、  
プロジェクト内で使用するNode.jsのバージョンに自動で切り替わります。  
.node-versionをサポートしているバージョン管理ツールと  
.node-versionで指定したバージョンのNode.jsがインストールされている想定です。

## 手順
プロジェクトのルートディレクトリに.node-versionというファイルを作成し、  
以下のように編集する。
```
16.20.0
```

上記の内容は、以下のコマンドでも可能。
```
echo "16.20.0" > .node-version
```

## 参考
- shadowspawn/node-version-usage: Document current usage of .node-version file  
  https://github.com/shadowspawn/node-version-usage
