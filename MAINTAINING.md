# Maintaining the FAQ/wiki

There is no CI automation for this — no stored `ANTHROPIC_API_KEY`, no
GitHub Action calling an LLM on untrusted public input. Turning an answered
Q&A discussion into a wiki entry is a manual step, done locally, typically
with Claude Code's help against a clone of this repo. `wiki/` here is the
source of truth; `.github/workflows/wiki-sync.yml` (no AI, just a file
mirror) publishes it to the real GitHub Wiki whenever `wiki/**` changes on
`main`.

## The process

1. **Find answered questions that aren't in the FAQ yet.**

   ```
   gh api graphql -f query='
   query {
     repository(owner: "KevinMilesCode", name: "Dynasty-Engine") {
       discussions(first: 50, answered: true, orderBy: {field: CREATED_AT, direction: DESC}) {
         nodes { number title url answer { body } }
       }
     }
   }'
   ```

2. **Ask Claude Code to draft the entry.** Point it at the discussion
   (number or URL) and the current `wiki/FAQ.md` / `wiki/Home.md`, and ask it
   to fold the answer in — append a concise Q&A entry to `FAQ.md`, or (only
   for something substantial/reusable) add a new topic page and link it from
   `Home.md`. Same judgment call the old automated drafter made, just done
   by a person reviewing it in the moment instead of an unattended CI run.

3. **Review, commit, push.** Since it's a local change you're looking at
   directly before it goes anywhere, there's no separate PR-review gate the
   way the CI version needed one — you *are* the review step. Push to `main`
   and `wiki-sync.yml` publishes it.

## Why manual instead of automated

The earlier design (a GitHub Action firing on `discussion: answered`,
calling the Anthropic API with a stored key, opening a PR) was rejected in
favor of this — deliberately, not for lack of building it. Once the repo is
public, Q&A bodies are attacker-controlled text; running an unattended CI
job against that on every answered question, funded by a standing API key,
is a bigger blast radius than doing the same drafting step locally, on
demand, with a person reading the discussion before anything gets written.
