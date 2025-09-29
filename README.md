## 🔁 Step-by-Step RAG Pipeline

1. **Data Ingestion**  
   Load data sources such as PDFs, plain text, or web content.

2. **Preprocessing**  
   Split documents into smaller chunks and attach metadata (e.g., title, page number, source).

3. **Embeddings**  
   Convert text chunks into dense vector representations using an embedding model.

4. **Vector DB**  
   Store embeddings in a vector database (e.g., ChromaDB) for fast similarity search.

5. **Query Embedding**  
   Transform the user’s query into a vector representation.

6. **Retrieval**  
   Perform a similarity search to fetch top-k most relevant chunks from the database.

7. **LLM Answer Generation**  
   Provide context-aware answers by combining the retrieved content with the user’s query.

8. **Enhanced Features**  
   - 📖 **Citations** → Attribute answers to specific sources/pages.  
   - ✅ **Confidence Score** → Show retrieval similarity.  
   - 📝 **Summaries** → Generate concise responses.  
   - 📜 **History Tracking** → Maintain conversation/query history.

## Information Retrieval Approaches

## 1. BM25

BM25 is a **sparse retrieval algorithm**.

It’s based on traditional Information Retrieval (IR) techniques using **term frequency (TF)** and **inverse document frequency (IDF)**.

It matches queries and documents by looking at **exact word overlaps** and weighting terms.

**Example:**  
If your query is *"real-time pricing model"*, BM25 will look for documents containing those exact words (and their frequencies).

📌 **Strength:** Very good at precise keyword matching.  
📌 **Weakness:** Fails when query and document use different wording (e.g., *car* vs. *automobile*).

---

## 2. RAG (Retrieval-Augmented Generation)

RAG pipelines usually use **vector search (dense retrieval)** instead of BM25.

Dense retrieval uses **embeddings (numerical vectors)** to represent queries and documents.

It retrieves documents not only by exact words, but also by **semantic similarity**.

**Example:**  
If your query is *"pricing engine"*, it may also retrieve docs about *"revenue optimization models"* because embeddings capture meaning.

📌 **Strength:** Captures semantic meaning and synonyms.  
📌 **Weakness:** Sometimes retrieves less relevant but semantically related docs (**hallucination risk**).

---

## 3. Hybrid Search (BM25 + Dense Retrieval in RAG)

Hybrid search combines **BM25 (sparse retrieval)** and **vector embeddings (dense retrieval)**.

The goal is to get the **best of both worlds**:

- BM25 ensures exact keyword match.  
- Embeddings ensure semantic match.

**Ways to combine:**
- **Score fusion** – normalize and combine BM25 + vector similarity scores, then rank.  
- **Union/Intersection** – take top-k from both and merge.  
- **Weighted hybrid** – e.g., *70% embedding relevance + 30% BM25 releva*


