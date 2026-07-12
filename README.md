# FinBERT Sentiment Analysis of Federal Reserve Communications

Sentiment analysis of Federal Reserve communications from 1968 to 2025 — minutes, statements, transcripts, and press releases — using [FinBERT](https://huggingface.co/yiyanghkust/finbert-tone), a BERT model fine-tuned for financial text. The resulting sentiment scores are enriched with market and macroeconomic indicators to give a comprehensive view of Fed sentiment trends over time.

## What it does

1. **Scrapes** publicly available Federal Reserve communications (FOMC minutes, statements, transcripts, Beige Books, press releases) from federalreserve.gov, extracting text from both HTML pages and PDFs.
2. **Scores sentiment** for each document with the `yiyanghkust/finbert-tone` model (PyTorch + Hugging Face Transformers), aggregated per meeting date and per document type.
3. **Enriches** the scores with market and macro data — S&P 500 7-day change, VIX, inflation, the federal funds rate, unemployment, 10-year and 3-month Treasury yields, and the yield-curve spread — via `yfinance` and `pandas-datareader` (FRED).

## Repository contents

| File | Description |
| --- | --- |
| `full-scraping-and-analysis-code.ipynb` | End-to-end notebook: scraping, text extraction, FinBERT scoring, and data enrichment. Originally written for Google Colab (the Drive-mount cells can be skipped when running locally). |
| `sentiment_scores_enriched.csv` | Final output: per-date sentiment scores by document type (`Statement_Score`, `Minutes_Score`, `Transcript_Score`, `Internal_Score`, `Overall_Score`) alongside the enrichment variables listed above, from 1968 onward. |
| `requirements.txt` | Python dependencies. |
| `LICENSE` | MIT license. |

## How to run

```bash
pip install -r requirements.txt
jupyter notebook full-scraping-and-analysis-code.ipynb
```

Execute the notebook top to bottom to re-scrape, re-score, and re-enrich. The finished dataset is already included as `sentiment_scores_enriched.csv`, so the notebook only needs to be re-run to refresh or extend the data. A GPU is recommended for the FinBERT scoring step.

## Data sources

- **Federal Reserve communications** — scraped from [federalreserve.gov](https://www.federalreserve.gov) (minutes, statements, transcripts, Beige Books, press releases).
- **Raw scraped text (1968–2025)** — the full scraped corpus (minutes, statements, green book, transcripts) is available on Kaggle: [@federicogalli12](https://www.kaggle.com/federicogalli12).
- **Market data** — S&P 500 and VIX via `yfinance`.
- **Macro indicators** — inflation, federal funds rate, unemployment, Treasury yields via `pandas-datareader` (FRED).
- **Sentiment model** — [`yiyanghkust/finbert-tone`](https://huggingface.co/yiyanghkust/finbert-tone).

## License

MIT — see [LICENSE](LICENSE).

## Contact

Federico Galli — [@bobbydilan](https://github.com/bobbydilan) on GitHub.
