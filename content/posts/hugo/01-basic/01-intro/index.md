---
title: "Hugo入門：静的サイトジェネレータの魅力"
date: 2025-05-04T12:50:33+09:00
description: 最近、Hugoという静的サイトジェネレーターでホームページを構築したので、その魅力をざっくりまとめてみました。静的サイトって何？というところから、Hugoの特徴まで、初心者目線で整理してみます。
menu:
  sidebar:
    name: SSGの魅力
    identifier: hugo-intro
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

このページでは、Hugoという静的サイトジェネレーター（SSG）について初心者目線で情報を整理しています。  
これからHugoを使ってみたい人の参考になれば幸いです。

ちなみにこのサイトは Hugo + toha + GitHub Pages + XSever Domainにより**初年度1円**で公開されています。

## 静的サイトと動的サイトの違い

まず、静的サイトと動的サイトの違いを簡単に説明します。

### 静的サイトとは？

静的サイトは、HTMLファイルをそのままサーバーに置いて配信するシンプルな仕組みです。  
例えば、個人ブログやポートフォリオサイトなんかに向いています。

- **メリット**: 高速、セキュア、ホスティングが安い
- **デメリット**: 動的な機能（ログインやコメント機能など）が難しい

### 動的サイトとは？

一方、動的サイトは、ユーザーごとに異なるコンテンツを生成する仕組みです。  
例えば、FacebookやAmazonのようなサイトがこれに当たります。

- **メリット**: 柔軟でカスタマイズ性が高い
- **デメリット**: サーバーリソースが必要で、管理が複雑

ログインで人によってコンテンツを変えたいとかなら別ですが、普通の個人ブログなら静的サイトで十分だと思います。
Hugoだと問い合わせフォームからメールを送るのが難しかったりしますが、これはGoogle Formsを埋め込んだりで代用できます。

## Hugoの特徴

Hugoは静的サイトジェネレーターの中でも人気のあるツールの一つです。  
以下の点が魅力的だと感じました。

- **超高速**: Go言語で作られていて、ビルドがめちゃくちゃ速く自称世界最速。お作法に従ったファイル配置にすれば構造を勝手に解析してページやタグやリンクを作ってくれて超ラク。
- **Markdown対応**: 記事はマークダウンで書けるので、普段資料等をマークダウンで作っている私にピッタリ。ローカルHugoサーバを立ち上げれば、書きながらホットリロードで即確認できます。
- **無料でオープンソース**: 豊富なテーマが揃っていて、カスタマイズもお作法さえわかれば結構簡単。
- **柔軟性**: テンプレートやレイアウトの自由度が高い。

## 他のCMSとの比較

WordPressなどと比較して、Hugoには以下のようなメリットがあります。

- **パフォーマンス**: 静的サイトなので、ページの読み込みが速い。
- **セキュリティ**: データベースを使わないので、ハッキングリスクが低い。
- **コスト**: 無料で使える。GitHub Pagesとの組み合わせで0円運用可能。GitHub Pagesはカスタムドメインも対応可能。XServer Domainなら初年度1円でGoogleアドセンス可能。

## 他の選択肢まとめ

その他の静的サイトジェネレータの選択肢を(GPTさんが)整理しました。  
ざっくり上から人気順です。そもそもマークダウンで書いたろ！って人が少ないんでしょうね。。。

