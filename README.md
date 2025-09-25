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
