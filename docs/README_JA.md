<div align="center">

# AI 株式分析システム

[![GitHub stars](https://img.shields.io/github/stars/ZhuLinsen/daily_stock_analysis?style=social)](https://github.com/ZhuLinsen/daily_stock_analysis/stargazers)
[![CI](https://github.com/ZhuLinsen/daily_stock_analysis/actions/workflows/ci.yml/badge.svg)](https://github.com/ZhuLinsen/daily_stock_analysis/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-Ready-2088FF?logo=github-actions&logoColor=white)](https://github.com/features/actions)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker&logoColor=white)](https://hub.docker.com/r/zhulinsen/daily_stock_analysis)

<p align="center">
  <a href="https://trendshift.io/repositories/18527" target="_blank"><img src="https://trendshift.io/api/badge/repositories/18527" alt="ZhuLinsen%2Fdaily_stock_analysis | Trendshift" width="230" /></a>&nbsp;<a href="https://hellogithub.com/repository/ZhuLinsen/daily_stock_analysis" target="_blank"><img src="https://api.hellogithub.com/v1/widgets/recommend.svg?rid=6daa16e405ce46ed97b4a57706aeb29f&claim_uid=pfiJMqhR9uvDGlT&theme=neutral" alt="Featured | HelloGitHub" width="230" /></a>
</p>

**AI 大規模言語モデルを使った A 株 / 香港株 / 米国株向けのウォッチリスト分析システム**

ウォッチリストを毎日分析 -> 意思決定ダッシュボードを生成 -> Telegram / Discord / Slack / Email / WeChat Work / Feishu に配信します。

[**製品プレビュー**](#-製品プレビュー) · [**主な機能**](#-主な機能) · [**クイックスタート**](#-クイックスタート) · [**出力例**](#-出力例) · [**ドキュメント索引 EN**](./INDEX_EN.md) · [**フルガイド EN**](./full-guide_EN.md)

[English](README_EN.md) | [简体中文](../README.md) | [繁體中文](README_CHT.md) | 日本語 | [한국어](README_KO.md)

> 日本語版はまず README を提供しています。詳細ドキュメントは未翻訳のため、当面は英語版に案内します。

</div>

## 💖 Sponsors

<div align="center">
  <p align="center">
    <a href="https://open.anspire.cn/?share_code=QFBC0FYC" target="_blank"><img src="assets/anspire.png" alt="Anspire Open all-in-one model and search service" width="300" height="141" style="width: 300px; height: 141px; object-fit: contain;"></a>
    <a href="https://serpapi.com/baidu-search-api?utm_source=github_daily_stock_analysis" target="_blank"><img src="assets/serpapi_banner_en.png" alt="SerpApi realtime financial news search data" width="300" height="141" style="width: 300px; height: 141px; object-fit: contain;"></a>
  </p>
</div>

## 🖥️ 製品プレビュー

<p align="center">
  <img src="assets/readme_workspace_tour_20260510.gif" alt="DSA Web workspace demo" width="720">
</p>

## ✨ 主な機能

| 機能 | 内容 |
|------|------|
| AI 意思決定レポート | 結論、スコア、トレンド、売買水準、リスク警告、材料、アクションチェックリスト |
| マルチマーケットデータ | A 株、香港株、米国株、ETF。価格、K 線、テクニカル、資金フロー、チップ分布、ニュース、公告、ファンダメンタルズ |
| Web / デスクトップワークスペース | 手動分析、タスク進捗、履歴レポート、完全な Markdown、バックテスト、ポートフォリオ、設定、ライト / ダークテーマ |
| Agent 戦略チャット | 15 種類の内蔵戦略を使った複数ターン Q&A。Web / Bot / API から利用可能 |
| スマートインポートと補完 | 画像、CSV/Excel、クリップボード取り込み。銘柄コード、名称、ピンイン、別名補完 |
| 自動化と通知 | GitHub Actions、Docker、ローカルスケジューラー、FastAPI、WeChat Work / Feishu / Telegram / Discord / Slack / Email 配信 |

> 詳細なフィールド契約、データソース優先順位、Web/API の挙動、トラブルシューティングは [Full Guide (EN)](./full-guide_EN.md) を参照してください。

### 技術スタックとデータソース

| 種別 | サポート |
|------|----------|
| AI モデル | [Anspire](https://open.anspire.cn/?share_code=QFBC0FYC), [AIHubMix](https://aihubmix.com/?aff=CfMq), Gemini, OpenAI 互換プロバイダー, DeepSeek, Qwen, Claude, Ollama |
| マーケットデータ | [TickFlow](https://tickflow.org/auth/register?ref=WDSGSPS5XC), AkShare, Tushare, Pytdx, Baostock, YFinance, Longbridge |
| ニュース検索 | [Anspire](https://open.anspire.cn/?share_code=QFBC0FYC), [SerpAPI](https://serpapi.com/baidu-search-api?utm_source=github_daily_stock_analysis), [Tavily](https://tavily.com/), [Bocha](https://open.bocha.cn/), [Brave](https://brave.com/search/api/), [MiniMax](https://platform.minimaxi.com/), SearXNG |
| ソーシャルセンチメント | [Stock Sentiment API](https://api.adanos.org/docs)。Reddit / X / Polymarket に対応、米国株のみ、任意設定 |

## 🚀 クイックスタート

### 方法 1: GitHub Actions 推奨

約 5 分でデプロイできます。サーバーは不要です。

#### 1. リポジトリを Fork

右上の `Fork` をクリックします。プロジェクトが役に立ったら Star も歓迎です。

#### 2. Secrets を設定

Fork したリポジトリで `Settings` -> `Secrets and variables` -> `Actions` -> `New repository secret` を開きます。

**AI モデル設定。少なくとも 1 つ設定してください。**

まず 1 つのプロバイダーと API Key から始めます。複数モデルのルーティング、画像認識、ローカルモデル、高度な設定は [LLM Config Guide (EN)](./LLM_CONFIG_GUIDE_EN.md) を参照してください。

| Secret 名 | 説明 | 必須 |
|-----------|------|:----:|
| `ANSPIRE_API_KEYS` | Anspire API Key。モデルと Web 検索をまとめて利用できます | 推奨 |
| `AIHUBMIX_KEY` | AIHubMix API Key。複数モデルファミリーを切り替えて利用できます | 推奨 |
| `GEMINI_API_KEY` | Google Gemini API Key | 任意 |
| `ANTHROPIC_API_KEY` | Anthropic Claude API Key | 任意 |
| `OPENAI_API_KEY` | OpenAI 互換 API Key。DeepSeek や Qwen 互換サービスを含みます | 任意 |
| `OPENAI_BASE_URL` / `OPENAI_MODEL` | OpenAI 互換サービスを使う場合に設定します | 任意 |

**通知チャンネル。少なくとも 1 つ設定してください。**

| Secret 名 | 説明 |
|-----------|------|
| `WECHAT_WEBHOOK_URL` | WeChat Work bot |
| `FEISHU_WEBHOOK_URL` | Feishu bot |
| `TELEGRAM_BOT_TOKEN` + `TELEGRAM_CHAT_ID` | Telegram |
| `DISCORD_WEBHOOK_URL` | Discord webhook |
| `SLACK_BOT_TOKEN` + `SLACK_CHANNEL_ID` | Slack bot |
| `EMAIL_SENDER` + `EMAIL_PASSWORD` | Email 配信 |

**ウォッチリスト。必須です。**

| Secret 名 | 説明 | 必須 |
|-----------|------|:----:|
| `STOCK_LIST` | 例: `600519,hk00700,AAPL,TSLA` | 必須 |

ニュース検索を設定すると、センチメント、公告、イベント、材料の品質が上がります。対応サービスとフォールバックの詳細は [Search Configuration (EN)](./full-guide_EN.md#search-service-configuration) を参照してください。

#### 3. Actions を有効化

`Actions` タブで `I understand my workflows, go ahead and enable them` をクリックします。

#### 4. 手動テスト

`Actions` -> `Daily Stock Analysis` -> `Run workflow` -> `Run workflow` を実行します。

デフォルトでは平日の北京時間 18:00 に実行され、非取引日はスキップされます。

### 方法 2: ローカル / Docker

```bash
git clone https://github.com/ZhuLinsen/daily_stock_analysis.git && cd daily_stock_analysis
pip install -r requirements.txt
cp .env.example .env && vim .env
python main.py
```

よく使うコマンド:

```bash
python main.py --debug
python main.py --dry-run
python main.py --stocks 600519,hk00700,AAPL
python main.py --market-review
python main.py --schedule
python main.py --serve-only
```

Docker、スケジューリング、クラウドサーバーでの WebUI 利用は [Full Guide (EN)](./full-guide_EN.md) を参照してください。

## 📱 出力例

### 意思決定ダッシュボード

```markdown
🎯 2026-02-08 Decision Dashboard
Analyzed 3 stocks | 🟢 Buy:0 🟡 Watch:2 🔴 Sell:1

📊 Summary
🟡 000657: Watch | Score 65 | Bullish
🟡 600105: Watch | Score 48 | Range-bound
🔴 300260: Sell | Score 35 | Bearish

🚨 Risk Alerts:
Risk 1: Main-force funds showed notable outflow.
Risk 2: Chip concentration suggests short-term resistance.
```

## ⚙️ 設定

環境変数、モデルルーティング、通知チャンネル、データソース優先順位、取引ルール、デプロイの詳細は [Full Guide (EN)](./full-guide_EN.md) にあります。

## 🖥️ Web UI

Web ワークスペースでは、設定、タスク監視、手動分析、履歴レポート、完全な Markdown レポート、Agent 戦略チャット、バックテスト、ポートフォリオ管理、スマートインポート、ライト / ダークテーマを利用できます。

```bash
python main.py --webui
python main.py --webui-only
```

`http://127.0.0.1:8000` にアクセスしてください。認証、スマートインポート、補完、履歴コピー、クラウドサーバー公開の詳細は [Local WebUI Management (EN)](./full-guide_EN.md#local-webui-management-interface) を参照してください。

## 🤖 Agent 戦略チャット

利用可能な AI API Key を設定すると、Web の `/chat` ページで戦略チャットを使えます。明示的に無効化する場合のみ `AGENT_MODE=false` を設定してください。

- 移動平均クロス、Chan theory、Elliott wave、強気トレンド、テーマ株、イベントドリブン、成長品質、期待リプライシングなどの内蔵戦略
- リアルタイム価格、K 線、テクニカル指標、ニュース、リスク文脈の呼び出し
- フォローアップ質問、セッションエクスポート、通知送信、バックグラウンド実行
- カスタム戦略ファイルと実験的なマルチ Agent 編成

## 🧩 関連プロジェクト

| Project | Focus |
|---------|-------|
| [AlphaSift](https://github.com/ZhuLinsen/alphasift) | マルチファクター銘柄スクリーニングと全市場スキャン |
| [AlphaEvo](https://github.com/ZhuLinsen/alphaevo) | 戦略バックテストと自己進化実験 |

## 📞 Contact

| 項目 | 内容 |
|------|------|
| Email | [zhuls345@gmail.com](mailto:zhuls345@gmail.com) |
| Feedback | [GitHub Issues](https://github.com/ZhuLinsen/daily_stock_analysis/issues) · [Discussions](https://github.com/ZhuLinsen/daily_stock_analysis/discussions) |

## 📄 License

[MIT License](../LICENSE) © 2026 ZhuLinsen

## ⚠️ 免責事項

このプロジェクトは情報提供と学習を目的としています。AI が生成した分析は投資助言ではありません。株式投資にはリスクがあります。必ず自分で調査し、必要に応じて資格を持つ専門家に相談してください。
