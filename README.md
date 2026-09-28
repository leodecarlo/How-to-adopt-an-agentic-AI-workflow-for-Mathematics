# How-to-adopt-an-agentic-AI-workflow-for-Mathematics (September 2026)

This an essential and  not particularly technical guide on how to  to create the harness for doing Mathematical Research.

Now AI models can be used trough their respective desktop apps, this is the first step. In this way you can "connect" the models to a folder where you develop your project, giving the permission to modify the file and use your terminal for coding. In GPT app you choose the  "Work" or use "codex" (the first is better since "codex is more oriented to write code"),
One important advantge is that you can create a necessary coding  environment for that project that onlie would not be available to the AI model. 

But first let's start to understand what is the "harness" that AI engineer are used to say. Even it takes a bit to read, I suggest to read [this article](https://www.anthropic.com/research/vibe-physics) (from a QFT scientist who supervised early in 2025 an AI to get its Phd in theoretical physics)  to have good narrative of the experience about writing the .md file for building the harness for the AI. 

## The "Harness": Typical structure for an agentic research workflow

A typical folderstructure is as follow:

```text
project/
├── README.md                 # Overview and how to navigate the project
├── AGENTS.md                 # Instructions for the AI agent
├── GOAL_PROMPT.md            # Research goal and criteria for completion
├── PROGRESS.md               # Current checkpoint and next steps
├── RESEARCH_TRACKER.md       # Open questions, decisions, and references
├── FAILURES.md               # Attempts that did not work and why
├── FINAL_REPORT.md           # Consolidated results and remaining gaps
├── main files/               # Core project files
├── auxiliary files/          # Supporting material and references
├── computations/             # Scripts and computational checks
├── notes/                    # Working notes and derivations
└── generic output folder/    # Generated PDFs, figures, and other outputs
```

The agent reads `AGENTS.md` and `GOAL_PROMPT.md` to understand its instructions and goal, then checks `PROGRESS.md` before continuing work. It records new findings in `RESEARCH_TRACKER.md`, unsuccessful approaches in `FAILURES.md`, and the final synthesis in `FINAL_REPORT.md`.


