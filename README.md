# RAG
## Links
1. https://www.promptingguide.ai/techniques/rag
2. https://python.langchain.com/docs/use_cases/question_answering/how_to/vector_db_qa

## Technique
1. Normally LLMs produce Generation, but if we first retrieve some grounded info from some source, augmented the prompt with that retrieved info then the generation is called Retrieval Augmented Generation
2. Now, it helps reduce hallucination.
3. But also if **the retriever is bad then an answerable question can also be left unanswered**.
