---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】TypeScriptのコードの変更を検知して、自動で再実行する'
pubDate: 2023-05-13
description: '「ts-node-dev」を使用して、TypeScriptのコードの変更を検知して自動で再実行します。'
author: '玖堂いのは'
tags: ["Node.js", "TypeScript"]
---

# 【Node.js】TypeScriptのコードの変更を検知して自動で再実行する
「ts-node-dev」を使用して、TypeScriptのコードの変更を検知して自動で再実行します。

本記事は下記の内容を踏襲しています。  
[【Node.js】ExpressでWeb APIを作成する](../hello-express)

## 手順
以下のコマンドを実行して、必要なパッケージをインストールする。
```
npm install -D ts-node-dev
```

以下のコマンドを実行すると、コンソールに「Server listening on port 3000」と出力され、  
Webブラウザで http://localhost:3000/ping にアクセスすると「pong」という文字列だけのページが表示される。  
./src/app.tsで「pong」を「pong!」に変更すると、コードの変更を検知して自動で再実行され、  
Webブラウザで http://localhost:3000/ping に再びアクセスすると「pong!」という文字列だけのページが表示される。
```
npx ts-node-dev ./src/app.ts
```

## 参考
- wclr/ts-node-dev: Compiles your TS app and restarts when files are modified.  
  https://github.com/wclr/ts-node-dev
