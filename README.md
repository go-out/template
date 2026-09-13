# Go Out組織のデジタル地図用SDKを用いて、ページを構築するテンプレート
新しい地域・国のサイトを作るときは、このリポジトリを **「Use this template」** で複製して使います。

## 使い方

1. このリポジトリを「Use this template」で複製する
2. 複製先リポジトリの Settings → Pages で GitHub Pages を有効化する（テンプレートの設定は引き継がれないため、複製のたびに必要）
3. `index.json`（mapページ）・`date.json`（dateページ）を、実際のサイト内容に書き換える
4. 必要に応じて Markdownファイルも、実際の紹介文に差し替える・増やす

反映まで数分かかることがあるので、複製直後に404が出ても焦らず少し待ってから確認してください。

## 構成

```
template/
├── date/
│   ├── index.html     dateページ（カレンダー・目次）
│   └── date.json     dateページ用データ（プレースホルダー）
├── index.html    mapページ（地図・写真ギャラリー）
└── index.json    mapページ用データ（プレースホルダー）
```

`index.html`・`date/index.html`はどちらも [go-out/sdk](https://go-out.github.io/sdk/) の共通フレームワーク（JS/CSS）を絶対URLで読み込んでいます。
ページ自体のロジック・見た目を変えたい場合は、このリポジトリではなくsdk側を修正してください。

## JSONの書き方

`index.json`・`date.json`はあくまでプレースホルダーです。
実際のデータを書く際は、sdkリポジトリの `templates/map.jsonc`・`templates/date.jsonc`（コメント付きの雛形）を参照してください。

## サイト作成時のチェックリスト

- [ ] `index.html`・`date.html`の`<title>`・`<meta name="description">`を実際の内容に合わせる（JS側で上書きされるが、初期表示・SNS等での見え方に影響する）
- [ ] `index.json`のタイトル・説明・地図の初期位置（`map.center`）を書き換える
- [ ] `index.json`の`features`（サンプルスポット）を、実際のスポットに置き換える
- [ ] `date.json`のカバー・イベントを、実際の年中行事・イベントに置き換える
- [ ] `favicon`・OGP等、サイト固有にしたい部分があれば別途検討する（現状はsdk側の共通アセットを使用）