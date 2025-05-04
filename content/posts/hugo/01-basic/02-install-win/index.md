---
title: "HugoをWindowsにインストールする手順"
date: 2025-05-04T17:00:33+09:00
description: HugoをWindowsにインストールする手順をわかりやすくまとめてみます。初心者でも迷わず進められるはずなので、ぜひ試してみてください。
menu:
  sidebar:
    name: Winインストール
    identifier: hugo-install-win
    parent: hugo-basic
    weight: 10
hero: images/hugo.png
tags:
- Hugo
- Blog
categories:
- Development
draft: false
---


こんにちは。[フリーランスエンジニアの市原<i class="fas fa-link"></i>](/#about)です。  

HugoをWindowsにインストールするのはめちゃくちゃ簡単でしたが、公式はあっさりしているし、いくつか手段があって結局どれやねん！てなるかもしれません。  
ここでは、実際にやってみた手順をざっくりまとめてみます。初心者でも迷わず進められるはずなので、ぜひ試してみてください。  
これからHugoを使ってみたい人の参考になれば幸いです。

ちなみにこのサイトは Hugo + toha + GitHub Pages + XSever Domainにより**初年度1円**で公開されています。

## やってみたこと

- Windowsにビルド済みバイナリのHugoをインストールする方法
- Hugo用のフォルダを作る
- GitHubからHugoの実行ファイルをダウンロード
- ファイルを解凍して配置
- コマンドラインでHugoを動かす
- PATH環境変数を設定して、どこからでもHugoを使えるようにする

## 手順

[公式サイト<i class="fa-solid fa-arrow-up-right-from-square"></i>](https://gohugo.io/installation/windows/)

執筆時： v0.147.1

ビルド済みのexeを置いてパスを通すだけです。

### 1. フォルダを作る

まず、Cドライブに「Hugo」というフォルダを作りました。  
その中に「bin」というフォルダも作成。  
この「bin」フォルダにHugoの実行ファイルを入れ流予定です。

### 2. Hugoをダウンロード

次に、[HugoのGitHubリリースページ](https://github.com/gohugoio/hugo/releases)にアクセス。  
自分のWindowsに合ったバージョンをダウンロードします。  
だいたいwindows-amd64です。

### 3. ファイルを解凍して配置

ダウンロードしたZIPファイルを解凍。  
「hugo.exe」を「bin」に移動します。

### 4. コマンドラインでHugoを動かしてみる

コマンドプロンプトを開いて、作成した「Hugo/bin」フォルダに移動して以下を実行。

```bash
cd C:\Hugo\bin
hugo version
```

これでHugoのバージョン情報が表示されれば、一旦動作確認はOKです。

### 5. PATH環境変数を設定

どのフォルダからでもHugoを使えるようにするために、PATH環境変数を設定します。

1. **「システム環境変数の編集」**を開く（Windowsの検索バーで「環境変数」と入力すると出てきます）。
2. 「システム環境変数」の「Path」を選択して編集をクリック。
3. 「新規」をクリックして、「C:\Hugo\bin」を追加。
4. 保存してウィンドウを閉じます。

### 6. 設定を確認

コマンドプロンプトを再起動して、フォルダ移動せずに以下を実行。

```bash
hugo version
```

どのフォルダからでもHugoのバージョン情報が表示されれば、設定完了👌

## まとめ

- **環境変数の設定は必須**： PATHに追加すれば、どこからでもHugoを使えるようになる。
- **確認は`hugo version`**： 使えるか一発でわかる。

これでWindowsにHugoをインストールできました。  
次はHugoを使って実際に静的サイトを作ってみましょう。Hugoの高速さと使いやすさをぜひ体験してみてください！

## 関連リンク

[https://gohugo.io/installation/windows/](https://gohugo.io/installation/windows/)