| 名前           | 特徴                                                                                                                                       | 公式サイト                              |
|:---------------|:-------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------|
| **Next.js**    | Reactベースのフレームワークで、静的サイトと動的サイトの両方を構築可能。SSRやSSGをサポートし、高度な機能が豊富。<br>**評価**: Reactエコシステムの中心的存在で、最新技術を活用可能。 | [https://nextjs.org/](https://nextjs.org/) |
| **Gatsby**     | Reactベースの静的サイトジェネレータで、GraphQLを使用して柔軟なデータ管理が可能。プラグインエコシステムが充実し、SEOに強い。<br>**評価**: Reactユーザーに支持され、SEOやパフォーマンスに特化。 | [https://www.gatsbyjs.com/](https://www.gatsbyjs.com/) |
| **Hugo**       | Go言語で構築された静的サイトジェネレータで、超高速なビルド速度を誇る。Markdown対応で簡単にコンテンツ作成が可能。<br>**評価**: 高速性と柔軟性が評価され、初心者から上級者まで幅広く支持されている。 | [https://gohugo.io/](https://gohugo.io/) |
| **Jekyll**     | Rubyで構築された静的サイトジェネレータ。GitHub Pagesと統合され無料ホスティング可能。プラグインやテーマが豊富でカスタマイズ性が高い。<br>**評価**: 長年の実績とGitHub Pagesとの親和性が高い。 | [https://jekyllrb.com/](https://jekyllrb.com/) |
| **Nuxt.js**    | Vue.jsベースのフレームワークで、SSGとSSRをサポート。プラグインやモジュールが豊富で柔軟な開発が可能。<br>**評価**: Vue.jsユーザーにとって最適な選択肢として支持されている。 | [https://nuxtjs.org/](https://nuxtjs.org/) |
| **Eleventy**   | JavaScriptで構築された軽量な静的サイトジェネレータで、シンプルで柔軟性が高く、高速。初心者にも扱いやすい。<br>**評価**: 軽量でシンプルな構成が好まれ、JavaScriptユーザーに人気。 | [https://www.11ty.dev/](https://www.11ty.dev/) |
| **Hexo**       | Node.jsベースの静的サイトジェネレータで、高速でMarkdownを使用して簡単にコンテンツ作成可能。ブログ向けに最適化。<br>**評価**: ブログ用途に特化し、Node.jsユーザーに支持されている。 | [https://hexo.io/](https://hexo.io/) |
| **Docusaurus** | Facebookが開発した静的サイトジェネレータで、ドキュメントサイトやブログの作成に特化。Reactベースでカスタマイズ性が高い。<br>**評価**: Facebook製で信頼性が高く、Reactユーザーに支持されている。 | [https://docusaurus.io/](https://docusaurus.io/) |
| **MkDocs**     | Pythonで構築され、ドキュメントサイトの作成に特化。Markdownを使用して簡単にドキュメント作成可能。<br>**評価**: 技術ドキュメント作成に特化し、Pythonユーザーに支持されている。 | [https://www.mkdocs.org/](https://www.mkdocs.org/) |
| **Zola**       | Rustで構築された静的サイトジェネレータで、シンプルで高速、設定が簡単。デフォルトで多言語対応をサポート。<br>**評価**: Rustユーザーに注目され、高速性が評価されている。 | [https://www.getzola.org/](https://www.getzola.org/) |
| **Pelican**    | Pythonで構築された静的サイトジェネレータで、MarkdownやreStructuredTextをサポート。シンプルでPythonユーザーに最適。<br>**評価**: Pythonユーザーに特化したツールとして利用されている。 | [https://getpelican.com](https://getpelican.com) |

マークダウン対応、テンプレートがあってカスタム可能、運用コストが低い、それなりの人気とコミュニティ継続、  
これらを満たすのがHugoでした。テーマ選びをミスらなければ、数分でテストページ公開できるし、ブログにも超使いやすいです。（紹介の多いテーマの後継HugoBlox/theme-academic-cvは構造がややこしすぎるし更新止まっているのでやめとけ）

## まとめ

Hugoは、静的サイトを効率的に作成するための強力なツールです。  
自分で個人ブログやポートフォリオサイトを作って見た限りではおすすめです。これからHugoを使ってみたい人の参考になれば幸いです！

とりあえずやってみようかなという人は、Hugoのインストールへ進んでください。

[HugoをWindowsへインストールする手順 <i class="fa-solid fa-link"></i>](/posts/hugo/01-basic/02-install-win)
[HugoをMacへインストールする手順 <i class="fa-solid fa-link"></i>](/posts/hugo/01-basic/03-install-mac)

## 関連リンク

[https://gohugo.io/about/introduction <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://gohugo.io/about/introduction)  
[https://github.com/hugo-toha/toha <i class="fa-solid fa-arrow-up-right-from-square"></i>](https://github.com/hugo-toha/toha)
