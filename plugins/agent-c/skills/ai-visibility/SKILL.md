---
name: ai-visibility
description: Report how often ChatGPT, Claude, Gemini, Perplexity and other AI assistants name the business, using Agent C, and run a fresh check when asked. Use when the user asks whether AI recommends or mentions them, who AI names instead, how they're doing in AI search, or whether a fix they shipped worked.
argument-hint: "[recheck]"
---

# AI visibility with Agent C

1. Call the Agent C `visibility_status` tool and answer in a few plain sentences: how often AI names the business, the competitor named most, when it was last checked, and how many fixes are open.
   - If the tools aren't available or ask for sign-in, tell the owner to run `/mcp`, pick **agent-c** and sign in with their Agent C email. Then stop.
2. If there are open fixes, offer to make them in this repo (the `apply-fixes` skill).
3. Call `recheck` only when the owner asks (or `$ARGUMENTS` is `recheck`), or right after they say they've published a fix. It's refused within an hour of the last check; if so, say when they can try again. A check takes a few minutes, so tell them to ask again later rather than waiting.

Don't speculate about numbers Agent C didn't return.
