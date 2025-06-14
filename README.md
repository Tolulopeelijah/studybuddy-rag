# StudyBuddy - AI-Powered Study Material Assistant

StudyBuddy is a lightweight AI-powered assistant designed to help you process and explore PDF study materials intelligently. Beyond simple search, it automatically generates 5 open-ended and 5 closed-ended questions that cover the core content of your uploaded materials. Users can answer one question at a time, after which StudyBuddy evaluates the response highlighting what was accurate, what should have been added or avoided, and common pitfalls to watch out for. It leverages language models, embeddings, and vector databases to create an interactive, feedback-driven learning experience that boosts study effectiveness.

## Features

- Load and chunk large PDF study materials using PyPDFLoader and RecursiveCharacterTextSplitter  
- Generate vector embeddings with HuggingFace’s all-MiniLM-L6-v2 model  
- Store and search documents efficiently using ChromaDB  
- Retrieve relevant content using semantic search and top-k similarity matching  
- Generate 5 open and 5 closed questions from study materials using an LLM  
- Evaluate user answers with AI feedback on accuracy, relevance, and pitfalls  
- Supports LLMs like LLaMA3 via Groq API for fast completions  

## Tech Stack

- `LangChain`
- `ChromaDB`
- `PyPDFLoader` (from LangChain Community)
- `HuggingFace Embeddings`
- `ChatGroq`
- `Torch`
- `Python 3.10+`

## Project Structure
```
├─ data/
├── notebooks/
├── research_db/
├── environment.yml
├── LICENSE
├── README.md
├── .env
└── .gitignore
```


## Setup Instructions

1. Clone the Repo

```git clone https://github.com/yourusername/studybuddy.gitcd studybuddy```

2. Create the Environment

If you're using conda:

```conda env create -f environment.ymlconda activate studybuddy```

Or with pip:

```pip install -r requirements.txt```

3. Configure .env

Create a .env file in the root directory:

GROQ_API_KEY=your_groq_api_key

## How It Works

- PDF Loading – Study materials are loaded from PDF files using PyPDFLoader from LangChain Community tools.

- Text Chunking – Each document is split into overlapping, searchable chunks using RecursiveCharacterTextSplitter to preserve context and optimize semantic search.

- Vector Embedding – Chunks are converted into vector embeddings using HuggingFace’s all-MiniLM-L6-v2 model, optimized for retrieval tasks.

- Storage – Embeddings, along with their metadata, are stored in a ChromaDB collection for fast and efficient similarity search.

- Question Generation – The system generates 5 open-ended and 5 closed-ended questions based on the uploaded materials using an LLM.

- User Interaction – The user answers one question at a time. After each answer, the system evaluates the response and gives detailed feedback:

  - What should have been included

  - What should be avoided

  - Common pitfalls and how to improve

## Sample Usage
```
answer, sources = buddyassistant(
    "Programming language design",
    collection, 
    embeddings, 
    llm
)

for ind, each in enumerate(answer):
    print(f"Question {ind + 1}: {each['question']}", end = '\n\n')
    print(f"Your answer: {each['answer']}")
    print(f"AI's Evaluation: {each['evaluation']}")
    print("=" * 150, '\n')
)
```



## Author

Built by Your Tolulope Elijah free to reach out with questions or ideas for collaboration.

## License

This project is licensed under the MIT License – see the LICENSE file for details.

