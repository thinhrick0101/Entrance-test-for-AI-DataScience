# Legal Document Crawler

## Overview
This project is an asynchronous web scraper designed to download and organize legal documents from the Vietnamese Ministry of Justice's PhapDien website. The crawler fetches documents of different types, including full text, properties, history, related documents, and PDFs.

## Features
- Downloads and extracts legal document archives.
- Asynchronous web scraping using `aiohttp` for efficient fetching.
- Retries failed requests with exponential backoff.
- Saves different types of documents into categorized directories.
- Logs errors and progress for debugging and monitoring.

## Prerequisites
Ensure you have the following dependencies installed before running the script:

```sh
pip install aiohttp aiofiles beautifulsoup4 tqdm requests zipfile langchain torch
```

## Usage
1. Clone the repository and navigate to the project directory.
2. Run each cell in `crawl.ipynb` and `create_vectordb.ipynb`.

## Project Structure
```
.
├── crawl.ipynb             # Main script for downloading and processing documents
├── create_vectordb.ipynb   # Main script for creating database and storing documents
└── README.md               # Project documentation
```

## Functions
### In `crawl.ipynb`

### `download_and_extract()`
Downloads the legal document archive from the official source and extracts its contents.

### `fetch_with_retry(session, url, retries=3, delay=1)`
Fetches a URL with retry logic to handle temporary failures and rate limits.

### `save_content(content, save_path)`
Saves the downloaded content to a file asynchronously.

### `process_item_id(session, item_id)`
Processes a document ID by fetching and saving its various document types.

### `process_index_file(session, index_path)`
Asynchronously processes an index file by extracting item IDs and processing each one.

### `main()`
Asynchronous entry point for the crawler.

### In `create_vectordb.ipynb`

### `search_documents(query, k=5)`
Searches for documents similar to the given query and prints the results.

## Large Data Files and Vector Databases
Here is the shared link of data via Drive
[https://drive.google.com/drive/folders/1YSaJLPS7ORTtxVkrn8V6E9XECH0FNqN9?usp=sharing](https://drive.google.com/drive/folders/1YSaJLPS7ORTtxVkrn8V6E9XECH0FNqN9?usp=sharing)


