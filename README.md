# LLM Recommender System

An end-to-end **LLM recommendation engine** built using real-world Reddit discussions.  
Instead of relying on benchmarks or vendor claims, this system analyzes **authentic user sentiment** to recommend the most suitable large language model—such as ChatGPT, Claude, or Gemini—for a specific task.

By converting unstructured social media conversations into a structured knowledge base, the project enables **task-aware, sentiment-driven LLM recommendations** through semantic search.

---

## 📌 Objective

- Identify which LLM performs best for a given **use case** (e.g., coding, debugging, content creation)
- Base recommendations on **real user experiences**, not synthetic evaluations
- Provide an **interactive, explainable recommender** powered by NLP and transformers

---

## 📊 Dataset

- **Source**: Reddit (LLM-focused subreddits)
- **Volume**: 2,440 raw posts
- **Content**: User opinions, complaints, comparisons, and use cases related to popular LLMs

---

## 🏗️ System Architecture

The project follows a **modular, multi-stage NLP pipeline**, implemented across five Jupyter notebooks.

---

## 🔍 Pipeline Overview

### 1. Topic Modeling (`Topic Modeling.ipynb`)
- Uses **BERTopic** to cluster all Reddit posts
- Extracts **10 interpretable discussion topics**, such as:
  - Coding & development use cases  
  - Content moderation and safety filters  
- Enables semantic alignment between user queries and discussion themes

---

### 2. Sentiment Analysis (`Sentiment Analysis.ipynb`)
- Applies a **RoBERTa-based transformer** fine-tuned for social media text
- Classifies each post as:
  - Positive  
  - Negative  
  - Neutral  
- Captures nuanced, informal sentiment from real user language

---

### 3. Named Entity Recognition (`NER.ipynb`)
- Identifies which LLM is referenced in each post
- Approach:
  - **Regex matching** for explicit mentions (e.g., GPT-4o, Grok)
  - **Subreddit-based inference** when mentions are implicit  
    - Example: posts from `r/ClaudeAI` → tagged as *Claude*
- Ensures every post is mapped to a specific LLM

---

### 4. Knowledge Base Construction (`Knowledge Base.ipynb`)
- Merges topic labels, sentiment scores, and LLM identifiers
- Aggregates sentiment at the **LLM × Topic** level
- Computes a **Positive Experience Score**:



