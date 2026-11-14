# amazon-members-guide 収益化改善報告（2026年11月14日）

作業ブランチ：`improve/monetization-2026-11-14`。mainへのマージ・本番公開は未実施です。
既存サイトの修正です。公開中のデザイン、広告コード、Tracking ID、解析IDを保持。順位・AIO引用・成果発生は検証できていません。

## 優先問題と変更

Audible料金・プライム月額年額の2記事で申込時のプラン照合、別契約・更新日・二重登録の注意を補足。8記事の比較表によるスマホ横はみ出しを修正。記事のパンくずと対応する構造化データを追加。

一般記事から該当サービスの説明・公式申込条件へ進む既存導線を維持。申込対象のAudibleプレミアムとスタンダードの違いを明記しました。

## 本文を充実した既存記事

文字数はHTMLからscript/styleと空白を除いた概算で、評価指標ではありません。文字数のための水増しはしていません。

| 記事（公開ディレクトリからの相対パス） | 本文概算・改善前 → 改善後 |
| --- | --- |
| `articles/audible-price.html` | 2098 → 2564 |
| `articles/prime-monthly-yearly.html` | 2175 → 2551 |

パンくずを追加した記事は、その表示内容に合うBreadcrumbListを設定。既存のArticleとcanonicalは照合済みです。架空のReview・AggregateRating・Offerは新設していません。購入者レビュー10本文以上を個別確認できた商品は0件で、レビュー要約は追加していません。価格・仕様の古い確認日を一律に新しくしていません。

## 検証結果

- 静的検証：28ページ（404含む）、エラー0。タイトル・description・h1、canonical、サイトマップ、内部リンク・アンカー・参照資産、JSON-LD、重複タイトル・canonical、トップからの到達性を点検。
- サイトマップ：27URL。noindexとの整合を検証。robots.txtは既存のクロール許可と本番Sitemap指定を維持。
- ブラウザ：360・390・1440pxの84ケース。ページ横はみ出し0。外部広告・解析への通信は遮断。画像の実配信や計測通信の成功を意味しません。
- 改善前の横はみ出し：16ケース → 改善後0ケース。
- 広告保全：リンク・広告画像のHTML断片28個をSHA-256照合、一致。`scripts/affiliate-baseline.json`が修正前の基準です。既存Tracking ID：moon12-22。
- 外部参照先：27URLをHTTP GETで点検。未確認・差し替え前404を含む応答記録は`external-links.json`参照。403/503はリンク切れと断定しません。
- 公開状態：本番の既存ページ・robots・sitemapは200、無効URLは404。ブランチの改善は本番未反映です。
- 表示速度：メダカでは外部画像6リクエストを除去。他サイトを含む本番CWV・Lighthouse・実ユーザーLCP/INP/CLSは未測定。高速化の数値効果は主張しません。

静的HTMLサイトのためビルド工程はありません。

## 未確認事項・公開前の判断

正式なメンバー紹介条件と既存5種のリンク形式を点検。Audibleの880円・1,500円は公式カスタマーサービスで再確認。Kindle+への名称変更はAbout Amazon公式記事で確認。Prime登録画面などは503、紹介料率表の別紙と英語ヘルプには古い条件が混在し、アカウント固有の対象イベント・報酬額・全サービス最新申込画面は未確認です。リンクやTracking IDは変更していません。

共通：Amazonの商品ページの現在の表示・レビュー本文10件、A8管理画面の提携・成果対象・掲載URL、Search Consoleのクエリ別表示回数・CTR・順位、Cloudflare実測速度、実際の成果計測は未確認。広告をテスト購入・申込する検証は行っていません。既存の商品画像は、A8バナー・イメージ・メーカー参照を区別。新しい未許諾写真を追加していません。

## 全ページの診断台帳

`page-audit.json`にtitle/h1/description/canonical・index可否・サイズ・リンク数・構造化データ・到達性を保存。全ページに一律のタイトル変更はせず、検索意図が重なる販売年違いを区別し、問題のある記事とUIを優先しました。トップから到達できないindex許可ページ・内部リンク切れ・完全なタイトル重複は検証後0件。記事の統合・削除はしていません。

| ページ | 検索設定 | 本文概算 | 内部リンク先数 | 広告リンク・画像数 | 構造化データ |
| --- | --- | ---: | ---: | ---: | --- |
| `about.html` | index許可 | 386 | 3 | 0 | WebPage |
| `index.html` | index許可 | 1567 | 15 | 5 | WebPage |
| `404.html` | noindex | 287 | 4 | 0 |  |
| `privacy.html` | index許可 | 521 | 3 | 0 | WebPage |
| `guides.html` | index許可 | 2966 | 27 | 0 | CollectionPage |
| `articles/music-prime-vs-unlimited.html` | index許可 | 2209 | 8 | 1 | None |
| `articles/audible-not-understand.html` | index許可 | 2076 | 8 | 1 | None |
| `articles/audible-commute.html` | index許可 | 2116 | 8 | 1 | None |
| `articles/student-eligibility.html` | index許可 | 2099 | 8 | 1 | None |
| `articles/audible-offline.html` | index許可 | 2202 | 8 | 1 | None |
| `articles/cancel-trial.html` | index許可 | 2138 | 8 | 1 | None |
| `articles/audible-beginner.html` | index許可 | 2251 | 8 | 1 | None |
| `articles/prime-video-difference.html` | index許可 | 2136 | 8 | 1 | None |
| `articles/book-listening-app.html` | index許可 | 2226 | 8 | 1 | None |
| `articles/audiobook-vs-tts.html` | index許可 | 2188 | 8 | 1 | None |
| `articles/audible-sleep-timer.html` | index許可 | 2112 | 8 | 1 | None |
| `articles/audible-not-for-everyone.html` | index許可 | 1998 | 8 | 1 | None |
| `articles/audible-price.html` | index許可 | 2564 | 9 | 1 | None |
| `articles/prime-worth.html` | index許可 | 2188 | 8 | 1 | None |
| `articles/audible-after-cancel.html` | index許可 | 2128 | 8 | 1 | None |
| `articles/audible-vs-kindle.html` | index許可 | 2164 | 8 | 1 | None |
| `articles/prime-monthly-yearly.html` | index許可 | 2551 | 9 | 1 | None |
| `articles/prime-reading-vs-kindle.html` | index許可 | 2375 | 8 | 1 | None |
| `articles/kindle-not-all-books.html` | index許可 | 2189 | 8 | 1 | None |
| `articles/kindle-magazines.html` | index許可 | 2178 | 8 | 1 | None |
| `articles/reading-no-time.html` | index許可 | 2151 | 8 | 1 | None |
| `articles/kindle-phone.html` | index許可 | 2316 | 8 | 1 | None |
| `articles/audio-housework.html` | index許可 | 2074 | 8 | 1 | None |

## 再実行・差分の確認

- `python scripts/check_site.py .`（Python標準ライブラリのみ）
- 全差分：`git diff main...improve/monetization-2026-11-14`
- 本番へのマージ・デプロイは別途承認後。プレビュー環境が自動生成されても本番とは区別。
- 公開後はcanonical・サイトマップの実応答、Search Consoleの除外理由、記事→広告クリック→成果を確認。変更前後で同じ期間・クエリを比較してください。
