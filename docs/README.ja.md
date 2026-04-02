<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-ja.png" alt="Dependa" width="480" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  OSS を使っていいか判断し、記録して、説明できるツール
</p>

<p align="center">
  <a href="https://apps.microsoft.com/detail/9P84RLQQ401D">
    <img src="https://get.microsoft.com/images/ja-jp%20dark.svg" alt="Microsoft Store から入手" width="200" />
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

## Dependa でできること

### インポートとリスク分析

- **CycloneDX**（1.2〜1.6）と **SPDX**（2.2〜2.3）の JSON を自動判定してインポート
- またはフォルダスキャン（Python / NuGet / Node.js）
- すべてのコンポーネントに **リスクレベル**（高リスク / リスクあり / 既知・通常）を付与:
  - **リスク理由**（18 分類）— なぜ確認が必要か
  - **推奨対応**（12 種類）— 何をすべきか
  - **根拠** — 分類の裏付けデータ
  - **確信度** — 分析の確度

### レビューと承認ワークフロー

- コンポーネントごとに **承認** / **要対応** / **確認中** をレビュー
- レビュー統計と完了率で進捗を把握
- ワークフロー: 未開始 → レビュー中 → 完了 → 承認待ち → 差し戻し
- ガイドパネルが各ステップで何をすべきか説明 — 非技術者でも操作可能

### レポート

- エグゼクティブサマリー（リスク内訳・レビュー統計）
- 要対応項目をリスク理由・推奨対応付きでハイライト
- 自己完結型 HTML — 外部依存なし、印刷可
- CycloneDX SBOM 出力

### ポリシー

- 組織のライセンスルールを定義: 許可 / 要承認 / 禁止
- テンプレートから読み込み、ライセンスごとにカスタマイズ
- 分析時に自動適用

### AI Governance

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
