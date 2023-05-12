---
layout: ../../../layouts/MarkdownPostLayout.astro
title: '【Node.js】ExpressでWeb APIを作成する'
pubDate: 2023-05-12
description: 'Node.jsのWebアプリケーションフレームワーク「Express」を使用して、http://localhost:3000/pingというURLにGETリクエストを送信すると、レスポンスとして「pong」という文字列を返すWeb APIを作成します。TypeScriptの使用を前提としています。Node.js用のTypeScript実行エンジン「ts-node」での実行を想定しています。'
author: '玖堂いのは'
tags: ["Express", "Node.js", "TypeScript"]
---

# 【Node.js】ExpressでWeb APIを作成する
Node.jsのWebアプリケーションフレームワーク「Express」を使用して、  
http://localhost:3000/ping というURLにGETリクエストを送信すると、  
レスポンスとして「pong」という文字列を返すWeb APIを作成します。  
TypeScriptの使用を前提としています。  
Node.js用のTypeScript実行エンジン「ts-node」での実行を想定しています。

## 手順
以下のコマンドを実行して、必要なパッケージをインストールする。
```
npm install express
npm install -D @types/express
```

./srcにapp.tsというファイルを作成し、以下のように編集する。
```
import express from 'express';

const app = express();
const port = 3000;

app.get('/ping', (req: express.Request, res: express.Response) => {
  res.send('pong');
});

app.listen(port, () => {
  console.log(`Server listening on port ${port}`);
});
```

以下のコマンドを実行すると、コンソールに「Server listening on port 3000」と出力され、  
Webブラウザで http://localhost:3000/ping にアクセスすると「pong」という文字列だけのページが表示される。
```
npx ts-node ./src/app.ts
```

## 参考
- Express の「Hello World」の例  
  https://expressjs.com/ja/starter/hello-world.html
