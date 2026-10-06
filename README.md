# 魔女の脳ホームページ

個人サークル「魔女の脳」の公式サイト。Hugo（テーマなし・自前レイアウト）で構築し、
GitHub Actions 経由で GitHub Pages に公開している。

## 書き方

記事は `content/` に Markdown ファイルを置くだけで増える。

| 置き場所 | 表示される名前 | URL |
|---|---|---|
| `content/○○.md` | そのまま | `/○○/` |
| `content/site/○○.md` | `魔女の脳：○○` | `/site/○○/` |
| `content/special/○○.md` | `特別：○○` | `/special/○○/` |
| `content/category/○○/_index.md` | `カテゴリ：○○` | `/category/○○/` |

本文中のリンクは `[表示名](/リンク先/)` と書く。
リンク先の記事が存在すれば青、存在しなければ赤で表示される。

使える部品（shortcode）は `layouts/shortcodes/` を参照。
それぞれのファイルの先頭に書き方が書いてある。

- `infobox` … 右上の基礎情報ボックス
- `thumb` … 枠付きの画像
- `stub` … 「書きかけ」表示
- `hatnote` … 冒頭の注意書き

## 手元で確認する

```
hugo server
```

http://localhost:1313/ で確認できる。ファイルを保存すると自動で反映される。

## 公開

`master` に push すると GitHub Actions が自動でビルドして公開する。

## 色やフォントを変える

`static/css/main.css` の冒頭にある変数を書き換える。

## 注意

- Hugo のバージョンは `.github/workflows/hugo.yml` で固定している。
  `latest` に戻すと Hugo の更新で突然ビルドが壊れる。
- `public/` はビルド成果物なので Git では管理しない。
