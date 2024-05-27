---
tags:
    - retrieval 
    - evaluation 
    - LlamaIndex 
    - TruLens
---


[Course Link](https://learn.deeplearning.ai/courses/building-evaluating-advanced-rag/lesson/1/introduction)

This course is prepared with LlamaIndex andTruEra, mainly focusing on two retrieval options and [TruLens](https://www.trulens.org). The two retrieval options are:
- RAG Triad of Metrics
- *Sentence Window Retrieval*
- *Auto-Merging Retrieval*
Basic knowledge on LlamaIndex and TruLens will help a lot on this course. Also, both libraries' recent updates had some serious changes and the **code is outdated now**. Especially on the usage of [`ServiceContext`](https://docs.llamaindex.ai/en/stable/module_guides/supporting_modules/service_context_migration/) from LlamaIndex and [`Groundedness`](https://github.com/truera/trulens/issues/1149) from TruLens.

## RAG Triad of Metrics
This part is focused on the base usage of the TruLens and introduces three metrics for RAG system evaluation.
- **Context Relevance**: Basically how well the base retrieving method worked and the relevance of the retrieved text to the question
- **Answer Relevance**: How how much relevant the answer to the question 
- **Groundedness**: Looking for the proofs in the answers. How well are they supported by the facts.

Even though these are the only metrics used in this course, there are many more LLM evaluation alternatives in TruLens.
![LLM Evaluations](/images/2024-05-27-Building%20and%20Evaluating%20Advanced%20RAG/_llm_evaluations.png)
<sub>Resource: Course Documents</sub>

## Sentence Window Retrieval
This retrieval method adds former and latter $n$ sentences to the actual sentence. $n$ is denoted by `window_size` parameter. For example, say the original document to be "Hello. Foo bar. Cat dog. Bye" and the embedding search returns "Foo bar.". If `window_size = 1` then `SentenceWindowRetrieval` will send "Hello. Foo bar. Cat dog" to the LLM

## Auto-Merging Retrieval
First of all, this option expects a hierarchical/tree like structure of the chunks(*nodes* in LlamaIndex lingo) and this can be achieved by `HierarchicalNodeParser`. With this the document can be split into different sizes of chunks. For example, `chunk_sizes = [2024, 512, 128]` resulting three layers of hierarchy. Then, when a threshold[^1] is passed auto-merging retrieval returns the parent node, instead of the leaf.
This splitting with different sizes cause a lot of overlapped texts. All the parents contain the texts from their children. But the vector store stores only the leaf nodes. In this example the one with 128 length. This will reduce the costs on the vector store side.


[^1]: Unfortunately I couldn't find any more details about this *threshold*. Not even in the [example from the LlamaIndex docs](https://docs.llamaindex.ai/en/stable/examples/retrievers/auto_merging_retriever/)
