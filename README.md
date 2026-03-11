# Practical Advice for the Math Community on Using AI

I am a math PhD candidate at UC San Diego. The first three years of my PhD were in pure math, and after that I switched into large language model research. I now work full time at Amazon AWS as an applied scientist on AI.

This note is meant to be practical. I am not trying to answer big-picture questions like whether AI will replace mathematicians, or what AI means for the long-term future of mathematics. There is already plenty of discussion in that direction. What I want to do here is much more down to earth: concrete advice on how people in the math community can use current AI tools to help with day-to-day work.

## Sections

| Section | What it covers |
| --- | --- |
| [1. What basic AI tools are available?](#1-what-basic-ai-tools-are-available) | Chatbots, pro tiers, reasoning modes, agents, and base models |
| [2. What tasks can agents do?](#2-what-tasks-can-agents-do) | Proof work, proofreading, search, literature review, coding, and more |
| [3. How should you use agents most effectively?](#3-how-should-you-use-agents-most-effectively) | Installation, workflows, multiple agents, and advanced usage |
| [4. What if I do not know how to install or use these tools, or I run into problems?](#4-what-if-i-do-not-know-how-to-install-or-use-these-tools-or-i-run-into-problems) | Using AI itself as the tutor, debugger, and setup assistant |

## 1. What basic AI tools are available?

The easiest AI tools to access are the ordinary chatbot products: the free versions of ChatGPT, Gemini, or Claude. These are the simplest entry point. You open a website, type a question, and chat back and forth. For many people, this is the first and most natural way to try AI. The main advantage is convenience. The main disadvantage is quality: the free versions are usually the weakest versions.

The next step up is the paid or "pro" tier of those same products. This usually gives you access to better models, higher usage limits, and extra modes that are more capable on difficult tasks. I would still group both the free and paid versions into the same broad category: chatbots. The interface is still fundamentally a chat window, and the model mainly helps by answering prompts interactively.

Many of these chatbot products now also have stronger reasoning modes, often called things like "Deep Think," "Extended Thinking," or something similar. The idea is simple: instead of replying quickly, the system spends more effort on harder problems. For mathematical or technical work, this often helps. If you are asking for a proof sketch, checking edge cases, comparing definitions, or debugging a derivation, it is often worth turning on the stronger thinking mode.

A different category is the agent. Good examples are Codex and Claude Code. These are not just chatbots with a different name. A chatbot mostly answers what you ask in the conversation window. An agent can take a larger task, work through multiple steps, inspect files, write or edit files, run commands, revise its approach, and keep going until the task is actually completed. In other words, the agent is closer to a junior collaborator who can act, not just respond.

The biggest practical difference is tool use. Good agents often have access to tools that ordinary chatbots do not reliably have access to. For example, they may be able to use `bash` (the standard Unix command-line shell), run Python, edit files, search through folders, compile documents, or interact with other software systems. In many research settings, that kind of tool use is what makes the system genuinely useful. A model that can call Python or MATLAB, inspect your LaTeX files, run a script, and then revise its own output is much more powerful than a model that can only type text back to you in a browser tab.

This difference matters a lot in practice. If you only want a quick explanation of a theorem, a chatbot may be enough. But if you want to reorganize notes, clean up a LaTeX project, convert handwritten arguments into a structured draft, build a small experiment, write code for numerical checks, or iterate on a long technical document, the agent workflow is usually much better. The benefit is not just better answers. The benefit is that the system can actually do a multi-step job with real tools.

It is also useful to know the term base model. Roughly speaking, the base model is the underlying model doing the actual reasoning and generation. The product you use, such as a chatbot or an agent, is the interface and workflow layer around that model. So two tools may feel very different in use even if they are built on similarly strong underlying models.

As of March 11, 2026, my practical recommendation for people in mathematics is to start with Codex or Claude Code if you want the strongest public option. There may well be even more specialized agents inside companies or research labs that are not publicly available yet, but for tools that ordinary users can actually access, these are currently the most serious options I would point people toward. Exact rankings change quickly, and different people will disagree at the margin, but the main conclusion is simple: if you want the best performance on technical, multi-step work, use a strong agent rather than an ordinary chatbot tab.

## 2. What tasks can agents do?

The short answer is that agents are especially useful for long-horizon tasks. By that I mean tasks that are not solved in one prompt, but instead require many steps, backtracking, checking, rewriting, and combining different tools. This is exactly the kind of work that shows up all the time in mathematics.

Here are some of the most useful categories.

### Proofreading and writing

If you give an agent a set of notes, a draft paper, or a thesis chapter, it can look for unclear sentences, notation that changes halfway through, missing assumptions, undefined symbols, duplicated lemmas, bad references, or places where the exposition is much harder to follow than it needs to be. A normal chatbot can comment on a pasted paragraph. An agent can work through the whole document, keep track of notation, and propose edits in a more systematic way.

### Proof work

Current AI agents can already prove nontrivial mathematics. This is not hype. It is already happening. See, for example, https://www-cs-faculty.stanford.edu/~knuth/papers/claude-cycles.pdf, where Claude solved an open research problem. So the right mental model is not that these systems only help with routine exercises. They can already contribute to serious mathematical reasoning.

In proof work, an agent can:

- test whether a proof outline has gaps
- suggest special cases to check
- look for counterexamples to an overstrong claim
- rewrite a sketch into a more structured argument
- compare several possible proof strategies
- translate an argument into a cleaner form

Sometimes it can produce the full proof. Sometimes it produces a key lemma, a counterexample, or the right next idea. Even when it does not produce the final proof, it can still move the work forward in a substantial way.

### Mathematical search and literature review

Agents are also useful for mathematical search. Suppose you vaguely remember that a certain theorem, inequality, or construction exists, but you do not remember the exact name. Or suppose you want examples of a phenomenon, standard counterexamples, or several formulations of a definition from different sources. An agent can search, summarize, compare sources, and keep refining the search as it learns what you actually mean. This is much closer to how a human researcher works than a single search box query.

Literature review is another strong use case. If you want to get oriented in a new area, an agent can collect papers, identify recurring themes, summarize what each paper contributes, compare assumptions across papers, and organize the material into a more useful map. For example, if you are entering a topic in probability, PDE, optimization, or LLM theory, you can ask the agent to build a first-pass reading guide: what the foundational papers are, what the modern directions are, which techniques appear repeatedly, and where the main open questions seem to be.

### Explaining papers and concepts

Many papers are technically correct but extremely inefficient to read. An agent can translate a dense paper into plain language, explain the motivation before the formal statements, unpack notation, expand compressed arguments, and identify which parts are central and which parts are technical bookkeeping. This can save a lot of time, especially when you are trying to decide whether a paper deserves a full careful read.

### Everyday research support

There are also many smaller but still important tasks. Agents can help:

- reorganize lecture notes
- turn rough bullet points into a seminar handout
- prepare a first draft of slides
- generate examples and non-examples for a definition
- build small computational experiments
- write code to test a conjecture numerically
- clean up bibliographies
- standardize notation across files
- convert between informal notes and LaTeX
- produce structured reading summaries for a paper group or student seminar

For people doing applied or computational work, the usefulness is even broader. An agent can write Python scripts, check data formatting, run quick experiments, visualize outputs, compare model settings, or help maintain the surrounding research codebase. Even for pure mathematicians, this matters more than people sometimes expect, because a lot of mathematical work is really document work, search work, and organization work.

The main pattern is simple: agents are best when the task has many moving pieces. If the job requires reading a lot, keeping track of context, using tools, trying several approaches, and gradually improving the result, agents are often very effective.

## 3. How should you use agents most effectively?

The first practical step is to install a real agent on your computer, such as Claude Code or Codex, and get comfortable using it from the command line. If you are not familiar with the command line yet, you should become familiar with it. That is where a lot of the real power is. In the same spirit, you should also be familiar with GitHub, because a large fraction of useful open-source AI tools for mathematics either live on GitHub or are distributed through GitHub.

This is also why I want to emphasize again that agents are better than chatbots for serious use. A chatbot mostly lives inside a website tab. An agent lives inside your actual working environment. It can see files, edit files, run commands, call tools, and carry out a task over many steps. For mathematical work, that difference is often decisive.

### A good default workflow

One very effective habit is to use different agents for different tasks. Do not assume one single agent run should do everything.

For example:

- use one agent to attempt a proof
- use another agent to verify the proof
- feed the criticism back into the first agent
- repeat the loop

Or:

- use one agent to explain a paper
- use another to check whether the explanation missed assumptions, misread notation, or skipped technical subtleties

In practice, a loop of propose, verify, revise, and repeat is often much stronger than relying on one single agent run.

### Use multiple terminal windows

You should also get used to opening multiple agents in different terminal windows. This is a simple but powerful workflow.

For example, one window can be:

- doing proof search
- checking a draft
- searching the literature
- running code or numerical experiments

Once you start doing this, the agent feels much less like a chatbot and much more like a small research workflow running in parallel.

### More advanced usage

There are also more advanced ways to use agents. For example, you can write bash scripts that chain multiple agent calls together. This lets you build larger pipelines instead of manually supervising every step.

For an example in this direction, see my repository:

https://github.com/chenyang-an/one_click_textbook_to_lean

That kind of workflow can become very powerful for things like proofreading pipelines, formalization pipelines, or repeated verification loops.

That said, I would not recommend jumping into the advanced setups immediately. First get comfortable with the basics:

- install the agent
- use it from the terminal
- give it well-scoped tasks
- inspect the output carefully
- learn its strengths and failure modes

Once that feels natural, the more automated workflows will make much more sense.

So my advice to the math community is simple: try agents seriously. Do not judge them only from a few chatbot interactions in a browser. Use them as actual tools on your computer. In my view, agents are already much more useful than chatbots for many real mathematical tasks, and that advantage becomes even clearer once you learn how to use them well.

## 4. What if I do not know how to install or use these tools, or I run into problems?

This is actually one of the best parts: you can ask AI how to use AI.

If you do not know how to install Claude Code, Codex, Python, Lean, LaTeX, or some package you need, ask an agent. If you do not know what a terminal is, ask an agent. If you do not know what `bash` is, ask an agent. If GitHub feels confusing, ask an agent. If a command fails with an error message, paste the error into the agent and ask what went wrong. If something installed correctly yesterday but breaks today, ask the agent to help you debug it.

This sounds almost silly at first, but it is genuinely one of the most useful workflows. These systems are often very good at onboarding, setup, troubleshooting, and explaining software environments step by step. In many cases, the fastest way to learn the tool is to use the tool to teach you how to use it.

Here are examples of questions worth asking.

- "I am a mathematician and I have never used the terminal before. How do I install Claude Code on my laptop?"
- "I installed Python, but when I type `python` it says command not found. What should I do?"
- "I am trying to use GitHub for the first time. Explain what `git clone`, `git pull`, and `git push` mean in plain English."
- "I have a LaTeX project in this folder. How do I ask Codex to help me proofread it?"
- "I want one agent to draft a proof and another to verify it. What is a good workflow for that?"
- "I opened three terminal windows with different agents and now I am confused about how to organize them. Give me a simple workflow."
- "This Lean installation is failing. Here is the error message. Can you tell me exactly what to try next?"
- "I found a math AI project on GitHub. Explain the README to me and tell me what commands I need to run."
- "I want to write a bash script that sends the same task to multiple agents. Show me a minimal example."

You can also ask for very concrete guidance. Ask the agent to explain things assuming no background. Ask it to give copy-pasteable commands. Ask it to explain what each command does before you run it. Ask it to suggest the safest next step. Ask it to tell you how to undo a mistake. Ask it to summarize the difference between several installation options. These are all good uses.

So if you feel blocked because the tooling looks unfamiliar, do not treat that as a reason to avoid these systems. Treat it as one of the first problems to hand to the systems. In many cases, AI is not only the tool you are trying to learn. It is also the tutor, debugger, and setup assistant that helps you learn it.
