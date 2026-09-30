# How to Adopt an Agentic AI Workflow for Mathematics (September 2026)

<p align="justify">
This is an essential and not particularly technical guide on how to create a harness for doing mathematical research.
</p>

<p align="justify">
Now that AI models can be used through their respective desktop apps, downloading a desktop app is the first step. In this way, you can "connect" the models to a folder where you develop your project, giving them permission to modify the files and use your terminal for coding. In the GPT app, choose "Work" or use "Codex" (the first is better, since Codex is more oriented toward writing code).
</p>

<p align="justify">
One important advantage is that you can create the necessary coding environment for that project, which would not be available to the AI model online.
</p>

<p align="justify">
But first, let's understand what a "harness" is, as AI engineers use the term. Even though it takes a little time to read, I suggest reading <a href="https://www.anthropic.com/research/vibe-physics">this article</a> (by a QFT scientist who supervised an AI in early 2025 as it pursued a PhD in theoretical physics) for a good narrative of the experience of writing the <code>.md</code> file to build the AI's harness.
The basic idea is that, in a long chat, LLMs get lost and lose track of information. Creating this harness helps keep them focused on the task.
</p>

## The "Harness": A Typical Structure for an Agentic Research Workflow

<p align="justify">
A typical folder structure is as follows:
</p>

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

<p align="justify">
The agent reads <code>AGENTS.md</code> and <code>GOAL_PROMPT.md</code> to understand its instructions and goal, then checks <code>PROGRESS.md</code> before continuing work. It records new findings in <code>RESEARCH_TRACKER.md</code>, unsuccessful approaches in <code>FAILURES.md</code>, and the final synthesis in <code>FINAL_REPORT.md</code>. Other files may be suitable for a particular task. For example, if you are doing a review, <code>REVIEW_BY_SECTION.md</code> may be more appropriate than <code>RESEARCH_TRACKER.md</code>.
</p>

<p align="justify">
<code>GOAL_PROMPT.md</code> is the file containing the problem you want to solve, the simulations you want to run, etc. The filename is just a convention and has no special connection to the app's "Goal" mode. It is important to set a "goal condition": a condition that your AI model must meet before it stops working. (Do not worry if you interrupt its work; this set of files lets you interrupt the model and return to it later.) <code>AGENTS.md</code> defines the behavior of the agents. For example, it is important to ask adversarial agents to check the computations. These files must be well written, detailed, and adapted to the models you want to use (for example, Astra or Sol), so preparing them would require a lot of work. But do not worry: AI is here to help you, so preparing them is not as daunting as it might seem. The point is to let AI prepare these files for you!
</p>

### How to Let AI Prepare the Harness

<p align="justify">
Start a chat in Work mode (or the equivalent that lets your model write to your laptop and use your terminal). In the first turn, as a warm-up, ask the AI model to look at the main file and the main references that interest you. In the second turn, describe your problem technically, exactly as you would to a colleague, and ask the AI to think about it and devise a "Plan" to solve it. In GPT, turn on "Plan Mode" inside Work. (One of the main things I have learned about prompting is that the best way to prompt is to explain what you want and ask the AI to write a prompt for you to use later. I am almost certain that the prompts for mathematics published by OpenAI were written by OpenAI's own AI models.) Then copy the structure of the <code>.md</code> harness files you want to prepare (as above) into the chat and ask the AI to write them. The AI will ask whether you want it to carry out the plan; once you say "Yes," the work will be done. After this, you can inspect the various folders and files if you want to change the problem statement, agent instructions, etc.
</p>

<p align="justify">
Now that everything is settled, the real work begins.
</p>

## How to Get a First Draft, Develop It, and Review It

<p align="justify">
Once the harness is ready, all you have to do is ask the AI to pursue the goal. In GPT, activate "Goal" mode inside Work. But once the harness files are in the project folder, you can also give Work a normal instruction such as "Read AGENTS.md, GOAL_PROMPT.md, and PROGRESS.md. Carry out the next step toward the goal, check the result, and update the progress files." Goal mode adds a persistent objective and a progress control so the desktop app can continue working across turns until it reaches a completion condition or needs input. A normal Work prompt guides the task you give it, and you can continue steering it in the same chat.
</p>

<p align="justify">
Now you can start doing something else or go out for a long walk. When you return, you will have the first draft. At this point, you can ask an external model for a final audit. For example, you can create a new folder and, using the same techniques, prepare it for the audit and review. Ideally, you could use more than one model. For example, if you worked with GPT, using Claude's API for this could be a good idea. But using GPT again is also fine if you do not want to pay more. After this, an irresponsible prompter might try to submit the draft for publication.
</p>

<p align="justify">
The right way to use this technique is to explore ideas. For example, you might have an idea but face a serious gap in realizing it. Trying to talk with people may be very difficult; you may have no idea where to start reading everything you need, and you will probably get lost in the literature. A first draft can help you understand whether the idea is worth pursuing. If so, start reading the draft and use AI (in the same chat or another) to understand what was done. Then continue interacting with AI to learn and develop your paper and idea. By the time you reach a final result, you will have done the review yourself.
</p>

<p align="justify">
Note: I do not believe in these Lean certificates, although for some proofs in combinatorics or algebra they can be a good idea. In general, they seem silly to me, since Lean code that compiles does not guarantee that the definitions in Lean correspond to yours or that the proofs in Lean are the same as those in the document.
</p>

## Learning to Prompt and Interact with LLMs

<p align="justify">
To learn more about prompting and interacting with LLMs, I suggest these three foundational courses from <a href="https://academy.openai.com/pages/courses">OpenAI Academy</a>:
</p>

1. [AI Foundations](https://academy.openai.com/public/courses/ai-foundations-dnq5w): giving clear instructions, adding useful context, and checking responses.
2. [Applied AI Foundations](https://academy.openai.com/public/courses/applied-ai-foundations-szsmv): turning individual tasks into repeatable workflows.
3. [Agents and Workflows](https://academy.openai.com/public/courses/agents-and-workflows-y0qoc): defining goals and boundaries, directing agents, and reviewing their results.

<p align="justify">
<strong>GOOD PROMPTING RULE:</strong> To get a good prompt, explain to the AI in detail what you want, then ask it to write a prompt you can use to prompt it again!
</p>

## Suggested Benchmarks for Choosing AI Models for Mathematics

<p align="justify">
Many mathematical benchmarks for LLMs exist. One that I suggest is <a href="https://epoch.ai/frontiermath/tiers-1-4?view=graph&amp;tab=release-date&amp;tier=Tier+4+%28v2%29">FrontierMath</a>, which is interesting because its Tier 4 problems are difficult that request a multi-step long time horizon. However, this benchmark suffers from data contamination from AI training. I also suggest <a href="https://matharena.ai/arxivmath/">ArXivMath</a>, which is particularly interesting because it extracts short problems, such as propositions, from recent arXiv papers. This avoids data contamination and makes it useful for assessing models' ability to prove results in up-to-date mathematics.
</p>
