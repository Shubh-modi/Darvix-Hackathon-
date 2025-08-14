# Darvix-Hackathon-
Name- Shubh Modi
Email- shubhmdi111@gmail.com

# Project README

## 📌 Overview
This project appears to be a **Streamlit-based application** with a backend Python service for generating responses and referencing a knowledge base for feedback and style guidelines.

The repository contains:
- **`streamlit_app.py`**: The main Streamlit UI application.
- **`main.py`**: Likely the application entry point.
- **`backend/generator.py`**: Core logic for text generation or feedback processing.
- **`kb/`**: Knowledge base containing style and PEP8 guidelines.
- **`.env`**: Stores environment variables including API keys.
- **`requirements.txt`**: Python dependencies.

---

## 🛠 Setup Instructions

### 1️⃣ Clone the repository
```bash
git clone <your-repo-url>
cd <repo-folder>
```

### 2️⃣ Create and activate a virtual environment
```bash
python -m venv venv
source venv/bin/activate   # On macOS/Linux
venv\Scripts\activate    # On Windows
```

### 3️⃣ Install dependencies
```bash
pip install -r requirements.txt
```

### 4️⃣ Set up environment variables
Create a `.env` file in the root directory and add:
```
API_KEY=<your-api-key-here>
OTHER_CONFIG=<other-config-if-any>
```

### 5️⃣ Run the application
```bash
streamlit run streamlit_app.py
```

---

## 📋 Testing the Application
1. Ensure your `.env` file is properly configured with any required API keys.
2. Start the app using `streamlit run streamlit_app.py`.
3. Open the provided **localhost URL** in your browser.
4. Interact with the application UI and verify functionality.

---

## 💡 Approach Used
The approach for solving the problem includes:
- **Streamlit Frontend** for interactive UI.
- **Backend Python logic** in `backend/generator.py` for processing text and generating results.
- **Knowledge Base (`kb/`)** containing feedback and style guidelines.
- **FAISS index (`.kb_index/`)** for fast retrieval of relevant information.
- **Environment variables (`.env`)** for sensitive data handling.

---

## 🔑 API Key Details
- API keys are stored in the `.env` file and **not** committed to version control.
- Ensure you create your own `.env` file before running the application.
- The `.env` file format is:
```
API_KEY=your_key_here
```
This key might be required for API calls in `generator.py` or other modules.

---


