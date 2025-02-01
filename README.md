# PhysicsRAG-Pipeline

A comprehensive pipeline for processing physics textbooks and creating an intelligent retrieval system using OCR, embeddings, and hybrid search capabilities.

## Features

- PDF content extraction (text, images, and tables)
- Intelligent text chunking with context preservation
- Multi-modal content processing
- Hybrid search system combining BM25 and semantic search
- Batch query processing with async support
- Integration with Gemini AI for embeddings and context generation
- PostgreSQL for vector storage
- Elasticsearch for efficient text search

## Prerequisites

- Python 3.8+
- PostgreSQL 13+ with pgvector extension
- Elasticsearch 8.x
- Poppler (for PDF processing)
- Docker (optional, for containerization)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/PhysicsRAG-Pipeline.git
cd PhysicsRAG-Pipeline
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Install Poppler:
   - Windows: Download from [poppler releases](http://blog.alivate.com.au/poppler-windows/)
   - Linux: `sudo apt-get install poppler-utils`
   - macOS: `brew install poppler`

5. Set up PostgreSQL with pgvector:
```sql
CREATE EXTENSION vector;
```

6. Create necessary database and tables (see database setup scripts)

## Configuration

1. Update database configuration in the code:
```python
db_params = {
    "dbname": "ragdatabase",
    "user": "postgres",
    "password": "your_password",
    "host": "localhost",
    "port": "5433"
}
```

2. Set up your Gemini API key:
```python
api_key = "your-api-key"
```

## Usage

1. Prepare your PDF documents in the specified directory structure:
```
data/
  └── Physics/
      └── PDF's/
          └── chapter_1/
              └── UnitsandMeasurements.pdf
```

2. Run the Jupyter notebook:
```bash
jupyter notebook main_ocr.ipynb
```

3. Follow the notebook cells for:
   - Content extraction
   - Processing and chunking
   - Embedding generation
   - Search system setup
   - Query processing

## Project Structure

```
PhysicsRAG-Pipeline/
├── data/                    # PDF documents and extracted content
├── images/                  # Extracted images from PDFs
├── notebooks/              
│   └── main_ocr.ipynb      # Main pipeline notebook
├── scripts/                 # Utility scripts
├── requirements.txt         # Python dependencies
└── README.md               # Project documentation
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
