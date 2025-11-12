# 🤖 Data Science Chatbot  

An **AI-powered conversational assistant** that answers **data science and Python interview questions** using NLP, semantic embeddings, and a Gradio-powered interface.  
It scrapes real-world questions from Analytics Vidhya, embeds them using **SentenceTransformers**, and retrieves the most relevant answers based on cosine similarity.  

---

## 📘 Project Overview  

This project builds an intelligent chatbot that can:
- 🧠 Understand user queries related to **data science**, **machine learning**, and **Python**  
- 💬 Provide accurate, contextually relevant answers  
- ⚙️ Run fully locally in a Jupyter Notebook or via a **Gradio web interface**

The chatbot uses **semantic search (embedding-based retrieval)** instead of keyword matching, providing intelligent and meaningful answers.

---

## 🧰 Tools & Technologies  

| Category | Tools / Libraries |
|-----------|-------------------|
| **Language** | Python 3.10 |
| **Web Scraping** | `requests`, `beautifulsoup4` |
| **NLP / Embeddings** | `sentence-transformers` (`paraphrase-MiniLM-L6-v2`) |
| **Utilities** | `numpy`, `pandas` |
| **Interface** | `gradio` |
| **Model** | `SentenceTransformer` (Hugging Face) |

---

## ⚙️ How It Works  

1. **Data Extraction** 🕸️  
   Scrapes 100+ data science questions and answers from [Analytics Vidhya’s blog](https://www.analyticsvidhya.com/blog/2023/01/top-100-data-science-interview-questions/) using `BeautifulSoup`.

2. **Embedding Generation** 🧩  
   Converts each question into a **semantic vector** using the `paraphrase-MiniLM-L6-v2` model.

3. **Similarity Matching** 📊  
   Compares user queries to existing questions using **cosine similarity** to find the most relevant answer.

4. **Interactive Response** 💬  
   Displays results in a **Gradio chatbot interface** that users can interact with locally or online.

---


---
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/95c9a1db-e79f-4c12-8096-27899296fcfd" />

## 🖼 Demo & Architecture

### 💬 Gradio Chatbot Interface
Below is a preview of the chatbot answering a data science question interactively through Gradio.

<p align="center">
  <img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/95c9a1db-e79f-4c12-8096-27899296fcfd" >
</p>

### 🧩 System Architecture
This diagram shows the complete flow — from scraping questions to embedding and delivering answers.

<p align="center">
 <img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/906fd80f-6c88-40b3-83f6-bab79f53a8f3" >
</p>

---

## 🧠 Example Interaction  

```text
👤 User: What is the central limit theorem?
🤖 Chatbot: The central limit theorem states that the sampling distribution of the sample mean approaches a normal distribution as the sample size increases, regardless of the population distribution.
👤 User: What is Python used for in data science?
🤖 Chatbot: Python is a versatile, high-level programming language widely used for data analysis, visualization, and machine learning due to its simplicity and rich ecosystem.

🖥️ Interface Preview

After running the notebook, Gradio launches a simple web interface:

Enter any data science or Python question

Get instant AI-driven responses

interface = gr.Interface(
    fn=chatbot,
    inputs="text",
    outputs="text",
    title="Data Science Chatbot",
    description="Ask me any data science-related question! The chatbot will try to provide the best answer."
)

interface.launch()


