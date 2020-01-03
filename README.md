# slides-templateの概要

`marp-cli`を利用して、markdownで書かれたスライドをウェブに後悔するためのテンプレートです。

> 参照：https://github.com/marp-team/marp-cli

デプロイ先にはfirebaseの利用しており、それを前提としたscriptが書かれています。

もし別の環境にデプロイする場合は、適宜変更してください。

# 使い方

## markdownの編集

- `./base`ディレクトリ内に配置されたmarkdownファイルを基にスライドを表示するhtmlを`./published`配下に生成します。
- そのため、編集は基本的に`./base`配下に編集したmarkdownファイルを配置してください。
- 記法はmarpに則ってください。

## デプロイの仕方

`package.json`のscriptに用意していますが、適宜変更してください。

### node_modulesの取得

```
yarn install
```

### firebaseの初期化

firebaseにデプロイする場合は、ご自身のプロジェクトと紐付けてください。

```
firebase init
```

### firebase hostingへのデプロイ

scriptは色々用意していますが、以下だけ実行すればビルドとデプロイの両者が実行されます。

```
yarn deploy
```

この際行われる処理は以下の通りです

- markdownをhtmlへ変換
- markdownをjpgに変換（1枚目のみ、OGP用）
- published配下にコピー



