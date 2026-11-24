📌 Project Title
----------------

# AI-ENGINERING-PROJECT-FEEDBACK-ANALYSIS
I made  AI ENGIINERING about  a Feedback Analysis of AI Agents

📌 Project About
----------------

This Project mean by User transmited demands and present with Google Gemini API response basic but more high dimision agent.

Backend: FastAPI with REST API
AI: Google Gen AI SDK (Gemini)
Data Confirmation: Pydantic models
Interface: Streamlit subquery chat screen 
Structure: .env files with hidden keys management 

📌 Project Structure
--------------------
ai-agent/
├── app/
│   ├── __init__.py
│   ├── main.py          # FastAPI applications and endpoints
│   ├── agent.py         # With Gemini establish community logic of agent
│   ├── schemas.py       # Pydantic demain and response modelsi
│   └── config.py        # Valueble of Atmospher load
├── ui/
│   └── app.py           # Streamlit interface
├── .env.example         # For example valuable of atmospher
├── .gitignore
├── requirements.txt
└── README.md

📌 Project Library
-------------------
fastapi	0.162.7
google-genai	2.19.0	Gemini modellerine erişim
pydantic	2.14.0	Veri doğrulama ve şemalar
python-dotenv	1.2.2	.env dosyasından ortam değişkeni
requests	2.34.2	Harici HTTP istekleri
streamlit	1.67.0	Web arayüzü
