# カスタマイズメモ

## ローカル化

[https://toha-guides.netlify.app/posts/](https://toha-guides.netlify.app/posts/)

- `Quickstart`で確認。すんなりOK。
- GitHub Pagesの設定をDeploy from a branchに変更。カスタムドメイン用に自動でCNAMEを作成するように追加。
- 色を編集したいのでvariables.scssをhugo-tohaからコピーして編集。

## ホームカスタマイズ

- レイアウト調整
  - [https://toha-guides.netlify.app/posts/customizing/customize-layout/](https://toha-guides.netlify.app/posts/customizing/customize-layout/)
  - layoutフォルダをコピー
  - variables.scssで文字間等を調整
  - Experienceの表示が気になるので修正　layouts/partials/sections/experiences/positions.html
    - 縦一直線化
    - タイトルとResponsibilitiesの間が狭いのでCSSで調整
    - 在籍期間を改行
    - 会社間の隙間をbootstrapで調整
    - ポジション間に水平線追加
  - Aboutの自己紹介文を左揃えに修正
  - Aboutに見出し追加
  - Experienceの年月がサファリだと電話番号と認識されるため、Month yyyyに変更

## ブログ

- posts構造を整理。全部Sampleにまとめ。

構成案

1. Hugoの基本
  01.md: Hugo入門: 静的サイトジェネレーターの魅力
  02.md: Hugo インストール手順（Windows向け）
  03.md: Hugo インストール手順（Macintosh向け）
  04.md: Hugo サイト作成手順とフォルダ構成の概要
2. コンテンツ管理
  05.md: Hugo テーマの導入と設定方法
  06.md: Hugo のコンテンツ管理とカスタムリストページの作成
  07.md: Hugo のフロントマターの概要と活用方法
  08.md: Hugo のアーキタイプの概要と活用方法
3. テンプレートとレイアウト
  09.md: Hugo テンプレートの基本
  10.md: タクソノミーの活用方法
  11.md: テンプレートの基本と活用方法
  12.md: リストテンプレートの活用方法
  13.md: シングルテンプレートの活用方法
  14.md: ホームページテンプレートの作成と活用方法
  15.md: セクションテンプレートの活用方法
  16.md: Baseテンプレートとブロックの活用方法
4. 高度な機能
  17.md: 変数の基本と活用方法
  18.md: 条件ロジックの活用方法
  19.md: 条件分岐の基本と活用方法
  20.md: データフォルダの活用方法
  21.md: パーシャルテンプレートの活用方法
  22.md: ショートコードテンプレートの活用方法
5. デプロイと最適化
  23.md: サイトのビルドとホスティング方法
