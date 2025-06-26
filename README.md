# 📚 RAG Application using LangChain, OpenAI API, and FAISS

This project demonstrates a **Retrieval-Augmented Generation (RAG)** application using:

* 🔗 [LangChain](https://docs.langchain.com/)
* 🤖 [OpenAI's GPT model](https://platform.openai.com/docs/)
* ⚡ [FAISS vector store](https://github.com/facebookresearch/faiss)

The system allows users to ask questions, and it responds with answers by retrieving relevant context from your documents using semantic search and generating responses via LLM.

---

## 🚀 Features

* 🔍 Embedding-based document retrieval using FAISS
* 🧠 Context-aware answer generation with OpenAI's GPT
* 🧾 Custom prompt template for accurate RAG
* 🧪 Modular and testable LangChain `Runnable` pipeline
* 🧵 Clean integration of `RunnablePassthrough`, prompt, LLM, and output parser

---

## 🛠️ Tech Stack

* **LangChain** for chaining the components
* **OpenAI API** for LLM responses (`gpt-3.5-turbo`, etc.)
* **FAISS** for fast, local vector similarity search
* **tiktoken** (optional) for token counting
* **Python 3.9+**

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your_username/RAG_Application_using_Langchain_OpenAI_API_and_FAISS.git
cd RAG_Application_using_Langchain_OpenAI_API_and_FAISS
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Add OpenAI API Key

Create a `.env` file:

```bash
OPENAI_API_KEY=your_openai_api_key_here
```

Or set it in the script directly:

```python
import os
os.environ["OPENAI_API_KEY"] = "your_openai_api_key_here"
```

### 4. Add Your Documents

Place `.txt`, `.pdf`, or `.docx` files in the `data/` folder.

---

## 🧪 Run the Application

```bash
python main.py
```

Example output:

```
User: What is LangChain used for?
> Retrieved context...
> Generated answer: "LangChain helps build apps powered by large language models."
```

---

## 🧩 Key Components Explained

| Component             | Description                                  |
| --------------------- | -------------------------------------------- |
| `retriever`           | Uses FAISS to fetch relevant document chunks |
| `RunnablePassthrough` | Passes user query unchanged                  |
| `ChatPromptTemplate`  | Formats question + context for the LLM       |
| `llm_model`           | Sends prompt to OpenAI and gets answer       |
| `output_parser`       | Cleans final output                          |

---

## 🧠 Example RAG Chain

```python
rag_chain = (
    {"context": retriever, "question": RunnablePassthrough()}
    | prompt
    | llm_model
    | output_parser
)
```

---

## 📦 Requirements

* Python 3.9+
* langchain
* openai
* faiss-cpu
* tiktoken
* python-dotenv

Add to `requirements.txt`:

```
langchain
openai
faiss-cpu
tiktoken
python-dotenv
```

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 🙋‍♂️ Acknowledgments

* [LangChain Docs](https://docs.langchain.com/)
* [OpenAI API Docs](https://platform.openai.com/docs/)
* [FAISS by Facebook Research](https://github.com/facebookresearch/faiss)
