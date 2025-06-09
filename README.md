Step-by-Step Guide to Run the Chatbot on Your PC

 1. Install Python

- Download and install Python 3.8 or newer from: https://www.python.org/downloads/

- During installation, check Add Python to PATH.

 2. Prepare Your Project Folder

- Create a folder (e.g., chatbot).

- Place your chatbot code into a file named chatbot.py.

 3. Fix Code Errors

- Replace curly quotes ( ) with standard quotes (" ").

- Fix indentation and capitalization errors like 'If' to 'if', and correct 'def' declarations.

- (You can request a cleaned version from ChatGPT.)

 4. Install Required Libraries

Open terminal and run:

pip install faiss-cpu

pip install sentence-transformers

pip install spacy

python -m spacy download en_core_web_sm

 5. Run the Bot

- Navigate to the chatbot folder:cd path\to\your\chatbot\folder

- Run the chatbot:

python chatbot.py

You will see:

Smart E-commerce Chatbot (type 'quit' to stop)

You:

Type your question (e.g., Do you offer free shipping?) and the bot will respond.

 6. Check Logs

All chats are saved in chat_logs.json in the same folder.

 What the Code Does:

- Uses spaCy to extract entities (like product names).

- Uses SentenceTransformer to convert questions to vectors.

- Uses FAISS to search for the most similar question.

- Returns the answer from a predefined FAQ.

- Logs unknown questions and all conversations for improvement.
