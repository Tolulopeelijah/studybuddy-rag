# StudyBuddy - AI-Powered Study Material Assistant

StudyBuddy is a lightweight assistant that helps you process and search through PDF study materials using AI. It uses language models, embeddings, and vector databases to make academic research and studying more efficient.

Features

Load and chunk large PDF study materials

Convert content to vector embeddings using HuggingFace models

Store and search documents with ChromaDB

Query relevant content using semantic search

Supports LLMs like LLaMA3 via Groq API

Tech Stack

LangChain

ChromaDB

PyPDFLoader (LangChain Community)

HuggingFace Embeddings

ChatGroq

Torch

Python 3.10+

Project Structure

.├── data/                   # Folder for your PDF files├── notebook.ipynb          # Main notebook for running the assistant├── studybuddy/             # (Optional) Python modules if extracted├── environment.yml         # Conda environment export└── README.md               # You're here

Setup Instructions

1. Clone the Repo

git clone https://github.com/yourusername/studybuddy.gitcd studybuddy

2. Create the Environment

If you're using conda:

conda env create -f environment.ymlconda activate studybuddy

Or with pip:

pip install -r requirements.txt

3. Configure .env

Create a .env file in the root directory:

GROQ_API_KEY=your_groq_api_key

How It Works

PDF Loading – via PyPDFLoader

Text Chunking – using RecursiveCharacterTextSplitter

Vector Embedding – with HuggingFaceEmbeddings

Storage – into ChromaDB as vector documents

Query – ask questions and retrieve matching study material chunks

Sample Usage

query = "What is lexical scoping?"results = search_material_db(query, collection, embeddings)

for chunk in results:print(chunk["title"], "->", chunk["content"][:200])

Status



Author

Built by Your NameFeel free to reach out with questions or ideas for collaboration.

License

This project is licensed under the MIT License – see the LICENSE file for details.

