---
title: First post, demystifying agent evals
author: chchannn
pubDatetime: 2026-02-19T00:00:00Z
description: My first blog post, and agent evals.
tags:
  - journal
  - agent
  - evals
---

Today I finally set up this blog! 🎉

At work I continued on the Experiment Agent project. I'm at the phase of designing the evals for the subagents. Typically, the biggest headache for me is curating an evaluation dataset for this kind of task. IRL there is seldom a clean, well-structured dataset with clear signals immediately available. In the good old machine learning days — before 2025 — you either had to clean up dirty data or manually label. I hate both of these tasks.

Now with Claude Code, things are very different. After clarifying my task intention, with the help of a database MCP tool, it only took me about 30–40 mins to explore and identify a useful set of data to make an eval dataset. It may sound easy, but the dataset structure I was building was not trivial — they were from tuning chains, a series of optimization attempts. A row in the set was the step N → step N+1.

For the evals methodology I borrowed ideas from [Anthropic's evals guide](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents). This article introduced terminologies like grader and trial — very classroom and scientific research terms. If you've taken any experiment design course, you immediately know what they mean. The biggest inspiration I got was that you should set up 3 tiers of graders: code-based, model-based, and human-based. In this tier system, the complexity goes up and so does the cost.

Tomorrow I'll work on seeding the data into our dataset management tool LangSmith and building an evaluation harness. Last time it took me about an hour to build an eval harness for a grounding project, with 2 simple code-based metrics. This time I have 5 graders — 2 code-based, 3 model-based — much more complicated. Maybe I'll aim at finishing seeding the 3 datasets first.

In addition to my main project, I'm also on-call this week. I was paged 3 times at 7 this morning. Nothing was serious — lots of overly sensitive alerts. Regardless of the noise, on-call has honestly been easy because I can just throw the alerts and traces to our internal background coding agent to triage while I'm doing other tasks. Sonnet 3.5 could already do a decent job accurately triaging most incidents, and now with Opus it's only gotten better.

Today was my dear colleague Apollo's last day. I was very sad.