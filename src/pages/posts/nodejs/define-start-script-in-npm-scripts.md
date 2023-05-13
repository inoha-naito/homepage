---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】npm-scriptsにstartスクリプトを定義する'
pubDate: 2023-05-13
description: 'npm-scriptsにstartスクリプトを定義して、「npm run start」というコマンドを実行できるようにする。'
author: '玖堂いのは'
tags: ["Node.js", "TypeScript"]
---

# 【Node.js】npm-scriptsにstartスクリプトを定義する
npm-scriptsにstartスクリプトを定義して、「npm run start」というコマンドを実行できるようにする。

本記事は下記の内容を踏襲しています。  
[【Node.js】ExpressでWeb APIを作成する](../hello-express)

## 手順
以下のコマンドを実行して、必要なパッケージをインストールする。
```
npm install -D ts-node
```

package.jsonを以下のように編集する。
```
{
  ...
  "scripts": {
    "start": "ts-node ./src/app.ts"
  },
  ...
}
```

以下のコマンドを実行すると、コンソールに「Server listening on port 3000」と出力され、  
Webブラウザで http://localhost:3000/ping にアクセスすると「pong」という文字列だけのページが表示される。
```
npm run start
```

依存関係にないファイル(型定義ファイルなど)を読み込む場合は、--filesオプションを追加する。
```
{
  ...
  "scripts": {
    "start": "ts-node --files ./src/app.ts"
  },
  ...
}
```

## 参考
- scripts | npm Docs  
  https://docs.npmjs.com/cli/v9/using-npm/scripts
