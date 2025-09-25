# Real-Time Market Sentiment Analyzer 📈

This project is a Python-based pipeline that analyzes real-time market sentiment for a given company. It uses LangChain to orchestrate a series of steps: fetching a stock code, searching for recent news, and using Google's Gemini-1.5-Flash model to generate a structured JSON sentiment profile. The entire process is monitored and traced using MLflow.

## ✨ Features

-   **Dynamic Stock Code Extraction**: Automatically finds the stock ticker for a company.
-   **Real-Time News Fetching**: Uses the Exa Search API to gather the latest financial news.
-   **AI-Powered Sentiment Analysis**: Leverages Google's Gemini LLM for nuanced sentiment classification and entity extraction.
-   **Structured JSON Output**: Guarantees a clean, predictable JSON output for easy integration.
-   **End-to-End Observability**: Integrates with MLflow for comprehensive tracing, prompt debugging, and monitoring of the entire chain.

## 🛠️ Tech Stack & Tools

-   **Framework**: LangChain
-   **LLM**: Google Gemini-1.5-Flash (via Vertex AI)
-   **Data Source**: Exa Search API
-   **Observability**: MLflow
-   **Core Language**: Python 3.10+

## 🚀 Getting Started

Follow these steps to set up and run the sentiment analyzer on my local machine.

### 1. Prerequisites

-   Python 3.10 or higher.
-   A Google Cloud Project with the Vertex AI API enabled.
-   An API Key from [Exa Search](https://exa.ai/).
-   `git` installed on my system.

### 2. Setup Instructions

**a. Clone the Repository**
```bash
git clone <repository_url>
cd <repository_directory>


### Create and Activate a Virtual Environment **

# For Unix/macOS
python3 -m venv venv
source venv/bin/activate

# For Windows
python -m venv venv
.\venv\Scripts\activate

# Install Dependencies
pip install -r requirements.txt

## Configure Environment Variables
# .env
# Google Cloud Configuration
GCP_PROJECT_ID="My-gcp-project-id"
GCP_LOCATION="us-central1" # e.g., us-central1

# Exa Search API Key
EXA_API_KEY="My-exa-api-key"

gcloud auth application-default login

# Start the MLflow Tracking Server
mlflow ui

# Run the Python Script
python sentiment_analyzer.py --company "Google"