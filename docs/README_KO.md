<div align="center">

# AI 주식 분석 시스템

[![GitHub stars](https://img.shields.io/github/stars/ZhuLinsen/daily_stock_analysis?style=social)](https://github.com/ZhuLinsen/daily_stock_analysis/stargazers)
[![CI](https://github.com/ZhuLinsen/daily_stock_analysis/actions/workflows/ci.yml/badge.svg)](https://github.com/ZhuLinsen/daily_stock_analysis/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-Ready-2088FF?logo=github-actions&logoColor=white)](https://github.com/features/actions)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker&logoColor=white)](https://hub.docker.com/r/zhulinsen/daily_stock_analysis)

<p align="center">
  <a href="https://trendshift.io/repositories/18527" target="_blank"><img src="https://trendshift.io/api/badge/repositories/18527" alt="ZhuLinsen%2Fdaily_stock_analysis | Trendshift" width="230" /></a>&nbsp;<a href="https://hellogithub.com/repository/ZhuLinsen/daily_stock_analysis" target="_blank"><img src="https://api.hellogithub.com/v1/widgets/recommend.svg?rid=6daa16e405ce46ed97b4a57706aeb29f&claim_uid=pfiJMqhR9uvDGlT&theme=neutral" alt="Featured | HelloGitHub" width="230" /></a>
</p>

**AI 대형 언어 모델을 활용한 A주 / 홍콩 주식 / 미국 주식 워치리스트 분석 시스템**

워치리스트를 매일 분석 -> 의사결정 대시보드 생성 -> Telegram / Discord / Slack / Email / WeChat Work / Feishu 로 전송합니다.

[**제품 미리보기**](#-제품-미리보기) · [**주요 기능**](#-주요-기능) · [**빠른 시작**](#-빠른-시작) · [**출력 예시**](#-출력-예시) · [**문서 색인 EN**](./INDEX_EN.md) · [**전체 가이드 EN**](./full-guide_EN.md)

[English](README_EN.md) | [简体中文](../README.md) | [繁體中文](README_CHT.md) | [日本語](README_JA.md) | 한국어

> 한국어 버전은 우선 README 를 제공합니다. 아직 번역되지 않은 상세 문서는 당분간 영어 문서로 안내합니다.

</div>

## 💖 Sponsors

<div align="center">
  <p align="center">
    <a href="https://open.anspire.cn/?share_code=QFBC0FYC" target="_blank"><img src="assets/anspire.png" alt="Anspire Open all-in-one model and search service" width="300" height="141" style="width: 300px; height: 141px; object-fit: contain;"></a>
    <a href="https://serpapi.com/baidu-search-api?utm_source=github_daily_stock_analysis" target="_blank"><img src="assets/serpapi_banner_en.png" alt="SerpApi realtime financial news search data" width="300" height="141" style="width: 300px; height: 141px; object-fit: contain;"></a>
  </p>
</div>

## 🖥️ 제품 미리보기

<p align="center">
  <img src="assets/readme_workspace_tour_20260510.gif" alt="DSA Web workspace demo" width="720">
</p>

## ✨ 주요 기능

| 기능 | 범위 |
|------|------|
| AI 의사결정 리포트 | 핵심 결론, 점수, 추세, 진입/청산 가격대, 리스크 경고, 촉매 요인, 실행 체크리스트 |
| 멀티 마켓 데이터 | A주, 홍콩 주식, 미국 주식, ETF. 시세, K라인, 기술 지표, 자금 흐름, 칩 분포, 뉴스, 공시, 펀더멘털 |
| Web / 데스크톱 워크스페이스 | 수동 분석, 작업 진행률, 과거 리포트, 전체 Markdown, 백테스트, 포트폴리오, 설정, 라이트 / 다크 테마 |
| Agent 전략 채팅 | 15 개 내장 전략 기반의 멀티턴 Q&A. Web / Bot / API 에서 사용 가능 |
| 스마트 가져오기와 자동 완성 | 이미지, CSV/Excel, 클립보드 가져오기. 종목 코드, 이름, 병음, 별칭 자동 완성 |
| 자동화와 알림 | GitHub Actions, Docker, 로컬 스케줄러, FastAPI, WeChat Work / Feishu / Telegram / Discord / Slack / Email 전송 |

> 세부 필드 계약, 데이터 소스 우선순위, Web/API 동작, 문제 해결은 [Full Guide (EN)](./full-guide_EN.md)를 참고하세요.

### 기술 스택과 데이터 소스

| 유형 | 지원 |
|------|------|
| AI 모델 | [Anspire](https://open.anspire.cn/?share_code=QFBC0FYC), [AIHubMix](https://aihubmix.com/?aff=CfMq), Gemini, OpenAI 호환 제공자, DeepSeek, Qwen, Claude, Ollama |
| 시장 데이터 | [TickFlow](https://tickflow.org/auth/register?ref=WDSGSPS5XC), AkShare, Tushare, Pytdx, Baostock, YFinance, Longbridge |
| 뉴스 검색 | [Anspire](https://open.anspire.cn/?share_code=QFBC0FYC), [SerpAPI](https://serpapi.com/baidu-search-api?utm_source=github_daily_stock_analysis), [Tavily](https://tavily.com/), [Bocha](https://open.bocha.cn/), [Brave](https://brave.com/search/api/), [MiniMax](https://platform.minimaxi.com/), SearXNG |
| 소셜 심리 | [Stock Sentiment API](https://api.adanos.org/docs). Reddit / X / Polymarket 지원, 미국 주식만 해당, 선택 사항 |

## 🚀 빠른 시작

### 방법 1: GitHub Actions 권장

약 5 분 안에 배포할 수 있으며 서버가 필요 없습니다.

#### 1. 저장소 Fork

오른쪽 위의 `Fork` 버튼을 클릭합니다. 프로젝트가 도움이 되었다면 Star 도 환영합니다.

#### 2. Secrets 설정

Fork 한 저장소에서 `Settings` -> `Secrets and variables` -> `Actions` -> `New repository secret` 으로 이동합니다.

**AI 모델 설정. 최소 1 개를 설정하세요.**

먼저 하나의 제공자와 API Key 로 시작하세요. 멀티 모델 라우팅, 이미지 인식, 로컬 모델, 고급 설정은 [LLM Config Guide (EN)](./LLM_CONFIG_GUIDE_EN.md)를 참고하세요.

| Secret 이름 | 설명 | 필수 |
|-------------|------|:----:|
| `ANSPIRE_API_KEYS` | Anspire API Key. 모델과 웹 검색을 함께 사용할 수 있습니다 | 권장 |
| `AIHUBMIX_KEY` | AIHubMix API Key. 여러 모델 패밀리를 전환해 사용할 수 있습니다 | 권장 |
| `GEMINI_API_KEY` | Google Gemini API Key | 선택 |
| `ANTHROPIC_API_KEY` | Anthropic Claude API Key | 선택 |
| `OPENAI_API_KEY` | OpenAI 호환 API Key. DeepSeek, Qwen 호환 서비스를 포함합니다 | 선택 |
| `OPENAI_BASE_URL` / `OPENAI_MODEL` | OpenAI 호환 서비스를 사용할 때 설정합니다 | 선택 |

**알림 채널. 최소 1 개를 설정하세요.**

| Secret 이름 | 설명 |
|-------------|------|
| `WECHAT_WEBHOOK_URL` | WeChat Work bot |
| `FEISHU_WEBHOOK_URL` | Feishu bot |
| `TELEGRAM_BOT_TOKEN` + `TELEGRAM_CHAT_ID` | Telegram |
| `DISCORD_WEBHOOK_URL` | Discord webhook |
| `SLACK_BOT_TOKEN` + `SLACK_CHANNEL_ID` | Slack bot |
| `EMAIL_SENDER` + `EMAIL_PASSWORD` | Email 전송 |

**워치리스트. 필수입니다.**

| Secret 이름 | 설명 | 필수 |
|-------------|------|:----:|
| `STOCK_LIST` | 예: `600519,hk00700,AAPL,TSLA` | 필수 |

뉴스 검색을 설정하면 심리, 공시, 이벤트, 촉매 요인의 품질이 좋아집니다. 지원 서비스와 fallback 규칙은 [Search Configuration (EN)](./full-guide_EN.md#search-service-configuration)을 참고하세요.

#### 3. Actions 활성화

`Actions` 탭에서 `I understand my workflows, go ahead and enable them` 을 클릭합니다.

#### 4. 수동 테스트

`Actions` -> `Daily Stock Analysis` -> `Run workflow` -> `Run workflow` 를 실행합니다.

기본값은 베이징 시간 평일 18:00 실행이며 비거래일은 건너뜁니다.

### 방법 2: 로컬 / Docker

```bash
git clone https://github.com/ZhuLinsen/daily_stock_analysis.git && cd daily_stock_analysis
pip install -r requirements.txt
cp .env.example .env && vim .env
python main.py
```

자주 쓰는 명령:

```bash
python main.py --debug
python main.py --dry-run
python main.py --stocks 600519,hk00700,AAPL
python main.py --market-review
python main.py --schedule
python main.py --serve-only
```

Docker 배포, 스케줄링, 클라우드 서버 WebUI 접속은 [Full Guide (EN)](./full-guide_EN.md)를 참고하세요.

## 📱 출력 예시

### 의사결정 대시보드

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

## ⚙️ 설정

환경 변수, 모델 라우팅, 알림 채널, 데이터 소스 우선순위, 거래 규칙, 배포 세부 사항은 [Full Guide (EN)](./full-guide_EN.md)에 있습니다.

## 🖥️ Web UI

Web 워크스페이스는 설정, 작업 모니터링, 수동 분석, 과거 리포트, 전체 Markdown 리포트, Agent 전략 채팅, 백테스트, 포트폴리오 관리, 스마트 가져오기, 라이트 / 다크 테마를 제공합니다.

```bash
python main.py --webui
python main.py --webui-only
```

`http://127.0.0.1:8000` 으로 접속하세요. 인증, 스마트 가져오기, 자동 완성, 히스토리 복사, 클라우드 서버 공개는 [Local WebUI Management (EN)](./full-guide_EN.md#local-webui-management-interface)를 참고하세요.

## 🤖 Agent 전략 채팅

사용 가능한 AI API Key 를 설정하면 Web `/chat` 페이지에서 전략 채팅을 사용할 수 있습니다. 명시적으로 끄고 싶을 때만 `AGENT_MODE=false` 를 설정하세요.

- 이동평균 크로스, Chan theory, Elliott wave, 강세 추세, 테마, 이벤트 기반, 성장 품질, 기대 리프라이싱 등 내장 전략
- 실시간 시세, K라인, 기술 지표, 뉴스, 리스크 맥락 호출
- 후속 질문, 세션 내보내기, 알림 전송, 백그라운드 실행
- 사용자 정의 전략 파일과 실험적 멀티 Agent 편성

## 🧩 관련 프로젝트

| Project | Focus |
|---------|-------|
| [AlphaSift](https://github.com/ZhuLinsen/alphasift) | 멀티팩터 종목 스크리닝과 전체 시장 스캔 |
| [AlphaEvo](https://github.com/ZhuLinsen/alphaevo) | 전략 백테스트와 자기 진화 실험 |

## 📞 Contact

| 항목 | 내용 |
|------|------|
| Email | [zhuls345@gmail.com](mailto:zhuls345@gmail.com) |
| Feedback | [GitHub Issues](https://github.com/ZhuLinsen/daily_stock_analysis/issues) · [Discussions](https://github.com/ZhuLinsen/daily_stock_analysis/discussions) |

## 📄 License

[MIT License](../LICENSE) © 2026 ZhuLinsen

## ⚠️ 면책 조항

이 프로젝트는 정보 제공과 학습을 위한 것입니다. AI 가 생성한 분석은 투자 조언이 아닙니다. 주식 투자에는 위험이 있습니다. 직접 조사하고 필요한 경우 자격을 갖춘 전문가와 상담하세요.
