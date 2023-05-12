---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】TypeScriptのコードをコンパイルせずに実行する'
pubDate: 2023-05-12
description: 'Node.js用のTypeScript実行エンジン「ts-node」を使用して、TypeScriptのコードをコンパイルせずに実行します。'
author: '玖堂いのは'
tags: ["Node.js", "TypeScript"]
---

# 【Node.js】TypeScriptのコードをコンパイルせずに実行する
Node.js用のTypeScript実行エンジン「ts-node」を使用して、  
TypeScriptのコードをコンパイルせずに実行します。

## 手順
以下のコマンドを実行して、必要なパッケージをインストールする。
```
npm install -D ts-node
```

hello.tsというファイルを作成し、以下のように編集する。
```
const message: string = 'Hello, world!';
console.log(message);
```

上記の内容は、以下のコマンドでも可能。
```
( echo "const message: string = 'Hello, world!';"
  echo "console.log(message);" ) > hello.ts
```

以下のコマンドを実行すると、コンソールに「Hello, world!」が出力される。
```
npx ts-node hello.ts
```

## 参考
- ts-node | ts-node  
  https://typestrong.org/ts-node/
