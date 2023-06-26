# piza_sales_management_system
卒業研究課題１　販売管理システム

## ビジネス課題の確認

### 概要

  - 顧客名称：盛岡情報ビジネス株式会社
  - 依頼内容：注文受付業務システムの開発
  - 開発予算：3000万円
  - 製品納期:2023年9月30日
  - 開発会社：盛ジョビ.com

### 前提
- 盛岡情報ビジネス株式会社の各店舗では、ピザおよび関連商品の製造、宅配を行っている。
- 店舗内で注文を受け付けるスタッフ（インストア）は、顧客から注文依頼の電話を受け、手書きの注文依頼伝票を作成する。
- 顧客の情報は、顧客データベース（既存システム）に問い合わせる。
- 既存顧客の場合は、顧客情報（氏名、カナ、電話番号、住所）を注文依頼伝票に転記する。
- 新規顧客の場合は、顧客情報を注文依頼伝票に記入した上で、顧客データベースに登録する。
- その後、宅配担当のスタッフ（デリバリー）が商品を顧客に配達し、廃タイツが終了すると注文依頼伝票に配達完了を記録する、
- 現状では、注文依頼伝票が手書きの紙媒体であるため、注文受付業務にロスが生じている。
- そのため、T業務本部長とH統括マネージャーは、業務プロセスを見直しの早期実施を考えている。

### インタビュー
　開発に先駆けて、盛岡情報ビジネス株式会社の本件責任者（T業務本部長とH統括マネージャー）に対して、当社(盛ジョビ.com)の営業社員（以下、営業）がインタビューを実施した。
インタビュー内容は次のとおりである。

**営業**　            「開発を希望されている注文受付業務システム（以下、システム）について、ご利用方法をお聞かせください。」

**T業務本部長**　      「各店舗のスタッフが、顧客から注文依頼の電話を受け、顧客の検索、注文登録、注文依頼伝票の発行を行います。」

**営業**              「一連の注文受付業務を自動化ということですね？」

**T業務本部長**        「はい、そうです。将来的には全国的なWebシステムへ移行を考えていますが、現状の問題点解消が最優先事項ですので、各店舗で独立しているシステムで構いません。また、予算の面からも小規模なシステムを考えています。」

**営業**              「現在の顧客数を教えてください。」

**T業務本部長**        「全国に100店舗あり、全店舗で6,000人です。1店舗あたりの顧客数は、200人未満になります。」

**営業**               「主にシステムを利用する方はどなたになりますか？」

**Ｈ統括マネージャー**  「顧客情報の検索と変更、注文登録、注文依頼伝票の発行、配達の確認はインストアが行います。配達完了登録については、デリバリーが行うことが業務フローとして望ましいと考えています。」

**営業**               「顧客情報の変更、配達の確認、配達完了登録も機能として盛り込むということですね？」

**Ｈ統括マネージャー**  「その機能は非常に便利だと思います。ただ、顧客情報の登録は既存システムが利用できますので、システム化の必須機能ではないとと考えています。」

**営業**                「承知しました。その他のご要望はありますか？」

**T業務本部長**        「注文受付業務の改善は急務となっています。できるだけ早いシステム化を希望します。機能は必要最小限にしてください。」

**Ｈ統括マネージャー**  「各店舗では、ピザの製造作業を行いながらシステムを利用しますので、シンプルな操作性が望ましいです。顧客情報の検索、注文登録だけでも、先行して利用できればありがたいです。」 

**T業務本部長**          「近い将来、顧客情報の登録や売上管理機能も盛り込み、業務システムを統合したいと考えています。機能の追加やWebシステムへの移行を視野にいれたシステムにしていただきたいです。」

**営業**                 「承知しました。それでは、社に戻りまして要件定義書を作成いたします。本日はお忙しい中、ありがとうございました。」


### 社内での検討
　盛岡情報ビジネス株式会社の本件責任者とのインタビューを社内に持ち帰り、技術部とともに検討を行った。
   - 当初の開発目的の実行環境はデスクトップアプリケーションであったが、T業務本部長より「今後、Webシステムへの移行を視野にいれたシステムにしていただきたい」とのコメントがあったことを重要視した。
       - ディスクトップアプリとWebアプリの開発コストはあまり違いがないこと。
       - Webアプリはブラウザへの対応のみ考慮すればよいのに対して、デスクトップアプリは、OSやドライバ関係、インストールの検証が必要なこと。
       - デスクトップアプリからWebアプリへの移行のコストが高いこと。

 　このことから、技術部より目的のアプリプラットフォームをWebアプリケーションで開発をするほうがよいと見識があったことを盛岡情報ビジネス株式会社の担当者につたえたところ、了承された。

