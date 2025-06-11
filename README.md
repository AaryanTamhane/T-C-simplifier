
# 📄 T&C Summarizer Chrome Extension - README

## 🚀 Project Overview
This Chrome extension automatically detects and extracts Terms & Conditions (T&C) or Privacy Policy text from web pages. It then sends the extracted content to an AI model (like GPT-4-turbo) for summarization and returns a quick, user-friendly summary — highlighting any potential risks or critical clauses. This tool is especially useful for users and professionals who frequently interact with online services and need to make fast yet informed decisions.

## 🎯 Final Year Project Purpose
- Demonstrate integration of AI/LLM APIs with browser environments
- Build a real-world tool that solves a common problem
- Learn full-stack concepts (frontend, backend, ML/NLP APIs, deployment)

## 📌 Features
- Detects and reads visible Terms and Conditions from web pages
- Sends text to an LLM (OpenAI GPT-4-turbo or equivalent)
- Displays a short summary and flags risky clauses
- Runs in a browser popup for seamless user experience

## 🧰 Tech Stack
- **HTML, CSS, JS** — For Chrome extension UI and logic
- **Manifest v3** — For extension configuration
- **JavaScript DOM manipulation** — For extracting visible text
- **OpenAI API** — For AI-powered summarization
- **Chunking and filtering** — To manage long T&C documents

## 🏁 How It Works
1. **Content Script** detects if a page has T&C-related keywords ("terms", "conditions", etc.)
2. Extracts text from visible HTML elements
3. Filters unnecessary content, splits long texts into chunks
4. Sends top-priority text chunks to the API with a summarization prompt
5. Receives and displays the summary + risk analysis in the popup

## 📂 Folder Structure
```
TnC-Summarizer/
├── manifest.json
├── popup.html
├── popup.css
├── popup.js
├── contentScript.js
├── background.js (optional)
├── icons/
└── utils/
    └── extractor.js
```

## 📈 Future Improvements
- ✅ Risk scoring with traffic-light system (green/yellow/red)
- 🔄 Language support beyond English
- 🔍 Search or filter clauses by keyword
- 📦 Bundle with privacy policy summarizer

## 📎 References
- [OpenAI API Docs](https://platform.openai.com/docs)
- [Chrome Extension Docs](https://developer.chrome.com/docs/extensions/)
- [Stanford MCC Dataset](https://mcc.law.stanford.edu/)
- [Existing Extensions Study](https://chromewebstore.google.com/)

## 🙌 Acknowledgements
This project is part of the final-year B.Tech degree coursework. The goal is learning, exploration, and building a deployable tool that leverages LLMs for real-world browser-based applications.

> For questions, collaboration, or improvements, feel free to contribute!
