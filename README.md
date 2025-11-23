# .Automated-Web-Scraper-with-Schedule
Create a tool to scrape dynamic websites and store the data periodically.
# Automated Web Scraper with Scheduler (Beginner-Friendly Project)

## Overview
This is a Python-based automated web scraper that collects data from a website at regular intervals and stores it in a SQLite database.  
It also supports exporting the collected data into a CSV file.  
This project is ideal for beginners who want to learn web scraping, automation, and basic data storage.

---

## Features
- Scrapes quotes and authors from a sample website
- Stores scraped data in SQLite
- Automatically runs every 2 minutes using a scheduler
- Exports all collected data into CSV
- 100% beginner-friendly
- Works on Google Colab, Google AI Studio (Pilot), or locally

---

## Project Structure

---

## Installation
Install the required Python libraries:

---

## How to Run the Project

### Step 1: Run the scheduler

This will:
- scrape data every 2 minutes  
- store it inside `scraped_data.db`

### Step 2: Export to CSV
Run the following inside Python:

python
from database import export_to_csv
export_to_csv()
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
from bs4 import BeautifulSoup
from datetime import datetime

def scrape_data():
    url = "https://quotes.toscrape.com/js/"

    options = Options()
    options.add_argument("--headless")
    driver = webdriver.Chrome(options=options)

    driver.get(url)
    html = driver.page_source
    driver.quit()

    soup = BeautifulSoup(html, "html.parser")
    quotes = soup.select(".quote")
    data = []

    for q in quotes:
        text = q.select_one(".text").get_text(strip=True)
        author = q.select_one(".author").get_text(strip=True)

        data.append({
            "text": text,
            "author": author,
            "timestamp": datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        })

    return data

## 📦 Installation

1. Clone the repo:

2. Install dependencies:

3. Install a Selenium driver (ChromeDriver recommended)

Download:
https://chromedriver.chromium.org/

Then place it in the project folder.

4. Run scraper once:

5. Run the scheduled version:


## 🧪 How It Works

- **Selenium** loads the page fully.
- **BeautifulSoup** extracts the data from HTML.
- The data is inserted into an **SQLite table**.
- The scheduler repeatedly calls the scraper at your chosen time.
- You can press `CTRL + C` to stop it anytime.

## 📤 Exporting CSV

Creates:  
`output.csv`

## 🖼 Demo Screenshot
![Demo](demo_screenshot.png)

## 🤝 Contribute
Feel free to fork the repo and add:
- selector options
- multiple website support
- logging and error handling

## 🧑‍💻 Author
**Somashree Sadhukhan**

---


