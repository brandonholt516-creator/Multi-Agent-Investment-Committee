# LLM Multi-Agent Quantitative Investment Committee (`llm_quant1`)

An automated quantitative and qualitative investment analysis engine that orchestrates a multi-agent debate workflow using **Groq** and **yFinance**. The system fetches real-time market data, calculates key technical indicators, pulls historical fundamental metrics, and synthesizes them into actionable investment committee reports.

## 🧠 System Architecture & Multi-Agent Flow
The project runs an iterative pipeline across multiple dedicated LLM agents:
1. **Technical Analyst Agent**: Evaluates short-term price action, trends (MAs), RSI, ATR, and volume dynamics.
2. **Fundamental Analyst Agent**: Reviews long-term dividend growth, payout ratios, revenue trends, valuation metrics (P/E, P/S), and balance sheet health.
3. **Challenger Agent (Cross-Examination)**: Forces agents to self-critique, flag logical conflicts, and surface missing assumptions.
4. **Investment Committee Synthesizer**: Reconciles the conflicting analytical time horizons into a final recommendation and risk-adjusted position size.

## 🛠️ Features
- **Automated Pipeline**: End-to-end data acquisition via `yfinance`.
- **Resilient Workflows**: Implements custom rate-limit wrapping (`safe_call`) for seamless LLM connection stability.
- **Report Generation**: Dynamically formats standalone analytical records (`investment_report_*.md`) and multi-stage conversation step logs (`transcript_*.md`).
- **Structured Validation**: Clean JSON regex parsing layer ensures strict enforcement of schema structures returned by underlying models.

## 🚀 Setup & Installation

### 1. Clone the Project
```bash
git clone https://github.com
cd llm_quant1
```
*(Note: Replace `YOUR_GITHUB_USERNAME` with your actual GitHub username).*

### 2. Configure Local Environment Variables
Create a file named `.env` in the root folder to house your API access tokens safely. Do **not** commit this file to Git.
```text
GROQ_API_KEY=your_actual_groq_api_key_here
```

### 3. Install Dependencies
You can install dependencies via your terminal:
```bash
pip install pandas numpy yfinance groq python-dotenv
```
*Alternatively, the notebook includes embedded `%pip install` commands to automatically configure your environment when you select **Run All**.*

```

## 📈 Usage
Run all pipeline segments sequentially via your code editor or by selecting **Run All** directly from the Jupyter interface notebook file:
```bash
jupyter notebook final_version_capstone.ipynb
```

## 📁 Output Artifacts
Once execution concludes successfully, check the newly generated `outputs/` subfolder directory for analytical assets:
- `outputs/final_memo.json`: Final structural consensus weights.
- `investment_report_AAPL_*.md`: Human-readable Markdown breakdown for presentation.
- `transcript_AAPL_*.md`: Step-by-step trace of agent conversational debate stages.

## 🔒 Security
This repository includes a strict `.gitignore` mapping structure preventing local configuration files (`.env`), system caches, environment settings (`.venv`), or active credential footprints from tracking upstream to global history registries.

