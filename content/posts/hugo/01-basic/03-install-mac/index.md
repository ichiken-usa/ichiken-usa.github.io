---
title: "HugoをMacにインストールする手順"
date: 2025-05-04T18:10:00+09:00
description: HugoをMacにインストールする手順をわかりやすくまとめてみます。初心者でも迷わず進められるはずなので、ぜひ試してみてください。
menu:
  sidebar:
    name: Macインストール
    identifier: hugo-install-mac
    parent: hugo-basic
    weight: 30
hero: images/hugo.png
tags:
- Hugo
- Blog
categories:
- Development
draft: false
---

こんにちは。[フリーランスエンジニアの市原<i class="fas fa-link"></i>](/#about)です。  

HugoとGoとNode.jsをMacにインストールする手順を記載します。  
本題前にコマンドを書いておきます。

```bash
brew install hugo go node
```

以上です。

ちなみにこのサイトは Hugo + toha + GitHub Pages + XSever Domainにより**初年度1円**で公開されています。

## やってみたこと

- Homebrewを使ったソフトウェアのインストール(まだなら)
- ターミナルでHugoをインストールするコマンド
- Hugoのインストール確認方法

## 手順

[Hugo公式インストールガイド <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://gohugo.io/installation/macos/)

### 1. Homebrewをインストール

すでにインストール済みの場合はこのステップをスキップしてOKです。  
MacにHomebrewが入っていない場合は、Macで絶対に外せないパッケージ管理[Homebrewの公式サイト<i class="fa-solid fa-arrow-up-right-from-square"></i>](https://brew.sh/)にアクセスします。  
表示されているインストールコマンドをコピーして、ターミナルに貼り付けて実行します。

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

これでHomebrewがインストールされます。

### 2. Hugoをインストール

Homebrewが使えるようになったら、以下のコマンドをターミナルで実行してHugoをインストールします。  
ついでなのでテーマをローカルで確認するのにGoとNode.jsが必要になるのでついでに入れておきましょう。

```bash
brew install hugo go node
```

以上！

なお拡張版というのがあり、テーマによってはこちらが必要になるケースがあるようです。
試しに入れてみましたが、どちらにせよコマンド一発です。

```bash
CGO_ENABLED=1 go install -tags extended github.com/gohugoio/hugo@latest
```

### 3. インストールを確認

Hugoがちゃんとインストールされたか確認するには、以下のコマンドを実行します。

```bash
hugo version
```

このコマンドを実行してHugoのバージョン情報が表示されればOKです。  
ちなみに、`which hugo`コマンドを使うとHugoのインストール場所も確認できます。

GoとNode.jsの確認もしておきましょう。

   ```bash
   go version
   ```

Goのバージョン情報が表示されればインストール成功。

  ```bash
   node -v
   npm -v
  ```

  - `node -v`でNode.jsのバージョンが表示されれば成功。
  - `npm -v`でnpm（Node.jsのパッケージマネージャー）のバージョンが表示されれば成功。

## まとめ

- **Homebrewは便利**: Macでソフトウェアをインストールするならこれ一択。
- **Hugoの確認コマンド**： `hugo version`
- **Goの確認コマンド**: `go version`
- **Node.jsの確認コマンド**: `node -v`
- **npmの確認コマンド**: `npm -v`

これでMacにHugoをインストールできました。  
次はHugoを使って実際に静的サイトを作ってみましょう。Hugoの高速さと使いやすさをぜひ体験してみてください！

## 関連リンク

- [Homebrew公式サイト <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://brew.sh/)
- [Hugo公式インストールガイド <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://gohugo.io/installation/macos/)