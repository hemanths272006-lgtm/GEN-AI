# 🤖 Agentic AI Research Analyst

An **Agentic AI research and content-generation system** built using **CrewAI, Ollama, Qwen 2.5, and SerperDevTool**.

The project uses multiple AI agents working together in a sequential workflow:

**Research Analyst → Research & Verification → LinkedIn Writer → Final Blog Post**

---

## 📌 Project Overview

This project demonstrates how **Agentic AI** can automate the process of researching a topic and generating professional content.

The system accepts a topic such as:

> `AI in Hyderabad 2026`

It then:

1. Searches the web for recent information.
2. Identifies important trends and news.
3. Collects relevant statistics and sources.
4. Passes the research to another AI agent.
5. Generates a professional LinkedIn post.
6. Produces a final ready-to-publish result.

---

## 🧠 Is This Machine Learning or Generative AI?

This project is primarily **Generative AI / Agentic AI**.

### Why?

The notebook uses:

* **Ollama** for running a local Large Language Model
* **Qwen 2.5:7B Instruct** as the LLM
* **CrewAI** for creating and managing AI agents
* **SerperDevTool** for web search
* **Multiple AI agents** collaborating on a task
* **LLM-generated text** for the final LinkedIn post

Unlike traditional Machine Learning models that are trained to predict numerical or categorical outcomes, this project uses an LLM to **research, reason, and generate content**.

---

## 🏗️ Architecture

```text
                    USER TOPIC
                        │
                        ▼
              ┌──────────────────┐
              │  Research Analyst │
              │      Agent        │
              └────────┬─────────┘
                       │
                       ▼
                Serper Web Search
                       │
                       ▼
              Research & Statistics
                       │
                       ▼
              ┌──────────────────┐
              │  LinkedIn Writer  │
              │      Agent        │
              └────────┬─────────┘
                       │
                       ▼
                Qwen 2.5 LLM
                  via Ollama
                       │
                       ▼
             LinkedIn Blog Post
```

---

## 🛠️ Technologies Used

| Technology       | Purpose                 |
| ---------------- | ----------------------- |
| Python           | Programming language    |
| CrewAI           | AI agent orchestration  |
| Ollama           | Local LLM execution     |
| Qwen 2.5 7B      | Language model          |
| SerperDevTool    | Web search              |
| CrewAI Tools     | Agent tools             |
| Jupyter Notebook | Development environment |

---

## 🤖 AI Agents

### 1. Research Analyst

**Role:** Research Analyst

The Research Analyst is responsible for finding recent information about the given topic.

Its objectives include:

* Finding the latest developments
* Identifying key trends
* Finding important news
* Collecting statistics
* Verifying information using web search
* Providing sources

The agent uses `SerperDevTool` to search the web.

---

### 2. LinkedIn Writer

**Role:** LinkedIn Writer

The LinkedIn Writer receives the research produced by the Research Analyst and generates a professional LinkedIn post.

The generated content follows this structure:

```text
Hook
   ↓
3 Key Insights
   ↓
What it means for professionals
   ↓
Call to Action
   ↓
Hashtags
```

The target output is approximately **400 words**.

---

## 🔄 Workflow

### Step 1 — Install Dependencies

The notebook installs:

```bash
pip install crewai crewai-tools
```

### Step 2 — Configure Ollama

The project uses a local Ollama server:

```text
http://localhost:11434
```

The selected model is:

```text
ollama/qwen2.5:7b-instruct
```

### Step 3 — Configure Web Search

The project uses:

```text
SerperDevTool
```

to retrieve recent information from the web.

### Step 4 — Create AI Agents

Two agents are created:

```text
Research Analyst
        ↓
LinkedIn Writer
```

### Step 5 — Create Tasks

The Research Analyst performs research while the LinkedIn Writer uses the research as context.

### Step 6 — Run the Crew

The CrewAI workflow executes the tasks sequentially.

```python
process=Process.sequential
```

### Step 7 — Generate Final Output

The final result is a LinkedIn-ready blog post.

---

## 📊 Example Topic

The notebook currently uses:

```python
topic = "AI in Hyderabad 2026"
```

The system can be adapted to other topics such as:

```text
Generative AI in India
AI Startups in Bengaluru
Future of Cloud Computing
Cybersecurity Trends 2026
AI in Healthcare
Future of Software Development
```

---

## 📂 Project Structure

```text
Agentic-AI-Research-Analyst/
│
├── Agentic AI Research analyst I(1).ipynb
└── README.md
```

---

## ⚙️ Requirements

Before running the notebook, make sure you have:

* Python 3.9+
* Ollama
* Qwen 2.5 model
* CrewAI
* CrewAI Tools
* Serper API key
* Jupyter Notebook or Google Colab environment

---

## 🚀 How to Run

### 1. Install Ollama

Install Ollama on your system and verify:

```bash
ollama --version
```

### 2. Download the LLM

Pull the Qwen model:

```bash
ollama pull qwen2.5:7b-instruct
```

### 3. Install Python Packages

```bash
pip install crewai crewai-tools
```

### 4. Add Your Serper API Key

Set your API key as an environment variable:

```python
os.environ["SERPER_API_KEY"] = "YOUR_SERPER_API_KEY"
```

**Do not upload your real API key to GitHub.**

### 5. Start Ollama

Make sure the Ollama service is running locally.

### 6. Open the Notebook

Open:

```text
Agentic AI Research analyst I(1).ipynb
```

### 7. Change the Topic

Modify:

```python
topic = "AI in Hyderabad 2026"
```

For example:

```python
topic = "Generative AI Trends in India 2026"
```

### 8. Run the Notebook

Execute the cells sequentially.

The final generated content will appear under:

```text
### FINAL BLOG POST ###
```

---

## 🔐 Security Note

Never commit API keys or other credentials to GitHub.

Instead of:

```python
os.environ["SERPER_API_KEY"] = "actual-api-key"
```

use an environment variable or `.env` file that is included in `.gitignore`.

Example:

```text
SERPER_API_KEY=your_api_key_here
```

Add `.env` to:

```text
.gitignore
```

---

## 🎯 Key Learning Outcomes

Through this project, you can learn:

* What Agentic AI is
* How AI agents work
* Multi-agent workflows
* CrewAI framework
* LLM integration with Ollama
* Local LLM execution
* Web search integration
* Task orchestration
* Sequential agent execution
* Context sharing between agents
* AI-generated content
* Prompt and agent design

---

## 🌟 Future Improvements

The project can be extended with:

* 🔎 More web search sources
* 🧠 Additional specialized agents
* 📄 PDF/document research
* 🗃️ RAG integration
* 💾 Database storage
* 🌐 React frontend
* ⚡ FastAPI backend
* 📊 Research dashboard
* 📝 Automatic report generation
* 🔗 Automatic source/citation management
* 📧 Email delivery of generated reports

---

## 💡 Future Multi-Agent Architecture

A more advanced version could contain:

```text
                 User Topic
                     │
                     ▼
             ┌───────────────┐
             │ Research Agent │
             └───────┬───────┘
                     │
          ┌──────────┼──────────┐
          ▼          ▼          ▼
       News Agent  Data Agent  Trend Agent
          │          │          │
          └──────────┼──────────┘
                     ▼
              Fact Checker
                     │
                     ▼
               Content Writer
                     │
                     ▼
                Final Report
```

This would make the system more capable of performing complex research tasks autonomously.

---

## 👨‍💻 Author

**Hemanth S**

BE CSE (AI & ML)

---

## ⭐ Project Type

**Generative AI | Agentic AI | Multi-Agent Systems | LLM Application**

If you found this project useful, consider giving the repository a ⭐.
