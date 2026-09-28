# How to Adopt an Agentic AI Workflow for Mathematics (September 2026)

This is an essential and not particularly technical guide on how to create a harness for doing mathematical research.

Now that AI models can be used through their respective desktop apps, using a desktop app is the first step. This way, you can "connect" the models to a folder where you develop your project, giving them permission to modify the files and use your terminal for coding. In the GPT app, choose "Work" or use "Codex" (the first is better, since Codex is more oriented toward writing code).

One important advantage is that you can create the necessary coding environment for that project, which would not be available to the AI model online.

But first, let's understand what a "harness" is, as AI engineers use the term. Even though it takes a little time to read, I suggest reading [this article](https://www.anthropic.com/research/vibe-physics) (by a QFT scientist who supervised an AI in early 2025 as it pursued a PhD in theoretical physics) for a good narrative of the experience of writing the `.md` file to build the AI's harness.

## The "Harness": A Typical Structure for an Agentic Research Workflow

A typical folder structure is as follows:

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

The GOAL_PROMPT.md is the file containing the problem you want to solve, simulations you want to do, etc.., it is important to set a "goal condition", that is a condition that your AI model will have to meet before to stop working. (Do not worry if you interrupt its work, these set of files let you do interrupt the model and going back to it). Agents.md define the behavior of the agents, for example it is important to asking adversial agents to check the computations. These files has to be well written and detailed, adapted to the models you want to use(for example Astra or Sol), so they would ask a lot of work that you will retreat to the usual Chat. But it is not that drammatic as it could seem. The point is letting AI to prepare these files for you !

### How to prepare the AI
