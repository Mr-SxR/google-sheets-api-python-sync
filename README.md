# 🧾 Connect Google Sheets API with Python for Real-Time Data Sync

Easily connect your Python script with Google Sheets using the **Google Sheets API**  
and keep your data synced in real-time — no manual updates required.

---

## 🚀 Overview

Google Sheets API allows developers to **read, write, and update spreadsheet data** programmatically.  
By connecting it with Python, you can automate data entry, generate reports, and sync information across systems in real time.

Common use cases:
- Syncing sales data between your CRM and Google Sheets  
- Pushing data from APIs or databases to Sheets  
- Automating reports and dashboards  
- Creating live analytics pipelines  

---

## 🧰 Requirements

Before you start, make sure you have:

- Python 3.8+ installed  
- A Google Cloud account  
- The `google-api-python-client` and `gspread` libraries  
- Access to a Google Sheet  

---

## ⚙️ Step 1: Enable Google Sheets API

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).  
2. Create a new project (or use an existing one).  
3. Navigate to **APIs & Services → Library**.  
4. Enable **Google Sheets API** and **Google Drive API**.  
5. Go to **Credentials → Create Credentials → Service Account Key**.  
6. Download the generated `credentials.json` file.

📂 Place this file in your project directory.

---

## 🧩 Step 2: Install Dependencies

Install the required libraries using `pip`:

```bash
pip install gspread google-auth
```

---

## 🔑 Step 3: Authenticate with Google

Use the downloaded `credentials.json` to authenticate your script:

```python
import gspread
from google.oauth2.service_account import Credentials

# Define the scope (permissions)
scope = ["https://spreadsheets.google.com/feeds",
         "https://www.googleapis.com/auth/spreadsheets",
         "https://www.googleapis.com/auth/drive"]

# Authenticate and connect
creds = Credentials.from_service_account_file("credentials.json", scopes=scope)
client = gspread.authorize(creds)
```

✅ This connects your Python script to your Google Account using a secure service key.

---

## 📄 Step 4: Connect to a Google Sheet

You can open a Google Sheet either by its name or by URL.
```python
# Open by sheet name
sheet = client.open("Sales Data").sheet1

# OR open by URL
# sheet = client.open_by_url("https://docs.google.com/spreadsheets/d/YOUR_SHEET_ID/edit").sheet1
```

Once connected, you can read and write data just like a normal Python list.

---

## 📊 Step 5: Read and Write Data

**Read Data:**

```python
records = sheet.get_all_records()
for row in records:
    print(row)
```

**Write Data:**

```python
sheet.append_row(["2025-11-12", "New Order", "Completed", 420])
```

✅ Each time this script runs, it appends a new row to your Google Sheet.


## 🔁 Step 6: Real-Time Data Sync

To make your integration real-time, you can schedule the script to run periodically (e.g., every 5 minutes).

#### Option 1: Using `schedule` Library

```pyrhon
import schedule, time

def sync_data():
    sheet.append_row(["New API Data", "Synced", "✅"])
    print("Data synced successfully!")

schedule.every(5).minutes.do(sync_data)

while True:
    schedule.run_pending()
    time.sleep(1)
```

#### Option 2: Using Cron (Linux) or Task Scheduler (Windows)

Run your script automatically in the background at fixed intervals.

---

## 🧠 Pro Tips

- 🧱 Keep credentials secure — never upload them to GitHub.  
- ⚙️ Use environment variables for API keys.  
- 🕒 Add timestamps to track when data was synced.  
- 📈 Combine this with REST APIs for live dashboards.  
- 🧩 Automate both read & write to make it bidirectional.  

---

## 🧩 Example Project Idea

**Goal:** Sync data between an eCommerce API and Google Sheets.  
**Flow:**
1. Fetch new orders via API.  
2. Process the data in Python.  
3. Push the results into a Google Sheet.  
4. Trigger Slack or Email alerts if new data is added.

Such automation can eliminate daily manual work and maintain a seamless data pipeline.

---

## 🏁 Conclusion

Google Sheets + Python = endless automation possibilities.

By integrating the Google Sheets API, you can:
- Centralize and update business data in real-time  
- Automate repetitive reporting tasks  
- Build intelligent, connected dashboards  
- Deliver more value to clients and teams  

Mastering this makes Google Sheets your personal data command center —  
fully automated, always updated.

---

## 💼 Hire Me

Need help setting up real-time Google Sheets automation?  
I help businesses and freelancers connect systems to Google Sheets using **Python, APIs, and smart automation workflows**.

📩 **Email:** masudurrahmansifat@gmail.com  
🌐 **Portfolio:** [GitHub Profile](https://github.com/mr-sxr)  
💬 **WhatsApp:** [Chat on WhatsApp](https://wa.me/+8801858094178)  
📨 **Telegram:** [Message on Telegram](https://t.me/sifathub)

Let’s bring your data to life — automatically ⚡  

---

**Tags:** `python` `google-sheets` `api` `automation` `data-sync` `integration` `gspread` `google-api` `freelance`

> ⭐ Found this helpful? Star this repo and start automating your Sheets today!
