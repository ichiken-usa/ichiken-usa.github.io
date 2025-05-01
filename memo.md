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
  - アバター置き換え
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
- 追加とか削除はブラウザのキャッシュにより意図しない表示になる可能性があるので、あれ？と思ったら更新ボタン押すべし

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

### プライバシーポリシーページ追加

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
  - name: Privacy Policy
    url: privacy-policy/
    weight: 40
```

### カスタムドメイン

[GitHub Pages サイトのカスタムドメインを管理する](https://docs.github.com/ja/enterprise-cloud@latest/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain)

[【2024年版】GitHub Pagesで独自のカスタムドメインを設定する方法](https://qiita.com/sotanengel/items/034dd37cbc0dde9f7c86)

[xserverドメインをgithub pagesで使う](https://qiita.com/nanana_0777/items/4de3513b597b3983d456)

[Xserver Domain で取得したドメインを使って GitHub Pages で HTTPS に対応したサイトを公開する方法](https://y-ktzw.com/posts/custom-domain/)

ホスト名を空欄でAとAAAAを登録。
ホスト名にwwwを入れてCNAMEを登録。
1時間くらいしてから確認。→ githubのsettings→Pagesのカスタムドメインにwwwなしで入力。早すぎると失敗する。

iCloud+のサブスクに入っているとカスタムドメインのメールをサポートしているようなのでこれを使用。
最大5つのドメイン、それぞれ3つまでのメールアドレスを使えるらしい。
＠がサポートされていない、句読点エラーになる→末尾の手順に従い削除し登録はできた。15分後くらいに確認したらOKになった。
表示される手順に従うだけでできるあたりはさすがApple。
Facetimeもできるし完璧。

### GoogleアナリティクスとGoogle search console 

- アナリティクス
  - カスタムドメインとSSLをやってからが良い。
  - https://nexa-eng.com で登録してIDをパラメータへ入力。
- サーチコンソール
  - xserverに.nexa-eng.comの前の部分コピペ。TXT。コード
  - しばらく放置して再度サーチコンソールで確認。→ アクセス成功

## 流れ整理

1. GitHub Pagesでブログのベース作成
   1. 無料
   2. そのままGitHub上でフォークが最速
   3. 手元でHugoでやろうとするとエラーになり解消できず
   4. 公開できていることが確認できればOK。変更は後でも良い
   5. 構造がわからなくてもbioの文字を変更してアバター変えればそれっぽくなる
2. カスタムドメインとSSL設定
   1. 初年度1円
   2. Xserverが調べた限り最安
   3. ＠表記に対応していないのでAとAAAAはホストは空欄で設定。CNAMEはホストにwww。GitHubに書かれている通りでOK。
   4. SSLの無料のは隠れている。
   5. 15分くらいしたらGitHubのカスタムドメインを設定してHPPTSも設定。
3. カスタムドメインのメールアドレス取得
   1. iCloud+サブスク入っていたら追加料金無し
   2. 指示に従うと、DNS設定でエラーになり、最下部の通りにすれば行ける
   3. これも15分くらい待つ
   4. 確認完了したら好きなメールアドレス追加
4. Googleアナリティクスとサーチコンソール
   1. カスタムドメインでそれぞれ設定
   2. アナリティクスはIDを取得して埋め込む
   3. サーチコンソールはDNSに埋め込む。いつも通り設定後はしばらく置く。
   4. 一応テンプレにも埋め込む
5. GitHub Pagesを仕上げる
   1. 経歴
   2. カスタムドメインメールにする
   3. プライバシーポリシー追加
   4. お問い合わせ追加
   5. ナビゲーション整理