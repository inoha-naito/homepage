---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】Node.jsでHello, world!'
pubDate: 2023-05-10
description: 'Node.jsプロジェクトを作成し、コンソールに「Hello, world!」を出力します。'
author: '玖堂いのは'
tags: ["Node.js"]
---

# 【Node.js】Node.jsでHello, world!
Node.jsプロジェクトを作成し、コンソールに「Hello, world!」を出力します。

## 手順
以下のコマンドを実行して、sampleというディレクトリを作成し、そのディレクトリに移動する。
```
mkdir sample && cd sample
```

以下のコマンドを実行して、Node.jsプロジェクトを初期化する。  
package.jsonというファイルが作成される。
```
npm init -y
```

hello.jsというファイルを作成し、以下のように編集する。
```
console.log('Hello, world!');
```

上記の内容は、以下のコマンドでも可能。
```
echo "console.log('Hello, world!');" > hello.js
```

以下のコマンドを実行すると、コンソールに「Hello, world!」が出力される。
```
node hello.js
```

## 参考
- npm-init | npm Docs  
  https://docs.npmjs.com/cli/v8/commands/npm-init
