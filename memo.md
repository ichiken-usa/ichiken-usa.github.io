# レジュメブログ公開メモ

## テーマ

[https://github.com/HugoBlox/theme-academic-cv](https://github.com/HugoBlox/theme-academic-cv)

- フォークしてそのまま使用。
- ローカルでhugo server等でチェックしようとすると色々エラーが出るが、Githubでビルドすればいきなり公開可能。

## 関連情報まとめ

どうやらこれが使われている模様。
[https://heroicons.com](https://heroicons.com)

アイコンはこのサイトで判明
[https://okawayusuke.com/blog/2024/hugo-markdown/](https://okawayusuke.com/blog/2024/hugo-markdown/)

## HPのベースを完成させる

- bio関連
- ナビゲーション
- ブログページ関連
- タグページ

### bio関連情報変更

とりあえず構造がわからなくても変更できるauthorから変更。

- content/authors/admin/_index.md
  - 情報を修正
  - 新しく枠を追加するのがわからないのでタイトル修正してアワードと資格両方を記入
  - Languagesのパーセントのグラフが逆で修正方法がわからないのでいったん英語を50％に。
  - certificate_url: https://www.credly.com/badges/4bd00f45-afdb-4ebe-9480-b19c38d1b9c6　で勝手にSee certificateというリンクを作ってくれる

### ナビゲーション修正

- config/_default/menus.yaml
  - bioをHomeに変更
  - 不要な項目を削除
  - weightを変更して順番調整
- content/project.mdを削除
- postフォルダをblogに変更してmenus.yamlもblogに変更

最終的にはこれだけにした

```yaml
main:
  - name: Home
    url: /
    weight: 10
  - name: Blog
    url: blog/
    weight: 20
  - name: Tag
    url: tags/
    weight: 21
  - name: Experience
    url: experience/
    weight: 30
```

### ブログページ

そのままだとまとめのページがないのでteachingを流用
postをblogに変更

### 細々

- config/_default/hugo.yamlのWebsite name変更

```yaml
# Website name
title: Nexa Engineering
```

