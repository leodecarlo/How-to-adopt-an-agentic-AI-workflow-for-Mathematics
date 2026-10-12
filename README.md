# How to Adopt an Agentic AI Workflow for Mathematics (September 2026)

<p align="justify">
This is an essential and not particularly technical guide on how to create a harness for doing mathematical research.
</p>

<p align="justify">
Now that AI models can be used through their respective desktop apps, downloading a desktop app is the first step. In this way, you can "connect" the models to a folder where you develop your project, giving them permission to modify the files and use your terminal for coding. In the GPT app, choose "Work" or use "Codex" (the first is better, since Codex is more oriented toward writing code). Codex is OpenAI's coding agent for writing, reviewing, and debugging code; you can also use it in Visual Studio Code (VS Code) through the <a href="https://learn.chatgpt.com/docs/codex/ide">Codex extension</a>. Anthropic's equivalents are Claude Cowork for research and other general tasks, and <a href="https://code.claude.com/docs/en/vs-code">Claude Code</a> for coding, also available as a VS Code extension.
</p>

<p align="justify">
One important advantage is that you can create the necessary coding environment for that project, which would not be available to the AI model online.
</p>

<p align="justify">
But first, let's understand what a "harness" is, as AI engineers use the term. Even though it takes a little time to read, I suggest reading <a href="https://www.anthropic.com/research/vibe-physics">this article</a> (by a QFT scientist who supervised an AI in early 2025 as it pursued a PhD in theoretical physics) for a good narrative of the experience of writing the <code>.md</code> file (a plain-text file with simple Markdown formatting) to build the AI's harness.
The basic idea is that, in a long chat, LLMs get lost and lose track of information. Creating this harness helps keep them focused on the task.
</p>

<p align="justify">
If you prefer to avoid US companies and use an open model, I currently suggest Alibaba's Qwen for mathematics. <a href="https://qwenlm.github.io/qwen-code-docs/en/users/features/sub-agents/">Qwen Code already supports multi-agent workflows</a>, and Alibaba Cloud's low-cost <a href="https://www.alibabacloud.com/help/en/model-studio/token-plan-overview">Token Plan</a> can be used with it: the Lite subscription currently costs $8/month  and supports 1–2 concurrent agents. At the current promotional prices, Essential supports 2–3 concurrent agents for $16/month, Standard 3–4 for $25/month, and Pro 6–8 for $80/month.
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
The agent reads <code>AGENTS.md</code> and <code>GOAL_PROMPT.md</code> to understand its instructions and goal, then checks <code>PROGRESS.md</code> before continuing work. <code>AGENTS.md</code> can guide a single agent, but describing several roles in a file does not itself launch separate agents. The app must support subagent delegation. <strong>Multi-agent workflows are available on <a href="https://learn.chatgpt.com/docs/pricing">ChatGPT Plus (US$20/month)</a>; Ultra is not required.</strong> <a href="https://claude.com/pricing">Claude Pro (US$20/month when billed monthly)</a> includes Claude Code and <a href="https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork">Cowork</a>. How delegation starts depends on the app and mode:
</p>

