⚡ ZYNBOX – Personal Productivity AI Agent
Team: Utkarsh Sharma · Zeeshan · Utkarsh Pandey
---
📦 INSTALLATION (run these commands once)
```bash
pip install streamlit scikit-learn gensim numpy
```
Or install from requirements.txt:
```bash
pip install -r requirements.txt
```
---
🚀 HOW TO RUN
```bash
streamlit run zynbox\_app.py
```
Then open your browser at: http://localhost:8501
---
🧠 PROJECT ARCHITECTURE (for viva)
```
User Input
    │
    ▼
NLP Pipeline (preprocess\_text)
    │  - Lowercase
    │  - Remove special characters
    │  - Tokenize
    │  - Remove stopwords
    │
    ▼
Vectorization
    ├── TF-IDF  (TfidfVectorizer from sklearn)
    └── Word2Vec (Gensim, then averaged to sentence vector)
    │
    ▼
Logistic Regression Classifiers
    ├── Intent Classifier  → what does user want? (add\_task, show\_tasks, greeting…)
    └── Mood Classifier    → how does user feel? (calm, study, creative, energy)
    │
    ▼
Hybrid Chatbot Engine
    ├── Rule-Based (if-else) → for exact commands like "add task: ..."
    └── ML-Based             → for flexible intent/mood detection
    │
    ▼
Response + Theme Engine
    ├── Theme switch based on detected mood
    └── Tone-adjusted reply
    │
    ▼
Streamlit UI (chat bubbles, sidebar, analysis panel)
```
---
🎯 FEATURES CHECKLIST
Feature	Status
Rule-based chatbot (if-else)	✅
Text preprocessing (NLP pipeline)	✅
TF-IDF vectorization	✅
Word2Vec vectorization (Gensim)	✅
Logistic Regression (intent)	✅
Logistic Regression (mood)	✅
Task Manager (add/show/delete/done)	✅
Tasks saved to JSON	✅
Model saved with pickle	✅
Smart Theme Engine (5 themes)	✅
Mood → Auto theme switch	✅
TF-IDF vs Word2Vec comparison	✅
Productivity score	✅
Chat bubbles UI	✅
Sidebar navigation	✅
Quick action buttons	✅
Motivational messages	✅
---
💬 EXAMPLE COMMANDS TO TRY
```
hello
help
add task: Complete NLP assignment
add task: Study for ML exam
show tasks
done task 1
delete task 2
I am tired
I want to study
I feel bored
I am motivated
```
---
📁 FILES GENERATED AT RUNTIME
`zynbox\_tasks.json` – your saved tasks
`zynbox\_models.pkl` – trained ML models (auto-created on first run)
---
🔑 KEY CONCEPTS USED (for exam)
If-Else Logic – Handles commands like "add task:", "show tasks", "delete task"
Text Preprocessing – Lowercase → remove punctuation → tokenize → stopword removal
TF-IDF – Converts text to frequency-weighted numerical vectors
Word2Vec – Gensim model learning word embeddings from context; sentences averaged
Logistic Regression – Trained on labeled intents and moods; predicts class probabilities
Pickle – Serializes trained models to disk, loads them on startup
JSON – Stores and retrieves task data persistently
Streamlit – Web UI framework; session_state tracks chat history and theme
