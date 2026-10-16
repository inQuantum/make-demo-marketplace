---
name: investigate-repo
description: Load this FIRST, before calling any repository, documentation or search tool, whenever asked what a public GitHub repository is, how it is built, or how one part of it works. It names which tools to use and in what order; going straight to a tool returns a vague answer.
---

# Investigating a repository

You have DeepWiki tools for public GitHub repositories. No connection is needed for them.

**Start looking immediately.** Do not ask which part of the repository they mean or how deep to
go — map it first and the answer usually becomes obvious. Keep each call narrow: a tool call is
cut off after 30 seconds.

1. **Map it first.** Ask for the repository's documentation structure. The topic list doubles as
   a map of its real subsystems, and is often a better answer to "what is this" than prose.
2. **Then ask narrow questions.** One per thing you actually need. "How does the scheduler pick
   the next job?" beats "explain the architecture".
3. **Say what is not there.** DeepWiki indexes public repositories only, and answers from the
   code as it stands. Naming a file you did not read is the one failure that matters.

For the write-up, follow `research-brief` — the same five sections work for a repository.
