# CommentLens

**Turn YouTube comments into structured product intelligence.**

CommentLens analyzes YouTube video comments using AI to extract sentiment, pain points, feature requests, and praise — so product managers, brand teams, and creators can make decisions based on what users actually say, not what they assume.

## What it does

Point it at any YouTube video. CommentLens will:

1. Fetch the top comments (up to 50 in the open-source edition)
2. Run each comment through an LLM to classify sentiment, category, and extract structured tags
3. Synthesize a final report: ranked pain points, feature requests, praise highlights, and sentiment breakdown
4. Export as an HTML report + CSV data file

The analysis distinguishes between **product feedback**, **meta feedback** (about the YouTuber/video itself), and **off-topic comments** — so you get signal about the product, not noise about the reviewer.

## Quick Start

```bash
# Clone
git clone https://github.com/Alex-gmdotcom/commentlens.git
cd commentlens

# Install dependencies
pip install -r requirements.txt

# Run
python commentlens.py
```

A GUI window opens. Fill in the YouTube URL, product name, select your AI provider, paste your API key, and click "Start".

**Important**: Use the specific product name (e.g. `JetKVM`, `iPhone 16 Pro`), not a brand name (`Apple`, `Xiaomi`). Brand names cause the analysis to lose focus.

## Supported AI Providers

| Provider | Get API Key | Recommended Model | Est. Cost / Report |
|----------|------------|-------------------|-------------------|
| Claude | [console.anthropic.com](https://console.anthropic.com) | claude-sonnet-4-5 | ~$0.03 |
| OpenAI | [platform.openai.com](https://platform.openai.com/api-keys) | gpt-4o-mini | ~$0.02 |
| Gemini | [aistudio.google.com](https://aistudio.google.com/apikey) | gemini-2.5-flash | ~$0.01 |
| DeepSeek | [platform.deepseek.com](https://platform.deepseek.com) | deepseek-chat | ~$0.01 |
| MiniMax | [minimaxi.com](https://www.minimaxi.com) | MiniMax-M2.7 | China-friendly |

API keys are stored locally in `~/.commentlens_config.json` and never leave your machine.

## Output

Each run produces two files on your Desktop:

- **`CommentLens_Report_{product}_{timestamp}.html`** — Visual report with sentiment breakdown, ranked pain points, feature requests, and praise
- **`CommentLens_Data_{product}_{timestamp}.csv`** — Per-comment analysis data for your own exploration

## Sample Report

> Screenshot of a sample report will be added here after the first demo run.

<!-- TODO: Add screenshot -->

## Limitations (Open Source Edition)

- **50 comment limit** — enough to see trends, not enough for statistical confidence
- **Basic report only** — sentiment, pain points, features, praise
- No executive summary with counter-intuitive findings
- No attribution analysis (why a pain point exists)
- No recommended actions per pain point
- No competitive intelligence section
- No action checklist (this week / this month / monitor)

## Need deeper analysis?

We offer professional comment intelligence reports for brands, agencies, and MCNs:

| Report | What you get | Price |
|--------|-------------|-------|
| **Single Video Deep-Dive** | 500+ comments, executive summary, attribution analysis, action checklist, formatted PDF | $49 |
| **Competitive Scan** | 3–5 videos compared, cross-video patterns, competitive positioning | $199 |
| **Channel Intelligence** | Full channel (up to 20 videos), longitudinal trends, strategic recommendations | $499+ |

Turnaround: 48–72 hours. → [Order a report](https://alex-gmdotcom.github.io/commentlens/)

## FAQ

**Does this use the official YouTube Data API?**
Comment fetching uses the public library `youtube-comment-downloader`. For commercial / high-volume use, switch to the official YouTube Data API.

**Can I run this without an API key?**
No. The analysis requires an LLM. Without one you'd just have a comment scraper.

**Does it support languages other than English?**
Yes. Comments are analyzed in their original language. The report language (Chinese or English) is selectable in the GUI.

## Contributing

PRs welcome, especially for:

- Official YouTube Data API integration
- Additional output formats (Markdown, Notion, Slack)
- Non-English report templates
- Performance improvements for batching

## License

MIT — use it freely. Attribution appreciated but not required.

---

<details>
<summary>中文说明</summary>

## CommentLens — YouTube 评论智能分析工具

将 YouTube 视频评论转化为结构化的产品洞察：情感分析、痛点提取、需求归类、好评亮点。

### 快速开始

```bash
git clone https://github.com/Alex-gmdotcom/commentlens.git
cd commentlens
pip install -r requirements.txt
python commentlens.py
```

启动后填入 YouTube 视频链接、产品名称、选择 AI 提供商并粘贴 API Key，点击"开始分析"即可。

### 支持的 AI 提供商

Claude / OpenAI / Gemini / DeepSeek / MiniMax（5 家全覆盖）

### 开源版限制

- 最多分析 50 条评论
- 基础报告（情感分布 + 痛点 + 需求 + 好评）
- 不含执行摘要、归因分析、行动清单、竞品洞察

### 需要更深度的分析？

我提供专业的评论分析报告服务，面向品牌方、MCN 和咨询机构：

- **单视频深度分析** $49 / ¥349
- **竞品对比扫描** $199 / ¥1,399
- **频道情报分析** $499+ / ¥3,500+

→ [了解详情](https://alex-gmdotcom.github.io/commentlens/)

</details>
