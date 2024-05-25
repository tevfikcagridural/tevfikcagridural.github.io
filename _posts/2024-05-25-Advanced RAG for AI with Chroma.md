---
tags:
    - RAG 
    - vector_database 
    - reranking 
    - query_enhancement 
    - vector_pitfalls 
    - embedding 
---

[Course Link](https://learn.deeplearning.ai/accomplishments/d540d1c3-69d5-442d-99f7-498c3650783b)

This course basically covers 4 main concepts:
## Pitfalls or retrieval - when vector search fails 
Under this topic the most important subject is [[Relevancy and Distractions]]. And unfortunately there is no straightforward solution provided.

## Query Expansion
This method is enhancing the query with two different ways. Both uses an LLM to add more variety and context to the base query. However, these additional calls will cause latency and token increase. The tradeoff should be strictly looked after
### Generated Answers
In this option an llm first asked with the query right away, without any context given from the datastore. Later on the initial query sent to the datastore with generated answer. 
### Multiple Queries
In this option the LLM asked to generate similar questions. Then with these augmented queries the datastore queried. 

## Reranking
Especially a cross-encoder reranking. Where the returned answers reranked within and the query by a reranking model. The options can be: Cross-Encoders, Bi-Encoders, Hybrid approaches and an LLM model to be prompted act as a reranking model.

{% include collapsible.html type="quote" title="ChatGPT-4o Generated details of first 3 options" content="
### Cross-Encoders 
**Cross-Encoders** are a specific type of neural network model where the query and each candidate document are concatenated and passed through the model together. This allows the model to consider the interactions between the query and the document in a detailed manner, leading to high accuracy in ranking. The main characteristics are:
 
- **High Precision:** Because the model can attend to the interactions between the query and the document tokens, it often achieves superior performance compared to other methods.
- **Computationally Intensive:** Since each document needs to be processed along with the query, the computational cost increases linearly with the number of documents to re-rank.

### Bi-Encoders
**Bi-Encoders** independently encode the query and the documents using two separate encoders (often the same model with shared weights). The representations of the query and the documents are then compared, typically using a similarity measure like cosine similarity. Key points include:
 
- **Efficiency:** Bi-Encoders are more efficient than Cross-Encoders because document representations can be pre-computed and stored, allowing quick similarity computation during re-ranking.
- **Lower Precision:** The independent encoding of query and documents might miss some nuanced interactions, potentially leading to less precise rankings compared to Cross-Encoders. 
### Hybrid Approaches
**Hybrid Approaches** combine elements of both Cross-Encoders and Bi-Encoders to balance precision and efficiency. One common hybrid method is to use a Bi-Encoder for an initial fast re-ranking pass and then apply a Cross-Encoder on a smaller subset of top candidates for a more precise ranking. This method tries to leverage the strengths of both models." %}

## Embedding Adaptors
This approach is adapting the query based on the user feedback. After the system returned $n$ answers, the marks the selected answer which might not be the first returned. This mark is used as feedback and an embedding adaptor model created. Later on the given query will be adapted with this model **before querying the datastore**. 
