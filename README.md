# Document Q&A with RAG using ChromaDB

## Overview

This project demonstrates how to build a **Document Q&A system** using **Retrieval-Augmented Generation (RAG)** with the **Chroma vector database** and the **Gemini API**. RAG addresses two major limitations of large language models (LLMs):
1. LLMs only "know" the information they were trained on.
2. LLMs have limited input context windows.

By combining document retrieval and LLM generation, RAG enables dynamic responses based on external knowledge, such as product-specific details or live updates.

### Key Components of RAG
1. **Indexing**: Prepares a searchable database of documents.
2. **Retrieval**: Identifies relevant documents based on a user query.
3. **Generation**: Combines retrieved documents with user input to generate a natural language response.

This project uses the following tools:
- **Chroma**: An open-source vector database for storing and searching document embeddings.
- **Gemini API**: For generating embeddings and creating responses.

---

## Features

- **Document Embedding and Storage**: Convert documents into vector embeddings and store them in ChromaDB.
- **Efficient Retrieval**: Query the database to find relevant documents for any question.
- **Dynamic Answer Generation**: Use the Gemini API to generate answers based on retrieved documents.

---

## Setup Instructions

### 1. Install Dependencies
Ensure you have Python installed, then run:
Add the key to your environment:
!pip uninstall -qqy jupyterlab kfp # Remove unused conflicting packages
!pip install -qU "google-genai==1.7.0" "chromadb==0.6.3"

### 2. Configure API Key
Obtain your Gemini API key from [AI Studio](https://aistudio.google.com/app/apikey) and store it as a Kaggle secret named `GOOGLE_API_KEY`. For more details, refer to the [Gemini API documentation](https://ai.google.dev/gemini-api/docs/api-key).

Add the key to your environment:
from kaggle_secrets import UserSecretsClient
GOOGLE_API_KEY = UserSecretsClient().get_secret("GOOGLE_API_KEY")


### 3. Prepare Documents
Define your dataset as plain text strings:
documents = [
"Document 1 content here...",
"Document 2 content here...",
"Document 3 content here..."
]


---

## Workflow

### Step 1: Create an Embedding Database
Use the Gemini API to generate embeddings for your documents and store them in ChromaDB.


### Step 2: Retrieve Relevant Documents
Query the database to find documents relevant to a user question.


### Step 3: Generate Answers
Use the Gemini API to generate an answer based on retrieved documents.


---

## Example Usage

1. **Input Query**: *"How do you use the touchscreen to play music?"*
2. **Retrieved Document**:
   > Your Googlecar has a large touchscreen display that provides access to a variety of features, including navigation, entertainment, and climate control...
3. **Generated Answer**:
   > To play music on your Googlecar, you can use the large touchscreen display by simply touching the "Music" icon, which will then allow you to play your favorite songs.

---

## Resources

- [Chroma Documentation](https://docs.trychroma.com/)
- [Gemini API Documentation](https://ai.google.dev/gemini-api/docs/)
- [FAQ & Troubleshooting Guide](https://www.kaggle.com/code/markishere/day-0-troubleshooting-and-faqs)

---

## Contributing

Contributions are welcome! Please fork this repository, make your changes, and submit a pull request.

---

## License

This project is licensed under the MIT License.







