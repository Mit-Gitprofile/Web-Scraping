# Web-Scraping

## Live Scraping Summary -> https://web-scraping-beta-neon.vercel.app/

# 🛒 Flipkart Mobile Price Scraper

> A Python web scraping project that extracts **216 mobile product listings** from Flipkart across 10 paginated search result pages — collecting product names, prices, specifications, and ratings into a structured CSV dataset.

---

## 📸 Project Preview

| Feature | Detail |
|---|---|
| 🌐 Source | [flipkart.com/search?q=mobile](https://www.flipkart.com/search?q=mobile) |
| 📦 Records Scraped | 216 raw rows / 158 unique products |
| 🏷️ Brands Covered | 19 brands (Apple, Samsung, realme, OnePlus, POCO …) |
| 📊 Output Format | CSV via Pandas DataFrame |
| 🛠️ Language | Python 3 · Jupyter Notebook |

---

## 🗂️ Project Structure

```
flipkart-mobile-scraper/
│
├── flipcart.ipynb        # Main scraper notebook
├── data.csv              # Scraped output dataset
└── README.md             # This file
```

### Step-by-Step Flow

```
┌─────────────────────────────────────────────────────────┐
│  Loop i = 0 → 9  (10 pages of Flipkart search results) │
│                                                         │
│  1. Build URL  →  GET request  →  parse with BS4       │
│  2. Locate product grid  →  div.DOjaWF.gdgoEp          │
│  3. Extract fields:                                     │
│       • Name        →  div.KzDlHZ                      │
│       • Price       →  div.Nx9bqj._4b5DiR              │
│       • Description →  ul.G4BRas                       │
│       • Review      →  div.XQDdHH                      │
│  4. Append to lists                                     │
└────────────────────────┬────────────────────────────────┘
                         │
                         ▼
              pd.DataFrame({...})
                         │
                         ▼
                    data.csv  ✅
```

---

## 📊 Dataset Schema

| Column | Type | Example |
|---|---|---|
| `Name` | string | `"Nothing Phone (3a) (Black, 128 GB)"` |
| `Price` | string | `"₹24,999"` |
| `Description` | string | `"8 GB RAM | 128 GB ROM | 50MP Camera..."` |
| `Review` | float | `4.5` |

### Sample Data

```
,Name,Price,Description,Review
0,"Nothing Phone (3a) (Black, 128 GB)","₹24,999","8 GB RAM | 128 GB ROM...",4.5
1,"realme P2 Pro 5G (Parrot Green, 512 GB)","₹22,999","12 GB RAM | 512 GB ROM...",4.4
2,"POCO C61 (Ethereal Blue, 64 GB)","₹5,899","4 GB RAM | 64 GB ROM...",4.2
```

---

## 🧰 Tech Stack

| Library | Purpose |
|---|---|
| `requests` | HTTP GET requests to fetch page HTML |
| `beautifulsoup4` | HTML parsing and CSS selector-based extraction |
| `html5lib` / `lxml` | Alternative HTML parsers for BS4 |
| `pandas` | DataFrame construction and CSV export |
| Jupyter Notebook | Interactive development environment |

---

## 📈 Data Insights (from scraped data)

- **Most listed brand:** realme (30+ listings)
- **Cheapest product:** Nokia 105 — ₹1,193
- **Most expensive:** Samsung Galaxy S25 Ultra — ₹1,65,999
- **Average price:** ~₹20,000
- **Average rating:** 4.35 ★
- **Highest-rated products (4.7 ★):** Samsung Galaxy S25 Ultra series

---

## 👤 Author

## **MIT UMARETIYA**

## 📫 Contact Information

- **GitHub:** https://github.com/Mit-Gitprofile
- **LinkedIn:** https://www.linkedin.com/in/mit-umaretiya-562048348/  
- **Email:** mitumaretiya29@gmail.com 
---

> ⭐ If you found this project helpful, please consider giving it a star!
