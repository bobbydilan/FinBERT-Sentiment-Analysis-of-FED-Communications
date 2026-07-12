# FinBERT Sentiment Analysis of Federal Reserve Communications

## Description

This project analyzes Federal Reserve minutes, statements, transcripts, and press releases using **FinBERT** for sentiment analysis. The results are enriched with additional economic data to give a comprehensive view of sentiment trends over time.

## Repository contents

| File | Description |
|---|---|
| `full-scraping-and-analysis-code.ipynb` | Jupyter notebook with the full scraping and sentiment-analysis pipeline. |
| `sentiment_scores_enriched.csv` | FinBERT sentiment scores enriched with additional economic indicators. |
| `LICENSE` | MIT License. |

## Data

- The corpus covers publicly available Federal Reserve communications — minutes, statements, transcripts, and press releases.
- Sentiment scores are computed with FinBERT and enriched with economic indicators.
- The full scraped raw text (minutes, statements, Greenbook, and transcripts, 1968–2025) is available on Kaggle: **@federicogalli12**.

## Getting started

Clone the repository:

```bash
git clone https://github.com/bobbydilan/FinBERT-Sentiment-Analysis-of-FED-Communications.git
```

Install the main dependencies:

```bash
pip install transformers torch pandas numpy matplotlib jupyter
```

Open and run the notebook:

```bash
jupyter notebook full-scraping-and-analysis-code.ipynb
```

Running the notebook reproduces the scraping and FinBERT sentiment analysis; the enriched output is saved as `sentiment_scores_enriched.csv`.

## License

This project is licensed under the MIT License — see [`LICENSE`](LICENSE) for details.

## Contact

For questions or feedback, reach out to Federico Galli on Discord: **@bobbydylan3428123**.
