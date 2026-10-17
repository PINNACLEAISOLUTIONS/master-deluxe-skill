# Generative Engine Optimization (GEO), SEO & RAG Architectures

## 1. Generative Engine Optimization (GEO)
Generative Engine Optimization is the discipline of structuring web and digital content so that modern AI search engines (Perplexity, ChatGPT Search, Claude, Google Gemini) select, synthesize, and cite your assets as authoritative primary sources.

### Core Citation Factors
- **Information Density**: AI models favor concise, fact-dense paragraphs over verbose marketing padding.
- **Named Entities & Data**: Explicit numbers, dates, version numbers, and verified benchmarks significantly increase retrieval probability.
- **Structured Schema (JSON-LD)**: Embed structured data markup (`TechArticle`, `Product`, `FAQPage`, `Organization`) for unambiguous entity mapping.
- **Direct Answer Headings**: Format section headings as questions (`H2: How does X work?`) followed immediately by a 2-3 sentence definitive answer.

---

## 2. Retrieval-Augmented Generation (RAG) Architecture
Retrieval quality dictates generation quality. A poorly indexed knowledge base guarantees LLM hallucinations.

### Chunking Strategies
- **Semantic Chunking**: Split on logical thematic shifts rather than fixed character/token limits. Respect sentence and markdown header boundaries.
- **Chunk Size Hierarchy**:
  - Small Chunks (128–256 tokens): Precision retrieval for factual questions, dates, numbers.
  - Large Chunks (512–1024 tokens): Contextual retrieval for synthesis and conceptual explanations.
- **Contextual Overlap**: Maintain a 10–15% overlap between chunks to prevent boundary information loss.

### Hybrid Retrieval Pipeline
Combine **Dense Vector Search** (semantic similarity via embeddings like `text-embedding-3-large`) with **Sparse Keyword Search** (BM25 / full-text search) using Reciprocal Rank Fusion (RRF) to capture both exact matches and semantic intent.
