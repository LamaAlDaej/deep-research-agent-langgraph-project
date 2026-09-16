# AI Research Agent — Project Starter

One self-contained notebook: **researcher → analyst → writer**. You build
the three agents with LangChain 1.x `create_agent` and chain them with
LangGraph's Graph API (`StateGraph`). Finish three TODOs — write the system
prompts (TODO #1), build the agents (TODO #2), build the pipeline (TODO #3).

## My Project: Multi-Agent Deep Research System

I extended the original three-agent pipeline into a **six-agent deep research system**:

1. **Research Planner** — breaks the main question into focused research tasks.
2. **Opportunity Researcher** — searches for benefits, successful examples, and supporting evidence.
3. **Risk Researcher** — searches for risks, limitations, and counter-evidence.
4. **Research Analyst** — combines and compares both sets of findings.
5. **Quality Checker** — decides whether the evidence is sufficient or more research is needed.
6. **Report Writer** — produces the final evidence-based report.
   

### Why This Design?

The two researchers work **in parallel** to reduce execution time and provide balanced perspectives. The Quality Checker reviews the evidence before writing. If important information is missing, the workflow returns to the Planner for a targeted research round.
The workflow also includes bounded revisions, source checks, tool and model-call limits, loop detection, tracing, and in-memory checkpointing for improved reliability.

**Workflow:** Planner → Parallel Opportunity and Risk Research → Analyst → Quality Checker → Report Writer or Targeted Research Retry


## Google Colab (easiest)

1. Open `research_agent.ipynb` in Colab.
2. Add a secret named `OPENROUTER_API_KEY` (key icon in the left sidebar).
3. Finish the TODOs, then `Runtime → Run all`.

## On your own machine

```bash
uv sync
cp .env.example .env   # open .env and paste your OPENROUTER_API_KEY
uv run jupyter lab research_agent.ipynb
```

## How to submit

1. **Fork** this repository (Fork button, top-right on GitHub).
2. **Clone your fork**, open the notebook, and finish the three TODOs.
3. **Commit and push** your work to your fork:
   ```bash
   git add research_agent.ipynb README.md
   git commit -m "Finish research agent project"
   git push
   ```
   Never commit your `.env` file — it holds your API key (it is already in `.gitignore`).
4. **Tag the academy** so we can find your submission: edit the bottom of your fork's `README.md`, add this line, then commit and push again:
   ```markdown
   Submitted by: <your name> — academy: @SDAIAAcademy
   ```
5. Your submission is complete when your fork's last commit contains your finished `research_agent.ipynb` and the README line above. Grading follows `EVALUATION.md`.

## Structure

```
project_starter/
├── research_agent.ipynb   # the whole project (helpers given, 3 TODOs inside)
├── EVALUATION.md          # Grading rubric for the project
├── pyproject.toml         # Dependencies (for local runs)
├── .env.example           # Environment variable template (local runs)
├── .gitignore             # Keeps .env and local caches out of git
└── uv.lock                # Locked dependency versions
```

## Quick reference

```bash
uv sync                                  # install dependencies
uv run jupyter lab research_agent.ipynb  # open the project
```

Submitted by: Lama AlDaej — academy: [@SDAIAAcademy](https://github.com/SDAIAAcademy)
