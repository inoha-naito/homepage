---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】rtxを用いたNode.jsの環境構築'
pubDate: 2023-05-09
description: 'バージョン管理ツール「rtx」を用いて、Node.jsの実行環境を構築します。「nodeコマンドを実行できる」が本記事のゴールです。'
author: '玖堂いのは'
tags: ["Node.js"]
---

# 【Node.js】rtxを用いたNode.jsの環境構築
バージョン管理ツール「rtx」を用いて、Node.jsの実行環境を構築します。  
「nodeコマンドを実行できる」が本記事のゴールです。

## 手順
インストール可能なプラグインを確認する。
```
rtx plugins ls-remote
```

Node.jsのプラグインをインストールする。
```
rtx plugins install nodejs
```

インストールされているプラグインを確認する。
```
rtx plugins ls
```

インストール可能なNode.jsのバージョンを確認する。
```
rtx ls-remote nodejs
```

任意のバージョンのNode.jsをインストールする。
```
rtx install nodejs@16.20.0
```

インストールされているNode.jsのバージョンを確認する。
```
rtx ls nodejs
```

システム全体に対して(ディレクトリを限定せずに)使用するバージョンを指定する場合は、以下のコマンドを実行する。
```
rtx global nodejs@16.20.0
```

現在のディレクトリに対して(ディレクトリごとに)使用するバージョンを指定する場合は、以下のコマンドを実行する。  
globalよりもlocalで指定したバージョンのほうが優先度は高い。
```
rtx local nodejs@16.20.0
```

現在使用しているNode.jsのバージョンを確認する。
```
node -v
```

## 参考
- jdxcode/rtx: Runtime Executor (asdf rust clone)  
  https://github.com/jdxcode/rtx
