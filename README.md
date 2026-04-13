# 🚨 Parallel Text Handling Processor
### Disaster & Crisis Communication Monitor
*Infosys Springboard Project*

---

## 📌 Overview

A Python-based **dual-stream parallel text analysis engine** that simultaneously processes disaster-related data from social media (tweets) and messaging platforms (WhatsApp chats) to extract actionable intelligence in near real-time.

During large-scale disaster events like the **Kerala Floods (2018)** or the **Turkey-Syria Earthquake (2023)**, millions of messages flood in within hours. This system is designed to process both streams in parallel — enabling faster, evidence-based deployment of relief resources.

---

## ⚡ Key Features

- 🔄 **Parallel Processing** — Uses `ProcessPoolExecutor` to split data across CPU cores simultaneously
- 📊 **Dual-Stream Analysis** — Processes both tweets and WhatsApp messages at the same time
- 🔍 **Rule Engine** — 7 regex-based crisis categories (distress signals, disaster types, resources, etc.)
- 🧹 **Real-Time Cleaning Preview** — Step-by-step text cleaning visualization
- 📡 **Real-Time CSV Analysis** — Upload any CSV and get instant alert classification
- 💾 **SQLite Storage** — All results persisted to a local database
- 📈 **Streamlit Dashboard** — Interactive visualizations, word clouds, sentiment analysis

---

## 🗂️ Project Structure

```
parallel_text_processor/
│
├── main.py                  # Entry point — runs full pipeline
├── preprocessing.py         # Text cleaning for tweets & WhatsApp
├── processor.py             # Parallel & sequential NLP processing
├── aggregator.py            # Merges worker results into insights
├── rule_engine.py           # Regex-based crisis keyword detection
├── output_generator.py      # CSV, SQLite, and chart generation
├── dashboard.py             # Streamlit dashboard (UI)
│
├── data/
│   ├── tweets/              # CrisisLexT26 tweet dataset folders
│   └── whatsapp/            # Whatsapp_chat.csv
│
└── output/                  # Generated CSVs, charts, and DB
```

---

## 📦 Datasets Used

| Dataset | Source | Description |
|---|---|---|
| CrisisLexT26 | CrisisNLP | 27,000+ labeled tweets from 26 global disaster events |
| WhatsApp Chat | Kaggle | Community-level messaging data simulating crisis communication |

---

## 🛠️ Installation

```bash
# Clone the repo
git clone https://github.com/SergeantJade/ParallelTextProcessor.git
cd ParallelTextProcessor

# Create virtual environment
python -m venv venv
venv\Scripts\activate      # Windows
source venv/bin/activate   # Mac/Linux

# Install dependencies
pip install -r requirements.txt
```

---

## 🚀 How to Run

**Step 1 — Run the pipeline (processes datasets, generates outputs)**
```bash
python main.py
```

**Step 2 — Launch the dashboard**
```bash
streamlit run dashboard.py
```

---

## 📊 Dashboard Tabs

| Tab | Description |
|---|---|
| 📡 Real-Time Analysis | Upload CSV or enter text → instant alert classification |
| 🐦 Tweets | Keywords, word cloud, sentiment, rule engine charts |
| 💬 WhatsApp | Keywords, active senders, word cloud, sentiment |
| 🔍 Rule Engine | Regex patterns, CSV results, SQLite DB preview |

---

## 🔍 Rule Engine Categories

| Rule | Keywords |
|---|---|
| `distress_signals` | help, trapped, rescue, sos, urgent, missing, emergency |
| `disaster_types` | flood, earthquake, fire, cyclone, tsunami, wildfire |
| `locations` | road, river, village, hospital, school, shelter |
| `resources` | food, water, boat, ambulance, medicine, blanket |
| `sentiment_words` | danger, safe, critical, severe, deadly, hopeful |
| `action_keywords` | evacuate, deployed, relief, alert, warn, coordinate |
| `infrastructure` | power, electricity, dam, highway, airport, grid |

---

## 🧰 Tech Stack

- **Python** — Core language
- **NLTK + TextBlob** — Tokenization & sentiment analysis
- **concurrent.futures** — Parallel processing (ProcessPoolExecutor)
- **Streamlit** — Interactive dashboard
- **SQLite** — Result persistence
- **Matplotlib + WordCloud** — Visualizations
- **Pandas** — Data handling

---

## 👨‍💻 Author

**SergeantJade**  
Infosys Springboard Project
