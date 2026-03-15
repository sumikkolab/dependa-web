<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/home-screen-ja.png" alt="Dependa" width="480" />
</p>

<h1 align="center">Dependa</h1>

<p align="center">
  依存ライブラリの脆弱性とライセンスをまとめてチェック。Windows で動く、オフライン対応の分析ツール。
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

## こんな経験はありませんか

Copilot が `requirements.txt` にパッケージを追加した。ライセンスは確認しましたか？ Cursor が `package.json` を生成した。その中の依存に既知の脆弱性が含まれていないと言い切れますか？

AI がコードを書く時代になり、自分で選んでいないライブラリが製品に入るようになりました。それでも、リスクの責任はあなたにあります。

ライセンスを調べるには SPDX を手作業で突き合わせ、脆弱性は OSV をひとつずつ検索、SBOM を作るにはまた別のツール。翌日にはライブラリが変わっている。

よくある SCA ツールは CI 環境と Linux が前提で、Windows で開発している現場には合いません。

**Dependa なら、Windows 上でそのまま動きます。ネット接続も不要。アカウント登録も不要。インストールしてすぐ使えます。**

## 機能

### スキャン

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/scan-results-ja.png" alt="スキャン結果" width="720" />
</p>

- **Python**（pip）、**NuGet**（.csproj / packages.config）、**Node.js**（npm）に対応
- 脆弱性データを内蔵（Python 243件 / NuGet 45件）しているので、ネットにつながなくても検出可能
- ライセンスを自動で分類（承認 / 注意 / 禁止 / 不明）
- 判定の**信頼度**を表示（高 / 中 / 低 / 要確認）— どこまで信用できるかがわかる
- PowerShell スクリプトやブラウザ拡張の外部接続先も検査

### レポート

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/html-report-ja.png" alt="HTML レポート" width="720" />
</p>

- HTML レポートを自動生成。外部ファイル不要で、そのまま開いて印刷できる
- CycloneDX 1.5 準拠の SBOM（JSON）を出力
- OSS 一覧表（CSV）とライセンス通知文書も生成可能
- ChatGPT や Claude に貼れる修正支援プロンプトも出力

### 高度な分析（Pro）

<p align="center">
  <img src="https://dependa.sumikkolab.com/manual/images/license-analysis-ja.png" alt="ライセンス分析" width="720" />
</p>

- **ライセンス互換性チェック** — Apache-2.0 と GPL-2.0 の特許条項の衝突や、コピーレフトと商用ライセンスの混在を検出して解説
- **脆弱性の優先度整理** — 深刻度ごとの内訳、影響を受けるパッケージ、修正方法を提示
- **リスクスコア** — パッケージごとに 0〜100 で定量的にリスクを評価
- **OSS 利用審査の支援** — 各パッケージの推奨アクション、商用利用時の注意点、組織向けチェックリストを生成
- **Delta Scan** — 前回のスキャン結果との差分を表示
- **オンラインでの確認** — 内蔵データの判定結果を、PyPI / npm / NuGet の公式情報で照合して信頼度を引き上げ
- **最新の脆弱性情報** — OSV API に問い合わせて、リアルタイムの CVE データで照合（任意で有効化）

## ネット接続なしで使える

通常のスキャンでは、インターネットに一切接続しません。脆弱性の照合、ライセンスの分類、ポリシーの判定、レポートの生成 — すべてローカルで完結します。

内蔵データが古くなると（90日以上経過時）、更新を促す案内が表示されます。

オンライン機能（OSV API、PyPI、npm、NuGet）もありますが、ユーザーが明示的に有効にしない限り通信は発生しません。

## GUI でも CLI でも

同じアプリで両方使えます。

```powershell
Dependa.exe                                                    # GUI を起動
Dependa.exe scan --path ./myproject --accept-terms             # コマンドラインでスキャン
Dependa.exe scan --path ./myproject --export all --overwrite   # CSV・通知文書・審査レポートを出力
Dependa.exe scan --path ./myproject --ai-prompt vuln           # AI 向け修正プロンプトを生成
Dependa.exe scan --path ./myproject --lang ja                  # 日本語で出力
```

## 無料版と Pro 版

**無料版** — Python と NuGet のスキャン、脆弱性の照合、信頼度つきライセンス分類、HTML レポート、SBOM、CSV 一覧表、ライセンス通知文書、スクリプト検査。「このプロジェクトに問題はあるか？」に答えます。

**Pro 版** — 上記に加えて、Node.js 対応、オンライン脆弱性照合、ライセンスのオンライン検証、互換性チェック、脆弱性の優先度整理、リスクスコア、OSS 審査支援、差分比較、審査レポート出力。「どこが深刻で、何から対応すべきか」まで踏み込みます。Microsoft Store で買い切り。

## インストール

**[Microsoft Store](https://apps.microsoft.com/detail/9P84RLQQ401D)** からインストールできます。自動更新、ランタイムの追加インストール不要。

## ドキュメント

**[ユーザーマニュアル](https://dependa.sumikkolab.com/manual/)** — 使い方、スキャン手順、レポートの読み方、CLI コマンド一覧、Pro 機能の活用、よくある問題と対処法。

## プライバシー

利用状況の収集や分析は一切行いません。アカウント登録も不要です。[プライバシーポリシー](https://dependa.sumikkolab.com/privacy-policy.html)

## ライセンス

Dependa は商用ソフトウェアです。無料版は費用なしで利用できます。開発元: [Sumikko Lab](https://dependa.sumikkolab.com)。使用しているサードパーティライセンス: [ThirdPartyNotices](https://dependa.sumikkolab.com/manual/licensing.html)
