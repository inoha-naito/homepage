---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Rust】rtxを用いたRustの環境構築'
pubDate: 2023-05-18
description: 'バージョン管理ツール「rtx」を用いて、Rustの実行環境を構築します。「cargoコマンドを実行できる」が本記事のゴールです。'
author: '玖堂いのは'
tags: ["Rust"]
---

# 【Rust】rtxを用いたRustの環境構築
バージョン管理ツール「rtx」を用いて、Rustの実行環境を構築します。  
「cargoコマンドを実行できる」が本記事のゴールです。

## 手順
インストール可能なプラグインを確認する。
```
rtx plugins ls-remote
```

Rustのプラグインをインストールする。
```
rtx plugins install rust
```

インストールされているプラグインを確認する。
```
rtx plugins ls
```

インストール可能なRustのバージョンを確認する。
```
rtx ls-remote rust
```

任意のバージョンのRustをインストールする。
```
rtx install rust@1.69.0
```

インストールされているRustのバージョンを確認する。
```
rtx ls rust
```

システム全体に対して(ディレクトリを限定せずに)使用するバージョンを指定する場合は、以下のコマンドを実行する。
```
rtx global rust@1.69.0
```

現在のディレクトリに対して(ディレクトリごとに)使用するバージョンを指定する場合は、以下のコマンドを実行する。  
globalよりもlocalで指定したバージョンのほうが優先度は高い。
```
rtx local rust@1.69.0
```

現在使用しているRustのバージョンを確認する。
```
cargo -V
```

## 参考
- jdxcode/rtx: Runtime Executor (asdf rust clone)  
  https://github.com/jdxcode/rtx
