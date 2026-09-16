# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project state

This is an early-stage Retrieval-Augmented Generation (RAG) project. There is no application
architecture yet to document — `main.py` is still the unmodified `uv init` placeholder, and the
only real work in progress is document-ingestion exploration in `notebook/document.ipynb`
(currently just imports `langchain_core.documents.Document` under a "Data Ingestion" heading).
`data/` is empty. Update this file as real structure emerges.

## Environment and commands

Dependencies are managed with `uv` (see `pyproject.toml` / `uv.lock`). Python 3.12 is pinned via
`.python-version`.

- Install/sync dependencies: `uv sync`
- Run the entrypoint: `uv run main.py`
- Add a dependency: `uv add <package>` (keeps `pyproject.toml` and `uv.lock` in sync)
- Run Jupyter on the notebook: `uv run jupyter lab notebook/document.ipynb` (the `ipykernel`
  dependency is already included)

Note: `requirements.txt` lists the same core packages (langchain, langchain-core,
langchain-community, pypdf, pymupdf) but `pyproject.toml`/`uv.lock` is the source of truth for
installs — prefer `uv` commands over `pip install -r requirements.txt`.

There are no lint, format, or test configurations/tools set up in this repo yet.

## Stack

- **langchain** / **langchain-core** / **langchain-community**: core RAG orchestration.
- **pypdf** / **pymupdf**: PDF parsing, for document ingestion.
