# RAG System for Food, Ingredients, and Restaurants

## Introduction
This repository contains a Google Colab notebook connected to Google Drive, showcasing a Retrieval-Augmented Generation (RAG) system. It integrates data from CSV files and web scraping to generate intelligent indexes and provide answers related to food, ingredients, and restaurants. The system also ensures polite responses when faced with uncertainty or offensive queries.

## Key Features & Innovations

### 1. Scalability with Web URLs
- **Dynamic Data Sources:** Utilizes web URLs, making the system inherently scalable and easily extendable to larger datasets.
- **Modular Design:** Seamless integration of additional data sources without major architectural changes.

### 2. Cost-Effective Embedding Generation
- **Open-Source BGE Model:** Leverages the free BGE model for embedding generation, minimizing costs while maintaining performance.
- **Efficient for Large-Scale Expansion:** Ideal for projects requiring cost-effective scaling.

### 3. Transparent Document Selection with Citations
- **Explainable Retrieval:** The model explains why specific documents were retrieved.
- **Proper Citations:** Enhances trust and factual reliability through detailed references.

### 4. Chain-of-Thought Reasoning
- **Step-by-Step Logic:** Incorporates Chain-of-Thought (CoT) prompting for coherent, logical responses.
- **Enhanced Reasoning:** Reflects the reasoning process behind each answer.

### 5. Polite and Context-Aware Responses
- **Professional Tone:** Provides polite responses when unsure or when faced with offensive queries.
- **Context-Awareness:** Maintains a respectful tone throughout.

### 6. Structured Response
- **Organized Output:** Returns structured responses with answers followed by a quote list, detailing the source, reason for selection, and citations.

## Data Ingestion Workflow

### Data Sources
- **Web Scraping:** Uses a curated list of URLs (`web_urls`) to scrape relevant, up-to-date information.
- **CSV Documents:** Ingests structured data from CSV files (`documents`), blending static and dynamic data inputs.

### Data Preprocessing
- **Chunking:** Divides text from both sources into meaningful chunks using semantic segmentation techniques to maintain context.
- **Embedding:** Transforms each chunk into vector embeddings using the BGE model, optimizing for both performance and cost.

### Indexing
- **FAISS Indexing:** Indexes chunks using FAISS for fast and efficient similarity searches across large datasets.

## Retrieval Approach & Pipeline Architecture

### Query Processing
- **Parsing:** User queries are parsed and preprocessed to align with the embedding space.

### Contextual Retrieval
- **Similarity Search:** Query embeddings are compared against indexed document embeddings using cosine similarity.
- **Model Used:** Retrieval powered by the `BAAI/bge-small-en` model.

### Response Generation
- **Prompt Integration:** Retrieved chunks are incorporated into the prompt for the language model.
- **Chain-of-Thought Prompting:** Ensures logical, step-by-step reasoning in responses.
- **Citations & References:** Outputs include clear citations explaining why specific documents were selected.

### Politeness & Factual Consistency
- **Polite Responses:** Provides polite responses when uncertain.
- **Avoiding Misinformation:** Actively avoids generating or propagating offensive or misleading content.

## Prompt Strategy

### Incorporating Retrieved Context
- **Seamless Integration:** Retrieved text chunks are embedded into prompts to ground responses in factual data.

### Demonstrating Reasoning
- **Chain-of-Thought:** Highlights the reasoning behind each answer to enhance transparency and trust.

### Factual Consistency
- **Cross-Verification:** Cross-verifies information across multiple sources and provides citations to maintain factual integrity.

## Future Enhancements

### Knowledge Graph Integration
- **Improved Relational Understanding:** Building a knowledge graph to improve relationships between concepts and enhance retrieval precision.

### Scaling with Additional Data Sources
- **Broader Coverage:** Integrating more dynamic data sources for comprehensive responses.

### Introducing UI
- **User Interface:** Developing a visually attractive UI for users to enter questions and receive responses interactively.

---
