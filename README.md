# ほどほどにね！はしごショッピング（shop.hashigo-map.com）

はしごシリーズの通販サイトまとめ。よく使う通販サイトを一覧で開き、セールの予定を見て、商品名をまとめて各サイトで検索できる。

- `public/` をそのまま Cloudflare Pages の `hashigo-shop` プロジェクトへ公開する（main への push で自動公開）
- 会員登録なし。登録内容は利用者のブラウザ（localStorage）だけに保存し、サーバーには送らない
- 全ページ noindex（`_headers`）。pages.dev は Cloudflare Access で自分だけ閲覧可（他のはしごサイトと同じ設定）

## 初回だけ

1. リポジトリの Secrets に `CLOUDFLARE_API_TOKEN` と `CLOUDFLARE_ACCOUNT_ID` を登録（他のはしごサイトと同じ値）
2. main に push すると Pages プロジェクト `hashigo-shop` が作られて公開される
3. Pages の「カスタムドメイン」に `shop.hashigo-map.com` を追加（DNS は自動）
4. Access「pages.dev production（はしごシリーズ）」に `hashigo-shop.pages.dev` と `*.hashigo-shop.pages.dev` を追加
5. ポータル（kuwabaratakumi/hashigo-map）の `public/index.html` にカードを足す

## 今の状態（試作版）

- 初期サイト：Amazon、ヨドバシ・ドット・コム、Paul Smith、LADER
- セール情報は表示確認用のサンプル（日付は仮）。公式API・手入力カレンダーからの取り込みはこれから
- 通知は、ページを開いているときのブラウザ通知のみ。閉じていても届く Web Push はこれから
- Paul Smith と LADER の検索URLはサイトの作りからの推測。要確認

企画メモ：claude.ai プロジェクト「OCOSCOサイトプロジェクト」の `hashigo-ec/planning-2026-11-09.md`
