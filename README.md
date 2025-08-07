# Atomberg-Smart-Fan-Analysis

An AI-powered multi-agent system designed to analyze the market presence of **Atomberg Technologies** in the smart fan category. This system collects data from Google and YouTube, calculates Share of Voice (SOV) metrics, performs sentiment analysis, and generates strategic recommendations for marketing and content teams.

The project was developed as part of the AI Internship program, demonstrating proficiency in AI agent development, local LLM integration, and data-driven market analysis.

## Key Features

- **Multi-Platform Data Collection**: Gathers real-time data from YouTube (videos) and Google Search (web results).
- **Advanced SOV Analysis**: Calculates Share of Voice based on brand mentions, sentiment, and engagement potential.
- **Share of Positive Voice**: Performs sentiment analysis to identify the share of positive brand conversations.
- **Autonomous AI Agents**: Utilizes the CrewAI framework with specialized agents for data collection, analysis, and strategy.
- **Local & Private AI**: Powered by Ollama and Llama 3.2:1B, ensuring all data processing is done locally for complete privacy and cost-efficiency.
- **Comprehensive Reporting**: Automatically generates a suite of analysis files, including:
    - 📊 A visual dashboard (`.png`)
    - 📈 A detailed metrics report (`.csv`)
    - 🧠 AI-generated insights (`.json`)
    - 📋 A summary report (`.txt`)
- **Actionable Recommendations**: Provides data-driven strategic recommendations for Atomberg's content and marketing teams.

## Tech Stack

The system is built on a modern, privacy-focused AI and data analysis stack:

| Component             | Technology                                                              | Purpose                                                                |
| --------------------- | ----------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| **AI Agent Framework**  | [CrewAI](https://www.crewai.com/)                                       | To orchestrate specialized AI agents for a sequential workflow.        |
| **Local LLM**           | [Ollama](https://ollama.com/) (Llama 3.2:1B)                            | For local, private, and cost-free AI reasoning and analysis.           |
| **Data Collection**     | Google APIs (`youtube-v3`, `customsearch-v1`)                           | To access public data from YouTube and Google Search reliably.         |
| **Core Language**       | Python 3.9+                                                             | The primary language for development.                                  |
| **Data Handling**       | [Pandas](https://pandas.pydata.org/)                                    | For data manipulation and creating structured metrics reports.         |
| **Visualization**       | [Matplotlib](https://matplotlib.org/)                                   | To generate visual charts and dashboards for easy interpretation.      |
| **LLM Integration**     | [LangChain](https://www.langchain.com/) (`langchain-ollama`)            | To connect CrewAI with the local Ollama LLM.                           |

## System Architecture & Workflow

The system operates through a sequential workflow managed by CrewAI, where each agent performs a specific task and passes its output to the next.

1.  **Keyword Input**: The process starts with a predefined list of strategic keywords (e.g., "smart fan India", "ceiling fan BLDC").
2.  **Data Collection Agent**:
    - For each keyword, this agent executes the `YouTubeSearchTool` and `GoogleSearchTool`.
    - It collects the top N results from each platform (N=15 for YouTube, N=10 for Google).
    - All collected data is aggregated into a single JSON dataset.
3.  **SOV Analysis Agent**:
    - Receives the collected data from the previous agent.
    - Executes the `SOVAnalyzer` tool to process the text content.
    - It counts brand mentions, calculates sentiment scores, and quantifies Share of Voice metrics.
4.  **Marketing Strategy Agent**:
    - Receives the structured analysis from the SOV Analyst.
    - Generates actionable recommendations, content strategies, and competitive insights based on real data.
5.  **Final Output Generation**: The main script takes the final output and generates the multi-format report files (PNG, CSV, JSON, TXT).

## Setup and Installation

Follow these steps to set up and run the project locally.

### 1. Prerequisites
- [Python 3.9](https://www.python.org/downloads/) or higher
- [Git](https://git-scm.com/)
- [Ollama](https://ollama.com/) is installed and running on your system.

### 2. Install Ollama and Pull the Model
First, ensure the Ollama server is running. Then, pull the required LLM:
