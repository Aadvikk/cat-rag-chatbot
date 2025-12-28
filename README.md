# Cat RAG Chatbot

This project implements a lightweight Retrieval-Augmented Generation (RAG)
pipeline that answers questions using a domain-specific PDF about cats.

Rather than relying solely on a language model’s internal knowledge,
the system retrieves relevant document chunks at query time and uses
them as grounding context to generate more reliable answers.

## How It Works
1. Load a PDF document
2. Split text into overlapping chunks
3. Generate vector embeddings for each chunk
4. Store embeddings in a FAISS vector index
5. Retrieve the most relevant chunks for a user query
6. Generate a grounded response using a language model

## Tech Stack
- Python
- Google Colab
- LangChain
- FAISS (vector similarity search)
- Hugging Face Sentence-Transformers (embeddings)
- OpenAI (LLM for response generation)

## Embeddings Design Choice
The initial design of this project used OpenAI embeddings for vectorization.
To improve reproducibility and avoid API quota limitations, the final
implementation uses a local Hugging Face sentence-transformer model
(`all-MiniLM-L6-v2`) to generate embeddings.

This approach keeps the pipeline fully functional in a free notebook
environment while maintaining strong semantic retrieval performance.

## Example Queries
- Why do cats purr?
- What do cats eat?
- How long do cats sleep?

## Notes
This project was developed entirely in a notebook environment to focus on
experimentation, clarity, and end-to-end understanding of the RAG workflow.
