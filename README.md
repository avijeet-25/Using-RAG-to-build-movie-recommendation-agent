AI Movie Recommendation Agent: High-Scale RAG Pipeline

A production-ready recommendation system leveraging Retrieval-Augmented Generation (RAG) and Agentic Workflows to provide grounded, context-aware movie suggestions. This project focuses on optimizing retrieval quality and latency when handling high-volume datasets (45,000+ records).

🚀 Overview
Traditional recommendation engines often rely on collaborative filtering or simple metadata matching. This project evolves that approach by using an LLM-powered agent to "understand" user intent and a RAG pipeline to retrieve relevant movie context from a massive vector database.

Key Engineering Challenges Solved:
Scalability: Efficiently querying and managing a vector store with 45,000+ movie records.

Retrieval Precision: Implementing optimized chunking and embedding strategies to reduce "noise" in the retrieved context.

Hallucination Mitigation: Using the RAG Triad (Faithfulness, Relevancy, and Contextual Precision) to ensure recommendations are strictly grounded in the dataset.

🛠️ Tech Stack
Orchestration: LangChain / LangGraph

LLM: Mistral 7B instruct v0.1

Vector Database: ChromaDB 

Data Processing: Pandas, NumPy, Scikit-learn

Evaluation: DeepEval / LangSmith (Tracing)

🏗️ Architecture
The system operates through a decoupled multi-stage pipeline:

Query Transformation: The agent re-writes the user's natural language request into a query optimized for vector search.

Vector Retrieval: A semantic search is performed against 45k+ movie embeddings using Cosine Similarity.

Context Injection: The top-K relevant movie metadata (genres, plot summaries, cast) is injected into the prompt.

Grounded Generation: The LLM generates a personalized recommendation with specific justifications based only on the retrieved context.

🌟 Key Features
Semantic Search vs. Keyword Search: Understands complex user requests like "Movies that feel like a rainy afternoon in Paris" rather than just searching for "Paris" or "Rain."

High-Volume Data Handling: Optimized for low-latency retrieval across a large-scale dataset.

Agentic Reasoning: Can handle multi-turn conversations, refining recommendations based on follow-up feedback.

Evaluation Suite: Includes scripts to measure retrieval recall and answer faithfulness.

📥 Installation & Setup

Clone the repository:

Bash
git clone https://github.com/avijeet-25/Using-RAG-to-build-movie-recommendation-agent.git

cd Using-RAG-to-build-movie-recommendation-agent


Create a virtual environment:

Bash
python -m venv venv
source venv/bin/activate     # On Windows: venv\Scripts\activate

Install dependencies:

Bash
pip install -r requirements.txt

📈 Future Roadmap

[ ] Hybrid Search: Integrating BM25 keyword matching with semantic vector search for better "niche" title retrieval.

[ ] Memory Persistence: Adding a PostgreSQL layer to remember user preferences across sessions.

[ ] Advanced Evaluation: Integrating CI/CD unit tests using DeepEval to prevent hallucination regressions.

🤝 Contributions
This project is open-source. As a contributor to the Bindu framework, I value modular and well-documented code. Feel free to open an issue or submit a pull request!

