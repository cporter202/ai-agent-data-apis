# Playbook: RAG Pipeline from Any Website

Turn any website into a knowledge base your AI can query. Crawl it, chunk it, embed it, ask it questions — with actors doing the heavy lifting.

## What you get

A question-answering system over any site's content: docs, blogs, product catalogs, forums. Ask in plain language, get answers grounded in the actual pages.

## Step 1 — Pick your actors

From the [catalog](../catalog/README.md):

- **RAG, embeddings & knowledge bases** (56) — purpose-built RAG actors
- **Live web data for agents** (496) — website crawlers that output clean markdown, ideal RAG input

The crawler matters most: clean markdown in means good chunks out.

## Step 2 — Crawl the source site

Run a website-content-crawler actor against your target site. Configure:

- **Start URLs** — the site root or sitemap
- **Max pages** — start with 100–500 while testing
- **Output format** — markdown (cleanest for chunking)

Export the dataset. You now have every page as structured text.

## Step 3 — Chunk and embed

Split pages into chunks (500–1,000 tokens with overlap), embed each chunk with an embedding model, and store vectors in your vector DB (Pinecone, Weaviate, pgvector, or even a local FAISS index for prototypes).

Several actors in the **RAG & knowledge bases** section handle chunking + embedding as a single step.

## Step 4 — Query it

Retrieval flow:

1. Embed the user's question
2. Fetch the top 5–10 most similar chunks
3. Stuff them into the LLM prompt as context
4. The model answers from the chunks, citing sources

This grounds every answer in your crawled content — no hallucinations about things the site never said.

## Step 5 — Keep it fresh

Schedule the crawler to re-run weekly (or daily for fast-changing sites). Re-embed changed pages, and your knowledge base never goes stale.

## The math

A 500-page docs site crawls for a few dollars in actor runs. The alternative — hand-writing a knowledge base or paying for a managed RAG service — costs 10–100x more. Actors make RAG a weekend project.

**[→ Start crawling on Apify](https://apify.com?fpr=p2hrc6)**
