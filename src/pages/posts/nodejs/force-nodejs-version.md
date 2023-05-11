---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】Node.jsのバージョンを強制する'
pubDate: 2023-05-11
description: 'プロジェクト内で使用するNode.jsのバージョンを強制します。'
author: '玖堂いのは'
tags: ["Node.js"]
---

# 【Node.js】Node.jsのバージョンを強制する
プロジェクト内で使用するNode.jsのバージョンを強制します。

## 手順
package.jsonを以下のように編集する。
```
{
  ...
  "engines": {
    "node": "16.20.0"
  },
  ...
}
```

プロジェクトのルートディレクトリに.npmrcというファイルを作成し、  
以下のように編集する。
```
engine-strict=true
```

上記の内容は、以下のコマンドでも可能。
```
echo "engine-strict=true" > .npmrc
```

## 参考
- Force correct Node.js version with npm | by Fabian Illner | Medium  
  https://medium.com/@fabian.illner/force-correct-node-js-version-with-npm-a2a57fd12fa
- package.json | npm Docs  
  https://docs.npmjs.com/cli/v9/configuring-npm/package-json#engines
- config | npm Docs  
  https://docs.npmjs.com/cli/v9/using-npm/config#engine-strict
