---
layout: post
title: Octopressのテーマを変更してみた
date: 2012-04-02 00:58
comments: true
categories: octopress
---
Octopressのテーマがデフォルトだとつまんないなーとか思ったので変更してみた。  
しかし今の所そんなにテーマが豊富じゃないようなのでそんなに選択肢は多くないっぽい。

## テーマのインストール

[List Of Octopress Themes](https://github.com/imathis/octopress/wiki/List-Of-Octopress-Themes)にOctopress用のテーマがリストアップされています。
今回は検索してて一番最初に見つけたSlashというテーマを入れてみます。  
インストール方法も上記Wikiに書いてある通りコマンドを3つほど実行するだけで簡単にインストールできます。

    git clone git://github.com/tommy351/Octopress-Theme-Slash.git .themes/slash
    rake install['slash']

## テーマ確認
インストールが完了したらプレビューで確認してみましょう。  
サーバが立ち上がったあと http://127.0.0.1:4000/ とかで確認できるはずです。

    rake preview

## テーマ反映

プレビューしてみて良い感じであればそのままgenerateして本番環境に反映させます。

    rake gen_deploy

GitHub Pagesで運用している場合暫く待つとGitHubからメールが飛んできてテーマが変わるはず。
