---
name: research-brief
description: Use when the user asks you to brief them on a company, product or market — "brief me on X", "what's the deal with X", "research X before our call". Runs a fixed search procedure and writes the result to a set shape.
---

# Writing a research brief

Triggered when someone wants to walk into a conversation informed. They want the brief, not a
transcript of your searching.

## Which tool

Use **`tavily_search`** for every step below, and `tavily_extract` to pull a single page in full.

Do **not** use `tavily_research`. It runs a deep-research agent that takes minutes, and a tool
call here is cut off after 30 seconds — the run fails rather than waits. Three quick searches
beat one long one anyway, and you control what each asks.

## The procedure

Run these as **separate `tavily_search` calls**. One broad search returns a summary you could
have guessed; three narrow ones return things the reader did not know.

1. **What it is** — the company or product, in its own words. Search the name plus "pricing" or
   "docs", not the name alone.
2. **What changed recently** — the last 6 months. Funding, launches, outages, leadership.
   Restrict the search to recent results.
3. **What people complain about** — search the name with "review", "vs", or "alternative".
   This is the step that produces the useful part of the brief.

If a result looks load-bearing but thin, pull that one page with `tavily_extract` rather than
trusting the snippet. One page, not a crawl.

## Check the dates

Search results bury their age. Before you use a fact, confirm when it was published, and say so
in the brief. A funding round from 2021 presented as current is the failure mode here.

## The output

Always these five sections, in this order, nothing else:

**What it is** — one sentence.
**Who it's for** — one sentence.
**Recent** — up to three bullets, each dated.
**Watch out for** — what the complaints agree on. Say "nothing consistent" if that's true.
**Unknown** — what you could not establish. Never leave this empty by guessing.

Keep the whole brief under 200 words. See `references/example-brief.md` for the shape.

## Do not

- Do not call `tavily_research`, or any tool that crawls a whole site. Both outlast the 30s limit.
- Do not cite a source you did not open.
- Do not fill **Unknown** with something you half-remember. Gaps are the honest part.
