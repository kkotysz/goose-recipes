# goose-recipes

This repository contains advanced **Goose agent recipes** for astronomy literature search, in particular for HADS (High-Amplitude Delta Scuti) and SX Phoenicis variable stars.

## Structure

- `hads-sxphe/` – main collection for searching, retrieving, and classifying HADS & SX Phoenicis papers from arXiv:
    - `recipe.yaml` – main orchestrator recipe (runs subrecipes, deduplicates, ranks, and classifies)
    - `subrecipes/`
        - `latest_hads_sxphe.yaml` – recent papers, recall-oriented
        - `classic_hads_sxphe.yaml` – classic, foundational, and review publications
        - `comprehensive_hads_sxphe.yaml` – broad, high-recall literature mining
- `LICENSE` – MIT License

All recipes make direct use of the [arxiv-mcp-server](https://github.com/aaif-goose/goose-mcp-arxiv), configured as an MCP extension, ensuring high-recall and fast up-to-date literature search.

## MCP arXiv Server: Quick Install

To run recipes locally you need the arxiv MCP server. Install it with:

```bash
uv tool install 'arxiv-mcp-server[pdf]'
```

To check it's working:
```bash
arxiv-mcp-server --help
```

If you run a recipe via goose CLI/desktop and the extension block is set, goose will launch the server itself using:

```
uv tool run arxiv-mcp-server --storage-path /your/path/to/arxiv-papers
```

You can adjust `--storage-path` to control the local arXiv cache location.

## Features
- Recipes compatible with [Goose agent platform](https://github.com/aaif-goose/goose)
- Parameterized search (limit by date, include/exclude case studies or reviews)
- Deduplication and classification by arXiv ID and topic relevance
- Ready for local use, scripting, and expansion

## Example Usage
1. Clone the repo:
    ```bash
    git clone https://github.com/kkotysz/goose-recipes.git
    cd goose-recipes
    ```
2. Run a recipe (replace with your goose CLI invocation):
    ```bash
    goose recipe run hads-sxphe/recipe.yaml
    ```
3. Optionally, edit parameters or add your own recipes for other star types.

---
**MIT License** (c) 2026 Krzysiek
