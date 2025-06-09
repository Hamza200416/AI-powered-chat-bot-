Modules and Tools Used

spacy – for Named Entity Recognition (NER).

sentence-transformers – to convert questions into vector embeddings.

faiss – Facebook’s library for efficient similarity search.

json and datetime – for logging conversations.

defaultdict – to track unanswered queries.



---

⚙️ Working Principle (Step-by-step)

1. Initialization

Loads a small English NLP model (en_core_web_sm) for entity extraction.

Loads the SentenceTransformer model (all-MiniLM-L6-v2) for sentence embedding.


2. Knowledge Base Setup

A dictionary of predefined FAQs (question-answer pairs) is created.

The keys (questions) are embedded into vectors using the embedding model.


3. FAISS Indexing

FAISS is initialized with the vector dimension.

Encoded questions are added to the FAISS index for similarity search.


4. Main Functionalities

a. retrieve_faq(query, top_k=1)

Converts the input query into an embedding.

Searches for the most similar question in the knowledge base using FAISS.

Returns the best-matching answer or logs the query as "unknown" if no match is found.


b. extract_entities(user_input)

Uses spaCy to extract named entities (like product names, dates, etc.).

Helpful for understanding context or future recommendation systems.


c. generate_response(user_input)

First, extracts entities (if any).

Then, retrieves the closest FAQ answer via retrieve_faq.


d. log_conversation(user_input, bot_response)

Logs the conversation with a timestamp to chat_logs.json for later analysis or training.


e. chat()

The main loop that runs the chatbot.

Takes user input, generates responses, prints, and logs them.


5. Entry Point

if __name__ == "__main__":
    chat()

Runs the chatbot when the script is executed directly.
