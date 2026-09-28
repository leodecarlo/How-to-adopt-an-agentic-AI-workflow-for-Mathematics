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

The agent reads `AGENTS.md` and `GOAL_PROMPT.md` to understand its instructions and goal, then checks `PROGRESS.md` before continuing work. It records new findings in `RESEARCH_TRACKER.md`, unsuccessful approaches in `FAILURES.md`, and the final synthesis in `FINAL_REPORT.md`. Other file that can be suitable for a task can added, for example if you are doing a review instead of a "RESEARCH TRACJER.md"  a "REVIEW_BY_SECTION.md" can be more adpat.

The GOAL_PROMPT.md is the file containing the problem you want to solve, simulations you want to do, etc.., it is important to set a "goal condition", that is a condition that your AI model will have to meet before to stop working. (Do not worry if you interrupt its work, these set of files let you do interrupt the model and going back to it). Agents.md define the behavior of the agents, for example it is important to asking adversial agents to check the computations. These files has to be well written and detailed, adapted to the models you want to use(for example Astra or Sol), so they would ask a lot of work that you will retreat to the usual Chat. But it is not that drammatic as it could seem. The point is letting AI to prepare these files for you !

### How to prepare the let AI preparing the Harnesse

Start a chat in Work mode(or the equivalent that let your model to write on your laptop and use your terminal). Make a first turn of warm-up where you ask the AI model the main file and main references of your interest. In the second turn describe in a technical way your problem, exactly as you would do to a collegue, and ask the AI to think about it to realize a "Plan" to solve it, in GPT you turn on the "Plan Mode" inside Work(One of the main things I learnt about prompting is that the best way to pronmpt is asking explaining what you want and asking AI a prompt to use it later. I observed that, with little doubt, the prompts for Math that OpenAI had pubblished was written by AI). And you copy in the chat the harness structure of .md files(as above) you want to prepare and ask to write it. The AI will tell you if you want to realize the plan, once you say "Yes" you will get the work done. After this you can inspect the various folder if you wants to change the problem statement, agent istructions, etc .. . 
Now that everything is settle the real thing has to come.

### How to get a first draft, develop and review it.

Now that the Harness is ready all you have to do is to ask AI to realize the goal, in GPT you activate the "Goal" mode inside work. (But Once the harness files are in the project folder, you can give Work a normal instruction such as: "Read AGENTS.md, GOAL_PROMPT.md, and PROGRESS.md. Carry out the next step toward the goal, check the result, and update the progress files."
Goal mode adds a persistent objective and a progress control so the desktop app can continue working across turns until it reaches a completion condition or needs input. A normal Work prompt guides the task you give it, and you can continue steering it in the same chat)

Now you can start to do something else or going out for a long walk. At your return you will have the first draft. At this point, you can as final audit to an external model, for example you can create a new folder and make with the same techniques a folder for the audit-review. Ideally you could use more than one model, for example, if you worked with GOT, using the API of Claude for this it can be  good idea. But also using again GPT, to not pay more, it is fine. After this, the unresponsbile prompeter can try to go for a submission for publishing.

The right way to use this techniqeu to explore ideas, for example you are doing this because you have an idea, but you serious gap to realize, trying to talk with peole will be very difficult , you have no idea from where to start reading all you need and probably you will get lost in the literature. So a first draft will help to understand if it is something that worths to pursued. If so you start reading, trying with AI (in the same chat or another) to understand what was done, and you start an interactions to learn, develop your paper and idea. 
Once you arrive at a finel result, you will have been the review.

Note: I do not believe in this Lean certificates, but for some proofs of Combinatorics or Algebra it can be a good idea, but in general to me it seems a silly thing, since a Lean code that compile does not guarantee that the definition in Lean corresponds to yours and that proofs in Lean are the same of the document.
