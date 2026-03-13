<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-ja.png" alt="Dependa" width="480" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  Windows 向け依存関係リスク分析 — 脆弱性・ライセンス・互換性をワンスキャンで。
</p>

<p align="center">
  <img alt="Status" src="https://img.shields.io/badge/Microsoft%20Store-%E5%AF%A9%E6%9F%BB%E4%B8%AD-orange" />
</p>

<p align="center">
  <a href="../README.md">English version</a>
</p>

---

## 何が問題か

Copilot が `requirements.txt` に足したパッケージ、ライセンスを確認しましたか？ Cursor が生成した `package.json`、その推移的依存に既知の CVE が含まれていないと言い切れますか？

AI コード生成が当たり前になった結果、自分で選んでいない依存を出荷するようになりました。でもリスクの責任は変わらずあなたにあります。ライセンス照合は SPDX を手作業で突き合わせ、脆弱性は OSV をひとつずつ検索、SBOM 生成はまた別のツールの設定。翌日には依存が変わっている。

SCA ツールの大半は CI パイプラインと Linux が前提です。Windows デスクトップで動いている現場には合わない。

**Dependa は Windows でローカル動作し、オフラインで回答を出します。クラウド不要。アカウント不要。**

## 機能

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/scan-results-ja.png" alt="スキャン結果" width="720" />
</p>

### スキャン

- **Python** (pip)、**NuGet** (.csproj / packages.config)、**Node.js** (npm)
- バンドル済みアドバイザリ DB による脆弱性照合 — ネットワーク不要
- ライセンス分類: Approved / Caution / Prohibited / Unknown
- スクリプト・ブラウザ拡張の外部参照検査

### レポート

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/html-report-ja.png" alt="HTML レポート" width="720" />
</p>

- 自己完結型 HTML — 外部 CSS/JS なし、オフラインで開ける、そのまま印刷可
- CycloneDX 1.5 SBOM (JSON)
- LLM に貼り付けて修正指示に使える構造化プロンプト出力

### 分析 (Pro)

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/license-analysis-ja.png" alt="ライセンス分析" width="720" />
</p>

- **ライセンス互換性** — Apache-2.0 + GPL-2.0 特許条項の衝突、Copyleft と Proprietary の混在を検出・説明
- **脆弱性トリアージ** — severity 別の内訳、影響パッケージ、修正パス
- **Delta Scan** — 前回スキャンとの差分
- **オンライン OSV 照合** — リアルタイム CVE データ（オプトイン）
- **オンラインライセンス補完** — PyPI / npm レジストリから補足

## オフラインが既定

オプトインしない限りネットワーク通信ゼロ。脆弱性照合、ライセンス分類、ポリシーチェック、レポート、SBOM — すべてローカル。

## CLI + GUI

同一バイナリ。

```powershell
Dependa.exe                                                    # GUI
Dependa.exe scan --path ./myproject --accept-terms             # スキャン
Dependa.exe scan --path ./myproject --ai-prompt vuln           # AI 修正プロンプト
Dependa.exe scan --path ./myproject --lang ja                  # 日本語出力
```

## Free と Pro

**Free** — Python + NuGet スキャン、ローカル脆弱性照合、ライセンス分類、HTML レポート、SBOM、スクリプト検査。「問題があるか？」に答える。

**Pro** — Node.js、オンライン OSV 照合、ライセンス互換性分析、脆弱性トリアージ、Delta Scan を追加。「どれくらい深刻で、何から直すか？」に答える。Microsoft Store でワンタイム購入。

## インストール

現在 Microsoft Store の審査中です。承認後に Store リンクが有効になります。

## プライバシー

テレメトリなし。分析なし。アカウント不要。[プライバシーポリシー](https://dependa.sumikkolab.com/privacy-policy.html)。

## ライセンス

Proprietary。Free 版は無償。[Sumikko Lab](https://dependa.sumikkolab.com)。
