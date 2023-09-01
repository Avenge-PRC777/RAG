# RAG
## Links
1. https://www.promptingguide.ai/techniques/rag
2. https://python.langchain.com/docs/use_cases/question_answering/how_to/vector_db_qa
3. https://ai.meta.com/blog/retrieval-augmented-generation-streamlining-the-creation-of-intelligent-natural-language-processing-models/

## Technique
1. Normally LLMs produce Generation, but if we first retrieve some grounded info from some source, augmented the prompt with that retrieved info then the generation is called Retrieval Augmented Generation
2. Now, it helps reduce hallucination.
3. But also if **the retriever is bad then an answerable question can also be left unanswered**.
4. Details of retrieval process here: https://python.langchain.com/docs/modules/data_connection/
5. Document loader supports different types of documents, even pdf.
6. The process is simple, data->chunks->embed->store in datastore->retrieve using algorithm (basic is semantic search)
7. ```
   embeddings = OpenAIEmbeddings()
   docsearch = Chroma.from_documents(texts, embeddings)
   qa = RetrievalQA.from_chain_type(llm=OpenAI(), chain_type="stuff", retriever=docsearch.as_retriever())
   ```
8. The chain has the prompt information
9. There are two main ways to retrieve documents relevant to a query- Similarity Search and Max Marginal Relevance Search (MMR Search). Similarity Search is the default, but you can use MMR by adding the search_type parameter (https://python.langchain.com/docs/use_cases/question_answering/how_to/vector_db_qa#vectorstore-retriever-options):
 ```
    docsearch.as_retriever(search_type="mmr")
 ```
