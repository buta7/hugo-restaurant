# README

## セットアップ

サイト作成

```shell
hugo new site hugo-restaurant
```

レポジトリ初期化

```shell
cd hugo-restaurant
git init
echo '*.bak' >> .gitignore
echo '*~' >> .gitignore
echo '*.orig' >> .gitignore
echo 'public' >> .gitignore
```

テーマ設定

```shell
cd themes 
git submodule add git@github.com:themefisher/restaurant-hugo.git
```

サイト設定

```shell
cd hugo-restaurant
cp -pr ./themes/restaurant-hugo/exampleSite/* .
```

config.toml

```toml
baseURL = "https://higebobo.github.io/hugo-restaurant/"
languageCode = "ja"
title = "Hugo Restaurant"
theme = "restaurant-hugo"
publishDir = "docs"
```

> github pagesやnetlifyで使う場合はbaseURLのプロトコルはhttpsにすること

Githubレポジトリ作成後

```shell
git remote add origin git@github.com:higebobo/hugo-restaurant.git
cp somplace/{Makefile,deploy.sh} .
make deploy
```

Github>Settings>Gighub Pages>Source>master branch/docs folder

## 既存のレポジトリからクローンする場合

```shell
git clone git@github.com:higebobo/hugo-restaurant.git higebobo-restaurant
cd higebobo-restaurant
git submodule update --init --recursive
```

## 使い方

### 投稿

新規ポートフォリオ

```shell
hugo new blog/hello.md
content/blog/hello.md created
```

編集

```shell
vi content/blog/hello.md
```

## Github連携

config.tomlに以下の設定があることを確認

```toml
baseURL = "https://higebobo.github.com/hugo-restaurant/"
publishDir = "docs"
```

公開(githubにプッシュ)

```shell
make deploy
```

## Link

* [Restaurant Hugo \| Hugo Themes](https://themes.gohugo.io/restaurant-hugo/)
