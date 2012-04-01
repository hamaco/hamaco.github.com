---
layout: post
title: "GitHub PagesでOctopress使ってみる"
date: 2012-03-23 00:46
comments: true
categories: github octopress
---

Markdownでメモ書きたかったので以前1回やったOctopressをまたセットアップしてみた。
前やった時のメモとか公式とか見ながら再度セットアップしたのでMarkdownの練習兼ねてメモ。

## Github Pages用のリポジトリ作成

[GitHub](https://github.com/repositories/new)で hamaco.github.com という名前でリポジトリを作成する。

## Octopressのダウンロード

ダウンロードというかgitでcloneしてくる。

    git clone https://github.com/imathis/octopress.git

bundlerとかいうやつで必要なgemとかインストールして初期処理を行う。

    cd octopress
    gem install bundler
    bundle install
    rake install

## Octopressの設定

### 初期設定

下記コマンドを実行するとgithubのリポジトリを聞かれるので最初に作成したGithub PageのリポジトリURLを指定する。

    rake setup_github_pages

    git@github.com:hamaco/hamaco.github.com.git

その後、下記コマンドを実行してしばらく(10分弱)待つと見れるようになる。

    rake generate
    rake deploy

### Blogの設定

設定ファイルを弄ってタイトルとかをちゃんとしたのにする。

    gvim _config.yml

## 記事の作成

記事を作成するのにはrakeを実行して、内容を書いてやる。

    rake new_post\["title name"\]
    gvim source/_posts/2012-03-23-title-name.markdown

## ソースの管理

なんかプロジェクトページとユーザページを統合しとくと面倒とか書いてあるブログがあったりしたので丁度アカウントも持ってたしBitbucketでソースを管理するようにしてみる。  
と言ってもBitbucketでリポジトリを作成してpushしてあげるだけ。  
Bitbucketでのリポジトリ作成はGitHubとたいして変わらないので割愛。分からなければ参考サイト見て下さい。

    git remote add bitbucket git@bitbucket.org:hamaco/octopress-github.git
    git push -u bitbucket source

## 参考サイト

- [Octopress Setup - Octopress](http://octopress.org/docs/setup/)
- [Big Sky :: githubとjekyllとoctopressで作る簡単でモダンなブログ](http://mattn.kaoriya.net/software/lang/ruby/20111017205717.htm)
- [GithubとOctopressでモダンな技術系ブログを作ってみる | Glide Note - グライドノート](http://www.glidenote.com/archives/1517)
- [Octopressのインストールから運用管理まで - T.I.D.](http://tokkonopapa.github.com/blog/2011/12/30/octopress-on-github-and-bitbucket/)

*追記予定*
source側の管理とかやったらその辺追記したりする予定
