<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-ja.png?v=2.0" alt="Dependa ダッシュボード" width="720" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  OSS を使っていいか判断し、記録して、説明できるツール
</p>

<p align="center">
  <a href="https://apps.microsoft.com/detail/9P84RLQQ401D">
    <img alt="Microsoft Store" src="https://img.shields.io/badge/Microsoft_Store-入手する-0078d4?style=for-the-badge&logo=microsoft" />
  </a>
</p>

<p align="center">
  <a href="../README.md">English version</a>
</p>

---

## 何が問題か

ベンダーから SBOM を受け取りました。140 パッケージ。どのライセンスを確認すべきですか？ 脆弱性はありますか？ 誰が何を承認しましたか？

AI コード生成が当たり前になり、自分で選んでいない依存を出荷するようになりました。監査で「OSS をどう管理しているか」を聞かれたとき、説明できますか？

**Dependa は SBOM を読み込み、リスクを分類し、レビュー・承認・レポートを支援します。ローカル完結。オフライン。クラウド不要。アカウント不要。**

---

## インポートとリスク分析

**CycloneDX**（1.2〜1.6）と **SPDX**（2.2〜2.3）の JSON を自動判定してインポート。またはフォルダスキャン（Python / NuGet / Node.js）。

すべてのコンポーネントに **リスクレベル**（高リスク / リスクあり / 既知・通常）、リスク理由、推奨対応、根拠、確信度を付与。

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/scan-results-ja.png?v=2.0" alt="リスク分析 — 高リスクコンポーネント" width="720" />
  <br><sub>高リスクの Unknown ライセンスを検出 — ガイドパネルで次の手順を案内</sub>
</p>

---

## レビューと承認ワークフロー

コンポーネントごとに **承認** / **要対応** / **確認中** をレビュー。進捗バーと統計で完了率を把握。ガイドパネルで非技術者でも操作可能。

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/review-detail-enriched-ja.png?v=2.0" alt="レビュー詳細 — オンライン補完済み" width="720" />
  <br><sub>オンライン補完で Unknown → MIT に解決。詳細パネルにライセンス情報・PURL・レビューコントロール</sub>
</p>

ワークフロー: **未開始 → レビュー中 → 完了 → 承認待ち → 差し戻し**

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/review-detail-risk-ja.png?v=2.0" alt="レビュー詳細 — リスク情報" width="720" />
  <br><sub>脆弱性情報・リスク理由・推奨対応がコンポーネントの詳細に表示</sub>
</p>

---

## レポート

エグゼクティブサマリー（リスク内訳・レビュー統計）、要対応項目のハイライト。自己完結型 HTML。

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/html-report-ja.png?v=2.0" alt="SBOM レビューレポート" width="720" />
  <br><sub>SBOM レビューレポート — コンポーネント数、リスク内訳、レビュー状態、ライセンス種別</sub>
</p>

---

## ポリシー

組織のライセンスルールを定義: **許可 / 要承認 / 禁止**。テンプレートから読み込み、カスタマイズ可能。

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/policy-builder-ja.png?v=2.0" alt="組織ポリシー" width="720" />
  <br><sub>24 ルール — GPL 禁止、LGPL 要承認、MIT/Apache 許可</sub>
</p>

---

## プロジェクト管理

複数の SBOM レビューをプロジェクト単位で管理。担当者、最終レビュー日、コンポーネント数、リスクサマリーを記録。

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/projects-ja.png?v=2.0" alt="プロジェクト管理" width="720" />
  <br><sub>6 プロジェクトを管理 — レビュー履歴とリスク数を一覧</sub>
</p>

---

## ダッシュボード

全レビュー活動の概要: レビュー実績、ワークフロー状態、ポリシー状況、最近のプロジェクト。

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-ja.png?v=2.0" alt="ダッシュボード" width="720" />
  <br><sub>ダッシュボード — 11 レビュー、要対応 7、高リスク 34（6 プロジェクト）</sub>
</p>

---

## AI Governance

- **AI BOM** — AI SDK・モデル設定・API キー・エンドポイントの棚卸し
- **Excessive Agency 検出** — 過大権限・自動承認パターンの検出
- **Data Sovereignty** — AI サービスのリージョン・データ送信先確認
- **IaC 対応** — Terraform / Bicep / ARM JSON から AI リソースを検出

## オフラインが既定

オプトインしない限りネットワーク通信ゼロ。リスク分析、ライセンス分類、ポリシーチェック、AI Governance、レポート — すべてローカル。

## Free と Pro

| | Free | Pro |
|---|---|---|
| SBOM インポート（CycloneDX / SPDX） | 1 ファイル | 無制限 |
| リスク分析（全詳細） | 全項目 | 全項目 |
| レビュー | 5 件まで | 無制限 |
| 承認ワークフロー | 表示のみ | 全遷移 |
| レポート | 透かし付き | 完全版 |
| SBOM 差分比較 | — | あり |
| オンライン補完（PyPI / npm / NuGet） | — | あり |
| AI Governance レポート | 表示のみ | レポート含む |
| プロジェクト管理 | 1 件 | 無制限 |

**Free** は「この SBOM にどんなリスクがあるか？」に答えます。
**Pro** は「レビューして、承認して、報告する」を実現します。

## インストール

**[Microsoft Store](https://apps.microsoft.com/detail/9P84RLQQ401D)** — 自動更新、ランタイム不要。

## プライバシー

テレメトリなし。分析なし。アカウント不要。[プライバシーポリシー](https://dependa.sumikkolab.com/privacy-policy.html)。

## ライセンス

Proprietary。Free 版は無償。[Sumikko Lab](https://dependa.sumikkolab.com)。