| App or mode | How delegation works (October 2026) |
| --- | --- |
| [ChatGPT Work — most intelligence levels](https://learn.chatgpt.com/docs/agent-configuration/subagents) | Ask explicitly for separate subagents. |
| [ChatGPT Work — Ultra](https://learn.chatgpt.com/docs/agent-configuration/subagents) | Can delegate suitable work proactively when parallel agents would materially improve speed or quality. Availability depends on your account and model. |
| [Codex — current local clients (desktop app, CLI, and IDE extension)](https://learn.chatgpt.com/docs/agent-configuration/subagents) | Subagent tools are enabled by default. Ask directly, or request delegation in applicable `AGENTS.md` or skill instructions. |
| [Claude Code — subagents](https://code.claude.com/docs/en/sub-agents) | Claude can select built-in subagents automatically when appropriate; you can also request subagents explicitly. |
| [Claude Code — agent teams](https://code.claude.com/docs/en/agent-teams) | A separate experimental feature, disabled by default. Enable it first with `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1`; Claude can then form teams on request or when appropriate in an interactive session. |
| [Cowork](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork) | Can coordinate parallel subagents for complex tasks when appropriate. Cowork capabilities are also being integrated into the unified Claude experience. |

<p align="justify">
For a mathematical task, a useful explicit request is: <em>"Spawn separate agents to develop the proof, check the computations, and search for counterexamples; then reconcile their findings."</em> Check the app's agent activity to see which agents actually ran. If separate agents are unavailable, a single model can still simulate these roles, though this gives less separation between developing and checking a result.
</p>

<p align="justify">
The main agent records new findings in <code>RESEARCH_TRACKER.md</code>, unsuccessful approaches in <code>FAILURES.md</code>, and the final synthesis in <code>FINAL_REPORT.md</code>. Other files may be suitable for a particular task. For example, if you are doing a review, <code>REVIEW_BY_SECTION.md</code> may be more appropriate than <code>RESEARCH_TRACKER.md</code>.
</p>

<p align="justify">
<code>GOAL_PROMPT.md</code> is the file containing the problem you want to solve, the simulations you want to run, etc. The filename is just a convention and has no special connection to the app's "Goal" mode. It is important to set a "goal condition": a condition that your AI model must meet before it stops working. (Do not worry if you interrupt its work; this set of files lets you interrupt the model and return to it later.) <code>AGENTS.md</code> defines the behavior of the agents. For example, it is important to ask adversarial agents to check the computations. These files must be well written, detailed, and adapted to the models you want to use (for example, Astra or Sol), so preparing them would require a lot of work. But do not worry: AI is here to help you, so preparing them is not as daunting as it might seem. The point is to let AI prepare these files for you!
</p>

<p align="justify">
<strong>NOTE:</strong> You can also ask AI to create the same <code>.md</code> files remotely, on the provider's servers. Depending on the service, you may not have direct access to inspect or modify those files. The AI also cannot use a particular coding environment installed on your laptop; it can only use the tools and libraries available in the remote environment, which may be limited to a standard Python setup.
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
Note: I think there is a shortcircuit in these Lean certificates, although for some proofs in combinatorics or algebra they can be a good idea. In general, they seem tricky to me, since Lean code that compiles does not guarantee that the definitions in Lean correspond to yours or that the proofs in Lean are the same as those in the document.
</p>

## Learning to Prompt and Interact with LLMs

<p align="justify">
To learn more about prompting and interacting with LLMs, I suggest these three foundational courses from <a href="https://academy.openai.com/pages/courses">OpenAI Academy</a>:
</p>

1. [AI Foundations](https://academy.openai.com/public/courses/ai-foundations-dnq5w): giving clear instructions, adding useful context, and checking responses.
2. [Applied AI Foundations](https://academy.openai.com/public/courses/applied-ai-foundations-szsmv): turning individual tasks into repeatable workflows.
3. [Agents and Workflows](https://academy.openai.com/public/courses/agents-and-workflows-y0qoc): defining goals and boundaries, directing agents, and reviewing their results.

<p align="justify">
<strong>GOOD PROMPTING RULE1:</strong> To get a good prompt, explain to the AI in detail what you want, then ask it to write a prompt you can use to prompt it again!
</p>

<p align="justify">
<strong>GOOD PROMPTING RULE2:</strong> Whether you are using interactive chat or the agentic technique described here, do not reach for the highest apple straight away. Start with smaller, simpler problems or subproblems as a warm-up, then gradually work your way up to more challenging ones.
</p>

## Suggested Benchmarks for Choosing AI Models for Mathematics

<p align="justify">
Many mathematical benchmarks for LLMs exist. One that I suggest is <a href="https://epoch.ai/frontiermath/tiers-1-4?view=graph&amp;tab=release-date&amp;tier=Tier+4+%28v2%29">FrontierMath</a>, which is interesting because its Tier 4 problems are difficult that request a multi-step long time horizon. However, this benchmark suffers from data contamination from AI training. I also suggest <a href="https://matharena.ai/arxivmath/">ArXivMath</a>, which extracts self-contained questions with exact answers from recent arXiv results, such as propositions, and its companion <a href="https://matharena.ai/brokenarxiv/">BrokenArXiv</a>, which tests whether models recognize corrupted problems and false mathematical statements. BrokenArXiv originally used deliberately altered statements; <a href="https://matharena.ai/arxiv_august/">the updated benchmark</a> focuses on earlier claims and conjectures refuted by recent papers. Using recent papers helps reduce the risk of data contamination and makes these benchmarks useful for assessing models on up-to-date mathematics.
</p>

<p align="justify">
I also suggest following the <a href="https://arcprize.org/leaderboard">ARC Prize leaderboard</a> to track the evolution of models' spatial and temporal reasoning capabilities. In particular, ARC-AGI-3 tests agents in unfamiliar interactive environments, where they must learn through actions and feedback and plan over multiple steps.
</p>
