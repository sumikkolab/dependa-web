<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-ja.png" alt="Dependa" width="480" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  依存関係と AI 構成を静的解析 — 脆弱性・ライセンス・ガバナンスをワンスキャンで。
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

Copilot が `requirements.txt` に足したパッケージ、ライセンスを確認しましたか？ Cursor が生成した `package.json`、その推移的依存に既知の CVE が含まれていないと言い切れますか？ Terraform で定義した AI サービスのリージョン設定、データがどこで処理されるか把握していますか？

AI コード生成が当たり前になった結果、自分で選んでいない依存を出荷するようになりました。AI SDK やモデル設定が気づかないうちに増えています。でもリスクの責任は変わらずあなたにあります。

**Dependa は Windows でローカル動作し、オフラインで回答を出します。クラウド不要。アカウント不要。**

## 機能

### スキャン

- **Python** (pip)、**NuGet** (.csproj / packages.config)、**Node.js** (npm)
- バンドル済みアドバイザリ DB による脆弱性照合 — ネットワーク不要
- ライセンス分類: Approved / Caution / Prohibited / Unknown

### AI Governance (v1.5 New)

- **AI BOM** — AI SDK・モデル設定・API キー・エンドポイントを依存関係・ソースコード・環境変数・IaC から統合的に棚卸し
- **Excessive Agency 検出** — ワイルドカード IAM・自動承認・無制限ループなど過大権限の候補を検出
- **Data Sovereignty 確認** — AI サービスのリージョン設定・データ送信先を確認
- **組織ポリシー照合** — 許可リージョン・承認済みプロバイダとの照合

### IaC 対応 (v1.5 New)

- **Terraform** (.tf) — HCL 軽量構造認識で AI リソースを検出
- **Bicep** (.bicep) — Azure AI リソースを検出、param default 解決
- **ARM JSON** (.json) — ARM テンプレートから AI リソースを検出

### レポート

- 自己完結型 HTML — 外部 CSS/JS なし、オフラインで開ける、そのまま印刷可
- CycloneDX 1.5 SBOM (JSON)
- LLM に貼り付けて修正指示に使える構造化プロンプト出力

### 分析 (Pro)

- **マルチエコシステム統合** — Python + npm を同時スキャン、統合結果表示
- **ライセンス互換性** — Apache-2.0 + GPL-2.0 特許条項の衝突、Copyleft と Proprietary の混在を検出・説明
- **脆弱性トリアージ** — severity 別の内訳、影響パッケージ、修正パス
- **Delta Scan** — 前回スキャンとの差分比較。AI BOM / Finding の追加・削除・新規・解消も検出 (v1.5 New)
- **例外管理** — 既知の問題を理由・承認者・期限付きで許容。追跡・取消・延長が可能
- **オンライン OSV 照合** — リアルタイム CVE データ（オプトイン）
- **オンラインライセンス補完** — PyPI / npm レジストリから補足

## オフラインが既定

オプトインしない限りネットワーク通信ゼロ。脆弱性照合、ライセンス分類、ポリシーチェック、AI Governance、IaC 解析、レポート、SBOM — すべてローカル。

## CLI + GUI

同一バイナリ。

```powershell
Dependa.exe                                                    # GUI
Dependa.exe scan --path ./myproject --accept-terms             # スキャン
Dependa.exe scan --path ./myproject --ai-prompt vuln           # AI 修正プロンプト
Dependa.exe scan --path ./myproject --lang ja                  # 日本語出力
```

## Free と Pro

**Free** — Python + NuGet スキャン、ローカル脆弱性照合、ライセンス分類、AI Governance（AI BOM / Excessive Agency / Data Sovereignty / 組織ポリシー照合）、IaC 対応（Terraform / Bicep / ARM JSON）、HTML レポート、SBOM。「今どうなっているか？」に答える。

**Pro** — Node.js、マルチエコシステム統合、Delta Scan（AI Governance 差分を含む）、例外管理、オンライン OSV 照合、ライセンス互換性分析、脆弱性トリアージを追加。「前回から何が変わったか、何から直すか？」に答える。Microsoft Store でワンタイム購入。

## インストール

**[Microsoft Store](https://apps.microsoft.com/detail/9P84RLQQ401D)** — 自動更新、ランタイム不要。

## プライバシー

テレメトリなし。分析なし。アカウント不要。[プライバシーポリシー](https://dependa.sumikkolab.com/privacy-policy.html)。

## ライセンス

Proprietary。Free 版は無償。[Sumikko Lab](https://dependa.sumikkolab.com)。
