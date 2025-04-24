# Call-Analysis-Backend
Call Transcription Analyzer with Groq LLM This project automates the analysis of phone call transcriptions using Groq’s LLaMA-3 model, combined with MongoDB for data storage and Sentence Transformers for future embedding capabilities. It's designed to fetch call data, extract insights via LLM, and store processed summaries back to a MongoDB.


# 📞 LLM-Based Call Transcription Analyzer

This project processes phone call transcriptions stored in MongoDB using a Large Language Model (Groq’s LLaMA-3 via Langchain) to extract insights such as:

- 📋 **Summary** of the conversation  
- 🧠 **Entities** (Name, Location, Phone, Age, DOB)  
- ⏰ **Reschedule Time** detection  
- 😊 **Sentiment analysis**  
- 💬 **Customer interest level**

Results are written back to the same MongoDB collection for enriched record-keeping.

---

## 🔧 Features

- Multi-threaded transcription processing 🚀
- Robust error handling & retry logic 🔄
- Structured logging 📜
- Auto-handling of malformed JSON from LLM
- Process tracking to avoid duplicate work ✅

---

## 📂 Folder Structure

📁 your_project/ ├── data/ # Contains .txt transcription files (optional) ├── processed_llm_files.txt # Tracks processed files ├── main.py # Core logic ├── .env # Stores your API keys ├── requirements.txt # Python dependencies └── README.md

---

## 🧪 Environment Variables (`.env`)

GROQ_API_KEY=your_groq_api_key

---

## 📦 Installation

```bash
git clone https://github.com/yourusername/call-transcription-llm.git
cd call-transcription-llm
python -m venv venv
source venv/bin/activate   # or venv\Scripts\activate on Windows
pip install -r requirements.txt
🚀 Run the Script
Make sure your MongoDB collection has transcriptions ("transcription" field in each doc):

bash
python main.py
🔐 MongoDB Notes
Ensure MongoDB URI is updated inside main.py:

python
MONGO_URI= os.getenv("MONGO_URI")
MONGO_DB = "CallAnalysis"
MONGO_COLLECTION = "phone_records"

## 📸 Example Output

Here is an example of the output you can expect from the API:

![Output Example](Call Analysis.png)
