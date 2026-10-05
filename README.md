# 🐝 Research Hive AI — Multi-Agent AI Research Assistant

**Agentic AI · LangChain · Mistral AI · Tavily · Web Research · LLMs**

## 📌 Overview

**Research Hive AI** is a multi-agent AI research assistant that automates web research, content extraction, report generation, and report evaluation.

The system coordinates specialized AI agents in a sequential pipeline:

**🔎 Search → 📖 Read → ✍️ Write → 🧐 Review**

Given a research topic, the system searches for recent information, reads relevant web content, generates a structured research report, and uses a critic chain to evaluate the final response.

## 🧠 Multi-Agent Architecture

| Component | Responsibility |
| --- | --- |
| 🔎 **Search Agent** | Searches for recent and reliable information using Tavily |
| 📖 **Reader Agent** | Selects relevant sources and extracts useful web content |
| ✍️ **Writer Chain** | Converts gathered research into a structured professional report |
| 🧐 **Critic Chain** | Reviews the generated report, provides a score, strengths, weaknesses, and verdict |

## ⚙️ AI Pipeline

```text
User Research Topic
        ↓
   🔎 Search Agent
        ↓
 Tavily Web Search
        ↓
   📖 Reader Agent
        ↓
 Web Content Extraction
        ↓
   ✍️ Writer Chain
        ↓
 Structured Research Report
        ↓
   🧐 Critic Chain
        ↓
 Score + Feedback + Verdict
```

The pipeline maintains the outputs of each stage and passes relevant context to the next component, enabling specialized agents to collaborate on one research task.

## 🤖 LLM

The project uses:

**Mistral AI — `mistral-small-latest`**

The model powers the Search Agent, Reader Agent, Writer Chain, and Critic Chain through LangChain.

## 🔍 Search & Retrieval

The Search Agent uses **Tavily** to retrieve up to five recent search results containing:

- Source titles
- URLs
- Search snippets

The Reader Agent then identifies a relevant source and extracts clean textual content for deeper analysis.

## ✍️ Research Report Generation

The Writer Chain combines search results and extracted web content to generate a structured report containing:

1. **Introduction**
2. **Key Findings**
3. **Conclusion**
4. **Sources**

This separation between research gathering and report generation creates a modular agentic workflow.

## 🧐 AI Critic & Evaluation

After report generation, a dedicated **Critic Chain** evaluates the output and returns:

- **Score out of 10**
- **Strengths**
- **Areas to Improve**
- **One-line verdict**

This adds an automated review layer to the research workflow instead of returning the first generated response directly.

## 🛠️ Tech Stack

**Programming:** Python  
**Agent Framework:** LangChain  
**LLM:** Mistral AI (`mistral-small-latest`)  
**Web Search:** Tavily  
**Web Content Extraction:** BeautifulSoup, Requests  
**Environment Management:** python-dotenv  
**Interface:** Streamlit

## 📁 Project Structure

```text
Research-Hive-AI/
│
├── agents.py          # Search/Reader agents and Writer/Critic chains
├── pipeline.py        # Multi-agent research orchestration
├── tools.py           # Tavily search and web scraping tools
├── app.py             # User interface
├── requirements.txt   # Python dependencies
└── README.md
```

## 🚀 Installation

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd Research-Hive-AI
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

**macOS/Linux**
```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project directory:

```env
MISTRAL_API_KEY=your_mistral_api_key
TAVILY_API_KEY=your_tavily_api_key
```

> Never commit your `.env` file or API keys to GitHub.

## ▶️ Run the Project

Run the research pipeline from the command line:

```bash
python pipeline.py
```

Or launch the interface:

```bash
streamlit run app.py
```

Enter a research topic and the agents will execute the complete research workflow.

## 💡 Skills Demonstrated

- Agentic AI
- Multi-Agent Systems
- Large Language Models (LLMs)
- LangChain Agents
- Prompt Engineering
- AI Workflow Orchestration
- Tool-Calling Agents
- Web Search & Information Retrieval
- Automated Research
- LLM-based Report Generation
- AI Output Evaluation
- Python

## 🎯 Project Outcome

**Research Hive AI** demonstrates an end-to-end **Agentic AI and multi-agent workflow** where specialized agents independently handle information discovery, content extraction, report generation, and quality review.

The project showcases how **LangChain, Mistral AI, Tavily, and custom tools** can be orchestrated to build an automated AI research system with an integrated critic and evaluation stage.
