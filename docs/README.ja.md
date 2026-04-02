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

今、Excel でリストを管理して Word でレビュー記録を書いていませんか？ 監査で「OSS をどう管理しているか」を聞かれたとき、説明できますか？

**Dependa は SBOM を読み込み、リスクを分類し、レビュー・承認・レポートを支援します。最終判断は人間が行います。ローカル完結。オフライン。クラウド不要。アカウント不要。**

## なぜこのツールが必要か

ソフトウェアはオープンソースコンポーネントで構成される時代になりました。SBOM の管理、ライセンスの追跡、脆弱性への対応は、ベストプラクティスではなくコンプライアンス義務になりつつあります。

既存のツールの多くは **検出とスキャン** に焦点を当てています。しかし実際の組織で難しいのは検出ではなく、**レビュー・承認・記録・説明** です。

多くのチームが今も Excel、メール、Word で OSS 利用レビューを管理しています。この業務を支援する標準ツールはありません。Dependa はこのギャップを埋めるために作られました。

> **製品カテゴリ**: OSS ガバナンス / SBOM レビュー管理ツール

## Dependa とは — そして何ではないか

Dependa は **OSS レビュー業務ツール** です。利用判断に必要な情報を整理し、判断を記録し、監査で説明できるレポートを出力します。

Dependa はスキャナではありません。OSS 利用の判断を記録し、説明するためのツールです。スキャン結果や SBOM は既にある前提で、その先のレビュー・承認・記録・報告を支援します。

| Dependa であるもの | Dependa ではないもの |
|---|---|
| レビュー・承認・記録のワークフローツール | 脆弱性スキャナ（Trivy / Snyk を使ってください） |
| リスクを分類して判断材料を整理するツール | SBOM 生成ツール（Syft / CycloneDX CLI を使ってください） |
| 判断を記録し監査用レポートを出力するツール | 自動判定ツール — 最終判断は人間が行います |
| ローカル完結のデスクトップ業務ツール | SaaS プラットフォームや CI/CD ツール |

---

## インポートとリスク分析

**CycloneDX**（1.2〜1.6）と **SPDX**（2.2〜2.3）の JSON を自動判定してインポート。またはフォルダスキャン（Python / NuGet / Node.js）。

すべてのコンポーネントに **リスクレベル**（高リスク / リスクあり / 既知・通常）、リスク理由、推奨対応、根拠、確信度を付与。

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/scan-results-ja.png?v=2.0" alt="リスク分析" width="720" />
  <br><sub>Unknown ライセンスが高リスクとして分類されている例 — ガイドパネルで次の手順を案内</sub>
</p>

---

## レビューと承認ワークフロー

コンポーネントごとに **承認** / **要対応** / **確認中** をレビュー。進捗バーと統計で完了率を把握。ガイドパネルで非技術者でも操作可能。

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/review-detail-enriched-ja.png?v=2.0" alt="レビュー詳細" width="720" />
  <br><sub>オンライン補完で Unknown → MIT に解決。詳細パネルにライセンス情報・PURL・レビューコントロール</sub>
</p>

ワークフロー: **未開始 → レビュー中 → 完了 → 承認待ち → 差し戻し**

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/review-detail-risk-ja.png?v=2.0" alt="レビュー詳細 — リスク情報" width="720" />
  <br><sub>脆弱性情報・リスク理由・推奨対応がコンポーネントの詳細に表示</sub>
</p>

---

## レポート

エグゼクティブサマリー（リスク内訳・レビュー統計）、要対応項目のハイライト。自己完結型 HTML。監査・上位層への説明資料として使えます。

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

## AI Governance（フォルダスキャンのみ）

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
| レビュー | 無制限 | 無制限 |
| 承認ワークフロー | 表示のみ | 全遷移 |
| レポート | 透かし付き | 完全版 |
| SBOM 差分比較 | — | あり |
| オンライン補完（PyPI / npm / NuGet） | — | あり |
| AI Governance レポート | 表示のみ | レポート含む |
| プロジェクト管理 | 1 件 | 無制限 |

**Free** は「この SBOM にどんなリスクがあるか？」に答えます。
**Pro** は「レビューして、承認して、報告する」を実現します。

Free で価値を確認し、Pro で業務を回す設計です。

## インストール

**[Microsoft Store](https://apps.microsoft.com/detail/9P84RLQQ401D)** — 自動更新、ランタイム不要。

## リンク

- [製品サイト](https://dependa.sumikkolab.com)
- [ユーザーマニュアル](https://dependa.sumikkolab.com/manual/)
- [Pro 機能ガイド](https://dependa.sumikkolab.com/manual/pro-features.html)
- [サポート](https://dependa.sumikkolab.com/support.html)

## 免責事項

Dependa はレビュー業務に必要な情報を整理するツールです。法的助言、ライセンスコンプライアンスの保証、専門的なセキュリティ評価の代替を提供するものではありません。最終的な利用判断はユーザーおよび所属組織の責任で行ってください。

## プライバシー

テレメトリなし。分析なし。アカウント不要。[プライバシーポリシー](https://dependa.sumikkolab.com/privacy-policy.html)。

## ライセンス

Proprietary。Free 版は無償。[Sumikko Lab](https://dependa.sumikkolab.com)。
