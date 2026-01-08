# 🕵️‍♂️ Phishing Dataset Collector & Automatic Screenshot Tool

This project automatically collects **live phishing URLs**, visits them using a headless browser, captures **full-page screenshots**, and stores metadata for building machine learning datasets for phishing website detection.

It helps in creating **large-scale, real-world phishing datasets** without manual effort. 
---
## 🚀 Features
✔️ Fetches fresh phishing URLs automatically
✔️ Adjustable dataset size (Testing vs Full Dataset)
✔️ Automatically opens each site
✔️ Captures **full-page screenshots**
✔️ Saves screenshots with structured filenames
✔️ Stores metadata (URL, Status, Title, Timestamp, Screenshot Path)
✔️ Skips dead / unreachable sites
✔️ Logs failures separately
✔️ Ready for ML & CV model training

---

## 🏗️ Architecture / Flow

```
Fetch URLs  →  Filter Valid  →  Open in Browser  →  Capture Screenshot
      ↓                       ↓
 Save Metadata           Skip Dead URLs
```

Final Output:

* `/screenshots` → All images
* `dataset.csv` → Metadata + Labels
* `/logs` → Failed & timeout logs

---

## 📥 Data Source

Currently using:

```
https://openphish.com/feed.txt
```

You can also plug:

* PhishTank
* Custom sources
* Local file URL list

---

## 🧰 Tech Stack

* Python
* Selenium / Playwright
* Requests
* Pandas
* Chrome / Chromium Headless

---

## 🔧 Installation

### 1️⃣ Clone Repo

```
git clone <your-repo>
cd phishing-dataset-collector
```

### 2️⃣ Install Requirements

```
pip install -r requirements.txt
```

### 3️⃣ Install Browser Driver

For Selenium (Chrome):

```
Download ChromeDriver compatible with your Chrome version
Add it to PATH
```

For Playwright:

```
pip install playwright
playwright install
```

---

## ▶️ Usage

### Basic Run

```
python main.py
```

### Adjust Dataset Size

In code:

```
LIMIT = 300   # testing
LIMIT = 5000  # full dataset
```

---

## 📂 Output Structure

```
project/
 ├─ screenshots/
 │   ├─ site_001.png
 │   ├─ site_002.png
 │   └─ ...
 ├─ dataset.csv
 ├─ logs/
 │   ├─ failed.txt
 │   └─ timeout.txt
 └─ README.md
```

---

## 🧾 dataset.csv Format

| url                                | title      | status | screenshot_path   | timestamp  | label    |
| ---------------------------------- | ---------- | ------ | ----------------- | ---------- | -------- |
| [https://abc.com](https://abc.com) | login page | live   | screenshots/1.png | 2026-01-07 | phishing |

---

## ⚠️ Error Handling

✔️ Automatically skips:

* Dead websites
* 404 / SSL error pages
* Sites blocking automation
  ✔️ Records failures in `/logs`
  ✔️ Continues crawling smoothly

---

## 🧪 Use Cases

* Computer Vision Phishing Detection
* CNN / ViT Dataset Creation
* Cybersecurity Research
* University Projects
* AI/ML Training

---

## 🔒 Legal Note

This project is for **educational & research purposes only**.
Do **NOT** misuse collected phishing sites.
Use responsibly for cybersecurity improvement only.

---

## 🤝 Contributions

Pull requests welcome!

---

## 👨‍💻 Author
Made with ❤️ by **Sanjay Singh**

---
