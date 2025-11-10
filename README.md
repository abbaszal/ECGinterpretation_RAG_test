# ECG RAG Test

This repository contains a simple **RAG** pipeline for **ECG interpretation knowledge**


##  Pipeline
1. **Knowledge Base**
   - Source: `ECG_Reference_Level_Knowledge_Base.csv`
 ### ECG Reference Knowledge Base

This dataset was derived from the document:
**"Methodological ECG Interpretation" by Dr. Araz Rawshani (2017)**  
Source: [https://ecgwaves.com](https://ecgwaves.com)
   - Each record contains a piece of expert ECG reference content.

2. **Embedding & Indexing**
   - Model: `sentence-transformers/all-MiniLM-L6-v2`
   - Vector index: `FAISS`

3. **Generation**
   - Model: `google/flan-t5-base`
   - The query + retrieved context are combined into a prompt.
   - The model generates an answer grounded in the retrieved knowledge.

## Example
```python
question = "What are the ECG findings that indicate ischemia?"
print(rag_answer(question))
