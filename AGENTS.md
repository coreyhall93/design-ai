# Agent Notes — design-ai (Sol reference)

## Read Order

**For using the design systems** (the main purpose of this library):
1. `FUTURE_COREY.md` — current local state and resume steps
2. `README.md` — upstream overview + full index of available companies
3. The specific target: `design-md/<slug>/DESIGN.md` (e.g. `design-md/linear/DESIGN.md`)
4. `CONTEXT.md` — why we maintain this fork
5. `.github/workflows/upstream-sync.yml` — only if modifying the automation

**When the task is about maintaining the fork itself** (adding custom designs, pulling updates, handling syncs, "I made changes now what?"):
- Start with `FUTURE_COREY.md`
- Then jump directly to the section in **this file** titled `## Managing the Fork & Upstream Syncs (First-timer / Agent Guide)`
- That section contains the practical commands, branch workflow, safe places for personal additions, and conflict guidance. It was written specifically because Corey relies on AI agents for this kind of work and will forget the details.

## Guidance

- **Primary use case**: When asked to "build this in the style of X" or "match the Stripe / Figma / Linear / Apple design system", locate the matching DESIGN.md here (or in the personal GitHub fork) and have the user (or the target project) copy it in as the source of truth.
- Prefer references from `~/Sol/02-Projects/design-ai/` or `https://github.com/coreyhall93/design-ai` so that updates flow through our controlled sync process.
- The files are intentionally human + LLM readable. Quote or inline relevant sections (color roles, typography scale, component rules, do's/don'ts, agent prompt guide) when giving instructions to other agents or models.
- If a requested brand is missing, the cleanest path is usually:
  1. Open an issue on the upstream repo (https://github.com/Khalidabdi1/design-ai) using their request template, or
  2. Create a local `design-md/my-internal-brand/` following the 9-section structure documented in upstream `CONTRIBUTING.md` and `README.md`.
- Do not suggest committing the entire `design-md/` tree into random projects. The value is selective reuse of individual DESIGN.md files.
- The preview HTML files (when present) can be opened in a browser for quick visual confirmation of the documented tokens and components.

## Local vs Upstream

- Upstream = the canonical, community-curated collection.
- This fork = our always-available local mirror + any personal extensions.
- Sync PRs on the GitHub fork are the mechanism that keeps the two aligned. Merge them deliberately.

## Managing the Fork & Upstream Syncs (First-timer / Agent Guide)

**This section exists specifically because Corey relies heavily on AI agents (Claude, Codex, Grok, etc.) for GitHub and coding work and will not remember the mechanics.**

When an agent is asked to help with this project in a maintenance capacity ("add my custom design", "pull latest designs", "I made some changes, now sync it"), come to this section first.

### Core Mental Model (very important)

- `coreyhall93/design-ai` (your fork on GitHub) is *your* controlled copy.
- `main` on your fork (and in the local clone) is the "blessed" version that contains:
  - Everything accepted from upstream, **plus**
  - Any personal additions or custom design systems you have added.
- Upstream changes from `Khalidabdi1/design-ai` are **never** forced directly onto your `main`. They are **proposed** via automated Pull Requests created by the workflow in `.github/workflows/upstream-sync.yml`.
- You (or an agent helping you) decide when to accept upstream changes by merging those PRs.
- Git will **never** silently overwrite your work. If there is a conflict, it will stop and require resolution.

### Always Start Here (exploration commands)

```bash
cd ~/Sol/02-Projects/design-ai

git remote -v          # Should show: origin = your fork, upstream = the original
git status
git branch -a
git log --oneline -10
```

### How to Pull the Latest from Upstream (the normal flow)

1. Go to your fork: https://github.com/coreyhall93/design-ai
2. Look in the Pull Requests tab for an open PR titled **"chore: sync with upstream design-ai"**.
3. Review the "Files changed" tab (new companies are almost always safe and additive).
4. Merge the PR on GitHub. This updates your fork's `main` branch.
5. Locally pull the update:

   ```bash
   cd ~/Sol/02-Projects/design-ai
   git pull
   ```

You can force a manual sync check at any time (instead of waiting for the daily 06:00 UTC run):

- On GitHub: Actions tab → "Sync with upstream" workflow → click **"Run workflow"** button.

### How to Make Your Own Changes or Add Custom Design Systems (safe first-timer way)

**Rule:** Prefer working on a feature branch instead of editing `main` directly.

```bash
cd ~/Sol/02-Projects/design-ai

# Create and switch to a new branch for your work
git checkout -b add/my-custom-brand

# Do your thing — e.g. add a completely new design system
mkdir -p design-md/local/my-internal-tool
# ... create DESIGN.md (and preview HTMLs if you want) following the 9-section format ...

git add .
git commit -m "Add my-internal-tool design system"

# Push the branch to your fork
git push origin add/my-custom-brand
```

After pushing the branch, you can:
- Open a Pull Request on GitHub from `add/my-custom-brand` → `main` (if you want the change on main), **or**
- Just leave the branch around for reference / future agents.

### Recommended Location for Your Personal / Custom Additions

Put anything that is *not* meant for the public upstream under a dedicated subdirectory that the original repo will never touch:

```text
design-md/local/
design-md/personal/
design-md/corey/
```

Example path:
`design-md/local/my-saas-product/DESIGN.md`

**Why this matters:** Upstream will never create or edit files inside `design-md/local/`, so future syncs will almost never produce conflicts with your custom work.

### What Happens When Both You and Upstream Have Changes?

- The sync workflow checks out your current `main`, creates/resets the `chore/sync-upstream` branch from it, then merges `upstream/main` into that branch.
- Clean cases (new folders, files you never touched) → automatic, no problem.
- Overlapping edits on the exact same lines of the exact same file → Git creates a **merge conflict**.
  - The conflict will be visible in the GitHub PR (or in your local working tree if you merge manually).
  - You must resolve it (edit the file to remove the `<<<<<<<` markers, keep the version(s) you want, then `git add` + commit).
- Your unique work is never deleted without you seeing it and approving the resolution.

The workflow is deliberately written to continue even when conflicts exist, so the PR gets created and the conflicts become visible for resolution.

### Local Manual Sync (if you ever need to do it by hand)

```bash
cd ~/Sol/02-Projects/design-ai
git fetch upstream
git checkout -B chore/sync-upstream main
git merge upstream/main
# If conflicts appear, resolve them now, then:
git add .
git commit -m "chore: manual sync with upstream"
git push origin chore/sync-upstream
# Then go to GitHub and create a PR from chore/sync-upstream to main
```

The automated Action + PR flow is strongly preferred.

### When Helping Corey (agent instructions)

- For any task involving "update the designs", "I added something", "sync my fork", "pull latest", or "I made changes to design-ai", immediately read this entire "Managing the Fork & Upstream Syncs" section.
- Prefer `design-md/local/` (or similar) for any custom work Corey creates.
- After merging a sync PR or making changes, check whether `FUTURE_COREY.md` needs a small update to the "Current State" or "Next Move" sections.
- Always leave the repo in a clean state (`git status` should be empty) before finishing.

## Related

- Upstream repo and contribution rules: https://github.com/Khalidabdi1/design-ai
- Sol workspace conventions: `~/Sol/README.md`, `~/Sol/07-Systems/Conventions/Project-Creation-Directive.md`
