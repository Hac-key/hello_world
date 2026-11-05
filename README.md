# hello_world

A small Python project that reads news articles from a CSV file, summarizes each article with the OpenAI API, and writes the results to an output CSV.

## Project overview

This app is designed to process a dataset of news stories and generate concise summaries while preserving progress in the output file. It supports resuming from previously completed rows and tracks status for each article.

## Features

- Reads `title` and `content` columns from a CSV file
- Summarizes each article using the OpenAI Responses API
- Saves results to `output/news_summaries.csv`
- Resumes work without reprocessing completed articles
- Marks rows as `completed`, `skipped`, or `error`

## Project structure

- `main.py` — entry point for the summarization workflow
- `data/` — input CSV files
- `output/` — generated summary CSV files
- `requirements.txt` — Python dependencies
- `.env` — local environment variables

## Setup

1. Create and activate a virtual environment if needed.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Create a `.env` file in the project root with your OpenAI key:

   ```env
   OPENAI_API_KEY=your_api_key_here
   OPENAI_MODEL=gpt-5-nano
   ```

4. Prepare an input CSV file at `data/news.csv` with at least these columns:

   ```csv
   title,content
   "Example headline","Example article body..."
   ```

## Run

```bash
python main.py
```

The script will read the input file, process each item, and save summaries in the output folder.
