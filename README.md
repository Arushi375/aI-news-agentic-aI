# 📰 AI News Agentic Researcher

An **agentic AI news research and summarization system** built with **LangGraph, LangChain, Groq, Tavily, and Streamlit**.

The application retrieves recent Artificial Intelligence news from the web, processes the retrieved articles using an LLM, generates concise date-sorted summaries with source links, and saves the results as Markdown reports.

---

## ✨ Features

- 🔎 **Web-based AI news retrieval** using Tavily
- 🤖 **LLM-powered summarization** using Groq
- 🧩 **LangGraph-based workflow orchestration**
- 📅 Supports multiple reporting periods:
  - Daily
  - Weekly
  - Monthly
  - Yearly
- 📝 Generates structured Markdown reports
- 🔗 Preserves source URLs for each news item
- 🌐 Streamlit-based interactive interface
- 🏗️ Modular project architecture separating:
  - Graph orchestration
  - LLM configuration
  - Tools
  - Nodes
  - State
  - UI

---

## 🧠 How It Works

The application follows a sequential LangGraph workflow:

```text
                    ┌─────────────────┐
                    │   User selects  │
                    │   time period   │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   Fetch News    │
                    │     Tavily      │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Summarize News  │
                    │    Groq LLM     │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   Save Result   │
                    │   Markdown File │
                    └────────┬────────┘
                             │
                             ▼
                           END
```

### Workflow

1. The user selects a reporting frequency.
2. The system queries Tavily for recent AI-related news.
3. Retrieved articles are passed to the LLM.
4. The LLM:
   - Summarizes each article.
   - Organizes articles by date.
   - Places the newest articles first.
   - Includes the original source URL.
5. The generated report is saved as a Markdown file.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Python** | Core application |
| **LangGraph** | Workflow and state orchestration |
| **LangChain** | LLM integration and prompting |
| **Groq** | LLM inference |
| **Tavily** | Web/news search |
| **Streamlit** | User interface |
| **Markdown** | Generated reports |

---

## 📂 Project Structure

```text
AINEWSAgentic/
│
├── AINews/
│   ├── daily_summary.md
│   ├── weekly_summary.md
│   └── monthly_summary.md
│
├── src/
│   └── langgraphagenticai/
│       │
│       ├── graph/
│       │   └── graph_builder.py
│       │
│       ├── LLMS/
│       │   └── groqllm.py
│       │
│       ├── nodes/
│       │   ├── ai_news_node.py
│       │   ├── basic_chatbot_node.py
│       │   └── chatbot_with_Tool_node.py
│       │
│       ├── state/
│       │   └── state.py
│       │
│       ├── tools/
│       │   └── search_tool.py
│       │
│       └── ui/
│           └── streamlitui/
│
├── app.py
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd AINEWSAgentic
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it:

**Windows**

```bash
venv\Scripts\activate
```

**macOS / Linux**

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Environment Variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
TAVILY_API_KEY=your_tavily_api_key
```

Never commit API keys to GitHub.

Add `.env` to `.gitignore`:

```text
.env
```

---

## ▶️ Running the Application

Start the Streamlit application:

```bash
streamlit run app.py
```

Then open the local Streamlit URL displayed in your terminal.

---

## 📄 Example Output

Generated reports are stored in the `AINews/` directory.

Example:

```text
AINews/
├── daily_summary.md
├── weekly_summary.md
└── monthly_summary.md
```

Example report format:

```markdown
# Daily AI News Summary

### 2026-10-04

- Summary of the latest AI development...
  [Source](https://example.com/article)

### 2026-10-03

- Summary of another AI development...
  [Source](https://example.com/article)
```

---

## 🧩 LangGraph Architecture

The application represents the news-processing pipeline as a graph:

```text
START
  │
  ▼
fetch_news
  │
  ▼
summarize_news
  │
  ▼
save_result
  │
  ▼
 END
```

Each node has a specific responsibility:

### `fetch_news`

Retrieves recent AI news using Tavily based on the selected time range.

### `summarize_news`

Passes retrieved article content to the Groq LLM and generates structured summaries.

### `save_result`

Persists the generated report as a Markdown file.

This separation makes the workflow easier to extend with additional processing or validation steps.

---

## 🚀 Future Improvements

Potential extensions include:

- [ ] Add source credibility filtering
- [ ] Add duplicate article detection
- [ ] Add article categorization
- [ ] Add sentiment analysis
- [ ] Add database persistence
- [ ] Add email/newsletter delivery
- [ ] Add scheduled automated reports
- [ ] Add multi-agent research and verification
- [ ] Add evaluation of generated summaries
- [ ] Add configurable news sources and domains

---

## 🎯 Learning Outcomes

This project demonstrates practical experience with:

- Agentic AI workflows
- LangGraph state graphs
- LLM orchestration
- Tool/API integration
- Prompt engineering
- Web-grounded AI applications
- Structured output generation
- Modular Python architecture
- Streamlit application development

---

## 👩‍💻 Author

**Arushi Kumari**

Interested in **Artificial Intelligence, Machine Learning, Generative AI, and Agentic AI**.
