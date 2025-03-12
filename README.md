# Oura Assistant
An AI assistant specialized in answering questions about Oura ring app usage. Built using a RAG pipeline with GPT-4o-mini, it provides accurate, source-cited answers and identifies out-of-scope questions.

[Live Demo](https://huggingface.co/spaces/tylervu-main/oura-assistant)

# Project Structure

- **OuraAssistant.ipynb**: Main Jupyter notebook containing the complete implementation of the RAG pipeline, from data collection to evaluation
- **gradio/**: Directory containing Gradio implementation files
    - `app.py`: Python code for the web interface
    - 'requirements.txt': Dependencies for the deployment
- **scraped_text/**: Directory containing the text data extracted from various sources
- **ouraring_links.txt*: URLs collected from the main Oura Ring website
- **support_links.txt**: URLs collected from the Oura support website
- **failed_urls.txt**: Log of URLs that couldn't be accessed during scraping
- **performance_metrics_comparison.png**: Visualization of the system's performance metrics

# Approach
This project implements a specialized question-answering system using these key components:

- Data Collection: Scraping Oura website, support documentation, Reddit threads, and YouTube transcripts
- Vector Database: Converting text chunks to embeddings and storing them in Pinecone
- Query Classification: Identifying whether questions are related to Oura
- RAG Pipeline: Retrieving relevant context for in-scope questions and generating answers
- Web Interface: Providing a user-friendly way to interact with the system

# Performance
The system achieves:

- 100% accuracy in identifying Oura-related questions
- 73.3% answer correctness across all questions
- 70% contextual accuracy in using relevant information

# Running the Project To run the Gradio interface locally:

```bash
cd gradio
pip install -r requirements.txt
python app.py
