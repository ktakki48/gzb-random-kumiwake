# GZB ランダム組み分け

バドミントンダブルス用に、A / B1 / B2 / C の各グループから最大6名を目安に、できるだけ均等な組をランダム作成するHTMLアプリです。

## 最終フォルダ構成

GitHubリポジトリ直下は以下の構成にしてください。

```text
/
├─ index.html
├─ manifest.webmanifest
├─ sw.js
├─ favicon.ico
├─ .nojekyll
├─ icons/
│  ├─ apple-touch-icon.png
│  ├─ favicon-16.png
│  ├─ favicon-32.png
│  ├─ icon-192.png
│  ├─ icon-512.png
│  ├─ icon-source.png
│  └─ icon-source.svg
└─ README.md
```

## GitHub Pages 公開手順

1. GitHubで新規リポジトリを作成します。
2. このZIPを展開し、上記ファイル一式をリポジトリ直下へアップロードします。
3. GitHubの `Settings` → `Pages` を開きます。
4. `Build and deployment` の `Source` を `Deploy from a branch` にします。
5. `Branch` を `main`、フォルダを `/root` にして保存します。
6. 数十秒後に表示される GitHub Pages のURLをSafariで開きます。
7. iPhone Safariの共有ボタンから「ホーム画面に追加」を選びます。

## 保存仕様

登録した名前はブラウザの `localStorage` に保存されます。

そのため、保存データは以下の単位で分かれます。

- 同じiPhone
- 同じブラウザ、Safari
- 同じGitHub Pages URL

リポジトリ名やURLを変えると保存先が変わります。名簿を残したい場合は、アプリ内の名簿バックアップ・名簿を復元機能を使ってください。

## 更新時の注意

`sw.js` はオフライン表示用のキャッシュを使います。ファイル更新後にiPhone側で古い表示が残る場合は、Safariでページを再読み込みするか、一度ホーム画面アイコンを削除して追加し直してください。


## 組み分けルール

- 0名：登録メンバーなし
- 1〜3名：ダブルスが成立しないため「4名以上で構成して下さい。」と表示します。
- 4〜6名：1組として表示します。
- 7名：4名＋3名になり、3名ではダブルスが成立しないため「8名以上で構成して下さい。」と表示します。
- 8名：4名＋4名
- 9名：5名＋4名
- 10名：5名＋5名
- 11名：6名＋5名
- 12名：6名＋6名
