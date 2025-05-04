---
title: "HugoをWindowsにインストールする手順"
date: 2025-05-04T17:00:33+09:00
description: HugoをWindowsにインストールする手順をわかりやすくまとめてみます。初心者でも迷わず進められるはずなので、ぜひ試してみてください。
menu:
  sidebar:
    name: Winインストール
    identifier: hugo-install-win
    parent: hugo-basic
    weight: 20
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

- Windowsにビルド済みバイナリのHugoを配置
- PATH環境変数を設定して、どこからでもHugoを使えるようにする
- のちのち必要になるGoとNode.jsも入れる

## Hugoインストール手順

[Hugo公式インストールガイド <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://gohugo.io/installation/windows/)

インストーラではなく、ビルド済みのexeを置いてパスを通すスタイルです。  
公式手順より詳細に記載しておきます。

### 1. フォルダを作る

まず、Cドライブに「Hugo」というフォルダを作成。  
その中に「bin」というフォルダも作成。  
この「bin」フォルダにHugoの実行ファイルを入れ流予定です。

`C:\Hugo\bin\`

### 2. Hugoをダウンロード

次に、[HugoのGitHubリリースページ](https://github.com/gohugoio/hugo/releases)にアクセス。  
自分のWindowsに合ったバージョンをダウンロードします。  
だいたいwindows-amd64です。  
私みたいにMシリーズのMacの仮想環境でWindowsを使ったりするとarmだったりします。

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

1. 「システム環境変数の編集」を開く（Windowsの検索バーで「環境変数」と入力すると出る）。
2. 「システム環境変数」の「Path」を選択して編集をクリック。
3. 「新規」をクリックして、「C:\Hugo\bin」を追加。
4. 「保存」して完了。

### 6. 設定を確認

コマンドプロンプトを再起動して、フォルダ移動せずに以下を実行。

```bash
hugo version
```

どのフォルダからでもHugoのバージョン情報が表示されれば、設定完了👌

以下のように、現在のブログ構成にGoとNode.jsのインストール手順を追加しました。Hugoの手順と同じトーンで記載しています。

## GoとNode.jsのインストール手順

Hugoを使う際に、テーマのローカル確認やビルドでGoとNode.jsが必要になる場合があります。  
ついでなので、WindowsにGoとNode.jsをインストールしてしまいましょう。どちらもインストーラでポチポチで終わりです。

### 1. Goをインストール

まず、Goをインストールします。

1. **Go公式サイトにアクセス**  
   [Go公式ダウンロードページ  <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://go.dev/dl/)にアクセスします。

2. **Windows用インストーラーをダウンロード**  
   自分のWindows環境（通常は`windows-amd64.msi`）に合った最新版インストーラーを選択してダウンロードします。

3. **インストーラーを実行**  
   ダウンロードしたインストーラーをダブルクリックして実行します。  
   セットアップウィザードに従い、インストールを完了させます（デフォルト設定でOK）。

4. **インストール確認**  
   コマンドプロンプトを開いて以下を実行します。

   ```bash
   go version
   ```

   Goのバージョン情報が表示されればインストール成功です。

### 2. Node.jsをインストール

次に、Node.jsをインストールします。

1. **Node.js公式サイトにアクセス**  
   [Node.js公式ダウンロードページ  <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://nodejs.org/)にアクセスします。

2. **LTS版をダウンロード**  
   安定版（LTS: Long Term Support）を選択してダウンロードします。

3. **インストーラーを実行**  
   ダウンロードしたインストーラーをダブルクリックして実行します。  
   セットアップウィザードに従い、インストールを完了させます（デフォルト設定でOK）。

4. **インストール確認**  
   コマンドプロンプトを開いて以下を実行します。

   ```bash
   node -v
   npm -v
   ```

   - `node -v`でNode.jsのバージョンが表示されれば成功。
   - `npm -v`でnpm（Node.jsのパッケージマネージャー）のバージョンが表示されれば成功。

これでGoとNode.jsのインストールが完了！  

## まとめ

- **環境変数の設定は必須**： PATHに追加すれば、どこからでもHugoを使えるようになる。
- **Hugoの確認コマンド**： `hugo version`
- **Goの確認コマンド**: `go version`
- **Node.jsの確認コマンド**: `node -v`
- **npmの確認コマンド**: `npm -v`

これでWindowsにHugo、Go、Node.jsをインストールできました。  
次はHugoを使って実際に静的サイトを作ってみましょう。Hugoの高速さと使いやすさをぜひ体験してみてください！

## 関連リンク

[Hugo公式インストールガイド <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://gohugo.io/installation/windows/)
[Go公式サイト <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://go.dev)
