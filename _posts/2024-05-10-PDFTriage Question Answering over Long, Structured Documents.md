---
tags:
  - pdf_text_extraction
  - paper
id: 66ad6e92-5852-480f-a15f-d10fd3dfe7ff
---

## General Thoughts
Overall I like the idea of creating metadata and functions. But usage of each function will blow up the total token. Regarding to table 3 and figure 13 this approach does not create miracles. There is no embedding can be used with graph databases..
[Paper link](https://arxiv.org/pdf/2309.08872.pdf)

## Highlights

> fetch_table, fetch_figure, and retrieve [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#107f721f-7c02-4502-87e0-75ae1e07f2e0)  

> Table 3: Answer Quality Scoring [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#d07ca254-a0b2-4d00-9d35-2a3eaa7118d0)  

Why this table results is so different than figure 3? In my opinion, structure related questions are not relevant for page and chunk embedding. Did the overall preference in figure3 calculated regarding to taxonomy proportions? structure related questions are only 3.7%

> The key contributions of this paper are: • We identify a gap in question answering over structured documents with current LLM approaches, namely treating documents as plain text rather than structured objects; • We release a dataset of tagged question types, along with model responses, in order to facilitate further research on this topic; and • We present a method of prompting the model, called PDFTriage, that improves the ability of an LLM to respond to questions over structured documents. [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#2179998c-cc30-4f15-8d9c-3b0162c7d609)  

> 8. Outside Questions (8.6%): Ask a question that can’t be answered with just the document. 9. Cross-page Tasks (1.1%): Ask a question that needs multiple parts of the document to answer. 10. Classification (3.7%): Ask about the type of the document. [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#120b5334-7257-4ff4-bd6e-524eca76df68)  

> ReAct (Yao et al., 2022) or Toolformer (Schick et al., 2023) -like way [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#86349b7f-5271-4241-99a4-c19d2da0a2cb)  

Check papers for improvement

> section #5? [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#1d3603d2-67f5-42c8-bf8d-82a6d8af9c3d)  

It's more of a structure question than a text question

> PDFs, web pages, and presentations are naturally structured with different pages, tables, sections, and so on. Representing such structured documents [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#974f6bcc-5e24-4a00-92a4-bd022eb3d851)  

Structured text does not only look like a simple headeres titles and text. But also includes tables, images and follow a standard structure

> On average a document contains 4,257 tokens of text [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#a970f56c-0a89-4f08-a70a-8f02ff3e83e7)  

Not bad

> 3.1 Document Representation [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#3044e997-d375-4454-bfb1-18b3d59b9baf)  


Metadata creation process!
Quite important but not much technical detail given

> 1. Figure Questions (6.5%): Ask a question about a figure in the document. 2. Text Questions (26.2%): Ask a question about the document. 3. Table Reasoning (7.4%): Ask a question about a table in the document. 4. Structure Questions (3.7%): Ask a question about the structure of the document. 5. Summarization (16.4%): Ask for a summary of parts of the document or the full document. 6. Extraction (21.2%): Ask for specific content to be extracted from the document. 7. Rewrite (5.2%): Ask for a rewrite of some text in the document. [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#7cf7d2b2-0dd2-4ccc-92cd-48a0262b7ca4)  

> we release our benchmark dataset consisting of 900+ human-generated questions over 80 structured documents from 10 different categories of question types for document QA [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#6c654c98-b525-4e0e-8e4b-0c9ddbfa6c38)  

Great resource for evaluation

> 100-word pieces [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#fe7c41dc-e19e-43ad-b131-cbb9507cb053)  

No semantic chunk(not even recursive). Wonder how that would score

> leverage document structure by augmenting prompts with both document structure metadata [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#fedaf2c1-33e6-4f5d-ba28-c36cd20d05be)  

Document structure metadata!

> Landeghem et al. (2023) [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#935e33ed-d79a-40d6-9ee4-191493b63b2b)  

> DUDE [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#e5c65e93-9ab0-47a2-9778-b4c489c9200c)  

Check paper

> Page Retrieval [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#50c81d4d-f56e-4750-9c9f-20c2e3c142d0)  

Very simple and straightforward approach

> QASPER (Dasigi et al., 2021) [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#062476d6-d34a-4e0e-9a9b-2900a3660a7a)  

Check paper

> five different functions [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#3e3f2b73-9c65-4776-9bb8-eabdb7cdd74e)  

> multi-step reasoning across the whole document. [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#1c60d5d2-fccd-4f4c-a918-d2259be71683)  

So multiple document answering is subject in this paper, right?

> fetch_pages, fetch_sections [⤴️](https://omnivore.app/me/https-arxiv-org-pdf-2309-08872-pdf-18f1534e815#bc8e6810-6c66-4bae-b563-9e1e3ad80e43)  

---