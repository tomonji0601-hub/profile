# ともきのホームページ

GitHub PagesとJekyllで公開する個人サイトです。架空の論文紹介は掲載せず、記事のひな形を未公開の `_drafts` に入れています。

## 初回公開

1. GitHubで `ユーザー名.github.io` という名前のリポジトリを作成します。
2. このフォルダの「中身」をリポジトリ直下にアップロードします。`_layouts` や `_drafts` も必要です。
3. `_config.yml` の `url` を `https://ユーザー名.github.io` に変更します。`baseurl` は空のままにします。
4. Settings → Pages → Build and deploymentで、Sourceを `Deploy from a branch`、Branchを `main`、フォルダを `/(root)` にして保存します。
5. GitHub上のビルド完了後、表示された公開URLを確認します。

通常のリポジトリ名（例 `research-notes`）で公開する場合、`baseurl: "/research-notes"` に変更します。

## Notesの記事を追加

`_drafts/paper-note-template.md` をコピーし、`_posts/2026-09-25-paper-short-name.md` のような名前で保存します。日付は公開日、英語部分は記事のURLになります。先頭の `---` で囲まれた情報と本文を編集してコミットすると、一覧に自動で追加されます。`_posts` フォルダがGitHub上になければ「Add file → Create new file」でフォルダ名を含めたパスを入力します。

`doi_url` は確認した `https://doi.org/...` を記入します。未確認なら空欄のままにしてください。`_drafts` の記事は通常公開されませんが、公開リポジトリではソース自体を誰でも読めるため、非公開資料や個人情報は置かないでください。

## 公開前の確認

- 名前・所属・研究紹介文を自分の希望に合わせて編集（名前は `_layouts/default.html`、`index.html`、`_config.yml` にあります）。
- 初期プロフィールは「ともき」と所属・研究領域のみ。学年や進学予定などは記載していません。
- 記事で原論文の結果と自分の考察を分け、図表を載せる場合は転載条件を確認します。

## ローカル確認（任意）

RubyとBundlerのある環境で `bundle install` のあと `bundle exec jekyll serve`。表示されたローカルURLを開きます。

`preview.html` は初期トップページの見た目を手元で確認するためのファイルで、公開対象から除外しています。記事追加後の本番確認はJekyllで行ってください。

公式ガイド:
- https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 自分で変える場所

- 自己紹介・研究内容：`index.html` の日本語部分を編集。
- サイト名：`_layouts/default.html`、`index.html`、`_config.yml` を編集。
- 色・文字サイズ・余白：`assets/style.css` を編集。
- Notesの記事本文：`_posts` 内のMarkdownファイルを編集。

記事の見出しは自由です。ひな形を全部埋める必要はなく、短いメモでも掲載できます。

## トップの研究写真

`assets/field.jpg` などに自分の写真を置き、`_config.yml` の `cover_image` に `"/assets/field.jpg"` を指定します。`cover_alt` に写真の内容、`cover_caption` に説明を記入できます。写真未指定の場合は写真欄を表示しません。参考サイトの大学ロゴ・写真は使用していません。

## Home / Research / Notes

- Home（`index.html`）：自己紹介と最近の記事5件。
- Research（`research.html`）：研究内容。
- Notes（`notes.html`）：論文紹介と研究活動の記事を新しい順に一覧表示。各タイトルから独立した記事ページへ移動できます。
- 論文紹介には `_drafts/paper-note-template.md`、活動記録には `_drafts/activity-note-template.md` をコピーして使います。どちらも `_posts/YYYY-MM-DD-英語の短い名前.md` に保存すると公開対象になります。
- `kind` は任意の分類です。「論文」「研究活動」などを指定できます。活動記録では論文の書誌情報は表示されません。
- ZIP内の `preview.html` → `preview-research.html` → `preview-notes.html` のメニューはローカルでも移動できます。これらは現時点の確認用で、記事を追加した後はGitHub PagesかJekyllで確認してください。
