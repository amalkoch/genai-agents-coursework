# 06 · AI Agents Coursework (Notebooks)

Jupyter/Colab notebooks from a course on generative AI and agents, covering prompting, LangChain, agents, RAG, LangGraph and multi-agent systems.

**Source:** `~/Downloads/`, `~/Desktop/` (exact duplicates were merged)
**Stack:** Python, Jupyter/Colab, OpenAI API, LangChain, LangGraph

| Module | Notebook (in `notebooks/`) |
|---|---|
| M3 | `M3_Lab1_Prompting_Strategies.ipynb` |
| — | `Prompting_with_API.ipynb` |
| M5 | `M5_Lab2_LangChain_Templates_Memory.ipynb` |
| M6 | `M6_Lab1_AI_Agents.ipynb` |
| M8 | `M8_Lab1_RAG.ipynb` |
| M10 | `M10_Lab1_LangGraph_Intro.ipynb` |
| M11 | `M11_Lab2_Multi_Agent_Investment_Analysis.ipynb` |

### `world-cup-chatbot/`: final project
A RAG + LangGraph agent that answers World Cup history questions, predicts matches and simulates all 104 matches of 2026. It holds the notebook, `src/` (agent, chains, ingest, tools, vectorstore, bracket_generator), `data/` (CSVs and a prebuilt FAISS index), `teams.json`, `matches.json`, `requirements.txt` and `Presentation.pptx`. See `world-cup-chatbot/README.md`.

## Security
The notebooks load the OpenAI key from a Colab secret, which is the right approach. But the setup cell's last line had printed the key into a saved output. **Those 7 outputs were removed from these copies.** The original notebooks in Downloads/Desktop still contain the key, and it was saved in files that may have been shared, so **rotate that OpenAI key**.

## Run
Open the notebooks in Jupyter or upload them to Google Colab.

## Status (checked 2026-11-07)
**🟢 Complete**, with one failed cell.
| Notebook | State |
|---|---|
| M3, M5, M6, M10, M11, Prompting_with_API | ✅ Every cell has been run, no errors |
| M8 RAG | 🟡 30 of 31 cells ran. Cell 23 failed with `NameError: DEFAULT_MINI_MODEL` (the kernel probably restarted). Re-run the setup cell, then cell 23 |
| World Cup chatbot | ✅ Fully run. Only the optional `interactive_chat` cell is left unrun on purpose |
- 🧹 **Removed** 3 blank, never-run course templates (M3, M6, M8 from Downloads). The completed versions were renamed to the plain names.
- 🔧 **Fixed the World Cup project.** The submitted `code/` folder was flat, but the notebook imports `src.*` and reads `data/`. I rebuilt it as `world-cup-chatbot/` with `src/` and `data/` and pointed the FAISS cache at `data/faiss_index/`. `load_project_data()` loads 48 teams and 104 matches. LangChain isn't installed on this Mac, so the full notebook hasn't been re-run here.
- 🔒 The leaked key outputs were removed from all 7 lab notebooks. See Security above.
