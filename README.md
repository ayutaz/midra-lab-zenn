# midra-lab-zenn

MiraLab用のZennの記事作成ドキュメント

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [使い方](#%E4%BD%BF%E3%81%84%E6%96%B9)
  - [準備](#%E6%BA%96%E5%82%99)
  - [新規記事の作成](#%E6%96%B0%E8%A6%8F%E8%A8%98%E4%BA%8B%E3%81%AE%E4%BD%9C%E6%88%90)
  - [記事のPreview](#%E8%A8%98%E4%BA%8B%E3%81%AEpreview)
  - [記事の公開](#%E8%A8%98%E4%BA%8B%E3%81%AE%E5%85%AC%E9%96%8B)
  - [記事の削除](#%E8%A8%98%E4%BA%8B%E3%81%AE%E5%89%8A%E9%99%A4)
- [参考サイト](#%E5%8F%82%E8%80%83%E3%82%B5%E3%82%A4%E3%83%88)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 使い方

## 準備

1. [Docker](https://www.docker.com/)のインストール
2. [Zenn](https://zenn.dev/)のアカウントを作成する
3. 以下の画像のようにZennの[GitHub連携](https://zenn.dev/dashboard/deploys?tab=repo_settings)
   にて[midra-lab-zenn](https://github.com/MidraLab/midra-lab-zenn)との連携及びデプロイ対象ブランチを `main` に設定する

![](docs/images/zennとgithubの連携と設定.png)

## 新規記事の作成

1. ターミナル上で `docker compose up -d --build` を実行
2. 記事を作成する用のブランチを新しく作成する(ブランチ名はなんでもOK)
3. ターミナル上で `docker exec midra-lab-zenn zenn new:article --publication-name midra_lab bash` を実行する
4. `articles`内に新しく生成されたファイルに記事を書いていく
5. 画像は`images`フォルダにその記事の名前のフォルダを作成して入れる。

## 記事のPreview

1. ブラウザで http://localhost:8000/ にアクセスをする
2. 任意のページをクリックして、記事を確認する

## 記事の公開

1. 記事の作成が完了したら、`published:` を trueに変更する
2. リモートブランチにpushする
3. `main` branchにPRを出す
4. 校正チェックが自動でされるので、PRにあるコメントを修正する
5. テストが通ったら自動で公開される

## 記事の削除

安全のため、コンテンツの削除は[ダッシュボードの投稿管理](https://zenn.dev/dashboard)からのみ行うことができます。

![](docs/images/delete-zenn-article.png)

# 参考サイト

* [Zenn CLIで記事・本を管理する方法](https://zenn.dev/zenn/articles/zenn-cli-guide)
