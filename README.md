# goose-recipes

A collection of example and advanced recipes for the Goose/AAIF platform.

## Repository Structure

- Each topic directory contains:
    - `recipe.yaml`  — main recipe orchestrating a workflow
    - `subrecipes/` — set of supporting subrecipes for specialized or multi-step actions
    - other README/config/license files as needed

Example (this repository iteration):
- `hads-sxphe/` — a complete orchestrator and subrecipes for searching and analyzing HADS & SX Phoenicis star literature

## Features
- Recipes compatible with [Goose agent platform](https://github.com/aaif-goose/goose)
- Supports parameters, subrecipes, deduplication, classification
- Easy integration with MCP servers (e.g., arxiv-mcp-server for arXiv literature search)
- Ready to expand with your own topics and workflows

## Example Usage
1. Clone the repository:
    ```bash
    git clone https://github.com/kkotysz/goose-recipes.git
    cd goose-recipes
    ```
2. Run a recipe:
    ```bash
    goose recipe run DIRECTORY/recipe.yaml
    ```
    Replace `DIRECTORY` with any workflow/topic directory, e.g.: `hads-sxphe`
3. (Optional) Adjust parameters or add your own recipes/subrecipes.

---

## Additional requirement: MCP arXiv Server

Some recipes use the arXiv MCP server. Install it with:

```bash
uv tool install 'arxiv-mcp-server[pdf]'
```

To verify it works:
```bash
arxiv-mcp-server --help
```

When you run a recipe via goose (CLI/Desktop) with the proper `extensions` block, the server starts automatically. You may also launch it manually if needed:

```bash
uv tool run arxiv-mcp-server --storage-path /your/path/to/arxiv-papers
```

---
**MIT License** (c) 2026 krzkot
