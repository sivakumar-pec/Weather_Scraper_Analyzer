INTERN ID CITS6831

# Weather Data Scraper & Analyzer

Scrapes live weather data for a city from the free [wttr.in](https://wttr.in)
service (no API key required), logs it over time, and analyzes temperature,
humidity, wind, and rain-chance trends.

## 📌 Project Overview

1. Scrape live weather data (current conditions + 3-day hourly forecast)
2. Log each snapshot to a local CSV to build a real history over time
3. Turn the forecast into a clean, analyzable DataFrame
4. Visualize temperature, humidity, wind, and rain-chance trends
5. Key insights & possible extensions

**City used:** Chennai (change the `CITY` variable in the notebook to track
any other city — wttr.in supports city names worldwide).

## 📡 Data Source

[`wttr.in`](https://wttr.in) — a free weather service with a JSON API, no
sign-up or API key required:
```
https://wttr.in/Chennai?format=j1
```

If there's no internet connection when the notebook runs, it automatically
falls back to a clearly-labeled demo dataset with the exact same structure, so
the analysis pipeline still runs end-to-end. This fallback should be removed
once you've confirmed the notebook runs with live internet access.

## 🛠️ Tools & Libraries

- Python 3
- requests (for scraping)
- pandas, numpy
- matplotlib, seaborn

## 🔑 Key Insights

- Temperature follows a clear daily cycle, rising through the day and
  dropping overnight.
- Temperature and humidity are typically inversely related.
- Rain chance varies noticeably by day — useful for planning ahead.
- The historical log (`weather_log.csv`) grows every run, so running this
  daily builds a genuine multi-day dataset over time.

## 🚀 How to Run

1. Clone this repo or download `Weather_Scraper_Analyzer.ipynb`
2. Make sure you have internet access (needed to reach wttr.in)
3. Open it in Jupyter Notebook, JupyterLab, or Google Colab
4. Run all cells from top to bottom
5. Re-run periodically (e.g. daily) to keep building `weather_log.csv`

## 📁 Files

| File | Description |
|------|-------------|
| `Weather_Scraper_Analyzer.ipynb` | Main notebook — scraper + analysis |
| `weather_log.csv` | Generated automatically after the first run |
| `README.md` | Project overview (this file) |

## ✍️ Author

Siva — B.Tech AI & Data Science, Panimalar Engineering College

## 📈 Possible Next Steps

- Automate the notebook/script via cron (Linux/Mac) or Task Scheduler
  (Windows) to build a multi-week historical dataset
- Track multiple cities in the same log and compare climates
- Add anomaly detection for unusual temperature swings
- Feed the historical log into a simple forecasting model and compare against
  wttr.in's own forecast
