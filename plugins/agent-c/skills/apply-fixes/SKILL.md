---
name: apply-fixes
description: Make Agent C's website fixes in this repository and leave every change for the owner to review. Use when the user asks to apply, make or work through Agent C fixes, or to fix what keeps their business out of ChatGPT, Claude, Gemini or other AI answers, in their site's code.
argument-hint: "[fix title or number, or blank for all]"
---

# Apply Agent C fixes

Agent C checks whether AI assistants name the business and writes the fix for each gap. Your job is to make those fixes in this repository. The owner reviews and publishes; you never do.

## Steps

1. Call the Agent C `list_fixes` tool. If it says the site hasn't been checked yet, stop and tell the owner to run a check in the Agent C app.
   - If the tools aren't available or ask for sign-in, tell the owner to run `/mcp`, pick **agent-c** and sign in with their Agent C email. Then stop.
2. If `$ARGUMENTS` names a fix (a title or its number in the list), do only that one. Otherwise work through every fix, one at a time.
3. For each fix, call `get_fix` with its `source` and `id`, then:
   - Find the file that renders the page under “Where it goes”. Search the repo for the page's URL path, its title or text already on it. Prefer the source (templates, components, content files) over built output.
   - Make the exact change. Keep the owner's wording and facts, and match how nearby code is written (the same markup, component or content format).
   - If the fix has placeholders like `[phone]` or `[hours]`, ask the owner for the real value. Never invent one.
   - If you can't find where it goes, or the fix is an off-site task (a directory listing, a review site), skip it and say why.
4. Check your work the way the fix's “How to check” section says, as far as you can without publishing (build the site, run its tests, or read the rendered file).

## Never

- Publish, deploy, merge, or push to the live branch. Leave a local change, or a draft pull request if the owner asks for one.
- Call `recheck` unless the owner asks. A check right after an unpublished change won't see it.

## When you're done

List each fix with the file you changed, then any you skipped and why. Tell the owner that once they publish, Agent C's next check will confirm it worked.
