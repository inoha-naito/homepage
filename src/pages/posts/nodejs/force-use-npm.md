---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】npmの使用を強制する'
pubDate: 2023-05-11
description: 'プロジェクト内で使用するNode.jsのパッケージ管理ツールをnpmに強制します。'
author: '玖堂いのは'
tags: ["Node.js"]
---

# 【Node.js】npmの使用を強制する
プロジェクト内で使用するNode.jsのパッケージ管理ツールをnpmに強制します。

## 手順
package.jsonを以下のように編集する。
```
{
  ...
  "engines": {
    "npm": ">=8.19.4",
    "yarn": "please-use-npm",
    "pnpm": "please-use-npm"
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
- How To Force Use Yarn Or NPM - Neutron Dev  
  https://neutrondev.com/force-use-yarn-or-npm/
- package.json | npm Docs  
  https://docs.npmjs.com/cli/v9/configuring-npm/package-json#engines
- config | npm Docs  
  https://docs.npmjs.com/cli/v9/using-npm/config#engine-strict
