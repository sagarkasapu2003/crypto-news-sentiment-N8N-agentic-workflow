# Crypto News Sentiment N8N Agentic Workflow

Automated workflow to fetch top cryptocurrency news, analyze sentiment, predict market impact, and send a daily email digest.

---

## **Overview**

`Crypto News Sentiment N8N Agentic Workflow` is a fully automated system that combines **real-time crypto news**, **NLP-based sentiment analysis**, and **market impact prediction** to provide actionable insights directly to your inbox. Ideal for crypto enthusiasts, traders, and analysts who want to stay informed efficiently.

---

## **Key Features**

- 📰 **Automated News Fetching:** Retrieves latest cryptocurrency news from [CryptoPanic API](https://cryptopanic.com/).  
- 🧠 **Sentiment Analysis:** Uses HuggingFace's `twitter-roberta-base-sentiment-latest` model to classify news as positive, neutral, or negative.  
- 🎯 **Market Impact Prediction:** Calculates potential market impact based on keywords like CPI, FOMC, Jobless, and GDP.  
- 📩 **Daily Email Digest:** Sends a neatly formatted email containing headlines, sentiment scores, predicted impact, and news source.  
- ⚡ **Flexible Deployment:** Can run on **n8n Cloud** or self-hosted using **AWS EC2 + Docker**.  
- 🔄 **Scalable Workflow:** Easily extendable to multiple cryptocurrencies and batch news processing.

---

## **Tech Stack**

- **n8n** – Workflow automation  
- **HuggingFace API** – NLP sentiment analysis  
- **CryptoPanic API** – Real-time crypto news  
- **SMTP / Email Node** – Automated email delivery  
- **Docker & AWS EC2** – Cloud-ready deployment  

---

## **Setup Instructions**

### 1. Clone the Repository

```bash
git clone https://github.com/sagarkasapu2003/crypto-news-sentiment-N8N-agentic-workflow.git
cd crypto-news-sentiment-N8N-agentic-workflow
2. Import the Workflow in n8n

Follow these steps to import the workflow JSON into n8n:

Open n8n Editor:

Cloud: https://app.n8n.cloud

Self-hosted: http://<your-ec2-ip>:5678

Click Workflows → Import.

Choose "Paste JSON" or upload the .json file included in this repository.

Click Import to add the workflow to your n8n instance.

Save the workflow to ensure all nodes and credentials are preserved.

After import, you should see all the nodes: Daily Trigger, Fetch Crypto News, Analyze Sentiment, Predict Market Impact, and Send Email Digest.

3. Configure Credentials

CryptoPanic API: Your API key.

HuggingFace API: Token for sentiment analysis.

SMTP Email Account: For sending the daily digest.

Ensure credentials are saved in n8n, otherwise the workflow will fail at the HTTP request or email steps.

4. Execute the Workflow
Manual Run

Open the workflow in n8n editor.

Click Execute Workflow → It will fetch the latest crypto news, analyze sentiment, predict impact, and send a test email.

Automated Run (Daily)

The workflow includes a Daily Trigger (Cron Node).

It runs automatically at the scheduled time (default: 00:30 IST).

Check Execution Logs in n8n to verify runs.
