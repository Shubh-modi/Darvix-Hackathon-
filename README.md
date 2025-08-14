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


## Approach  

### Objective  
To create an AI system that rewrites technical feedback in a friendly, mentor-like tone, while still maintaining the technical depth and providing actionable improvement steps.

---

### Technologies & APIs Used  
- **Groq LLaMA 3 API** – Core large language model used to rephrase review comments empathetically.  
  - API Key: Stored securely in environment variables during development (`gsk_********`).
- **LangChain** – Used for prompt creation, chaining review processing steps, and structured response formatting.
- **HuggingFace Embeddings** – Provides semantic embeddings of code and comments to enhance context-awareness.
- **Streamlit** – User interface for uploading JSON data and viewing generated empathetic feedback.

---

### Detailed Steps  

1. **Input Collection**  
   - Accepts JSON input in the following format:
     ```json
     {
       "code_snippet": "def get_active_users(users):\n results = []\n for u in users:\n if u.is_active == True and u.profile_complete == True:\n results.append(u)\n return results",
       "review_comments": [
         "This is inefficient. Don't loop twice conceptually.",
         "Variable 'u' is a bad name.",
         "Boolean comparison '== True' is redundant."
       ]
     }
     ```

2. **Prompt Engineering**  
   - Designed a LangChain `PromptTemplate` that:
     - Includes the original code snippet.
     - Passes each review comment separately.
     - Requests the model to produce:
       - Positive rephrasing.
       - The underlying reason (“why”).
       - Specific improvement suggestions.
       - Example code corrections.
       - Optional reference links.

3. **Model Processing**  
   - Groq LLaMA 3 model is queried through the API.  
   - HuggingFace embeddings help preserve semantic closeness between comments and code context.

4. **Output Formatting**  
   - Each comment’s response is formatted into Markdown:
     - Original comment.
     - Positive rewording.
     - Explanation.
     - Suggested improvement (code block).
   - All responses combined into a downloadable `.md` report.

5. **User Interface**  
   - Built using Streamlit:
     - Paste or upload JSON.
     - Click “Generate” to get empathetic review.
     - Download the report.


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

## Overview  
The Empathetic Code Reviewer is an AI-powered tool that transforms raw, harsh, or overly direct code review comments into **empathetic, constructive, and educational feedback**.  
Its purpose is to improve developer communication, reduce tension in code reviews, and help engineers grow through clear and supportive suggestions.

---


