# Adding or updating a session

Every event gets its own folder under `sessions/`, grouped by term. The folder holds the details, the slides, and what happened.

## Create a new session

1. Find or create the term folder, named `YYYY-term`, for example `2026-fall` or `2027-winter`.
2. Name the session folder with the date first, then a short name: `YYYY-MM-DD-short-name`, for example `2026-10-07-aws-101`. If the date is not set, use `TBD-short-name` and rename it later.
3. Copy the template:

   ```bash
   cp -r templates/session sessions/2026-fall/2026-10-07-aws-101
   ```

4. Fill in `README.md` in the new folder. Replace every `_TBD_` you can.
5. Add a row to [`sessions/README.md`](sessions/README.md), newest first.

6. Check the layout, then open a pull request:

   ```bash
   scripts/check-sessions.sh
   git checkout -b add-2026-10-07-aws-101
   git add sessions/
   git commit -m "Add 2026-10-07 AWS 101 workshop"
   git push -u origin add-2026-10-07-aws-101
   gh pr create --fill
   ```

   The same check runs automatically on every pull request, along with a check for broken links between files. The exec team reviews and merges.

## Update a session

Edit the files in its folder. What changes most: the status line, the checklist, and the links.

## Status values

| Status | Meaning |
|---|---|
| Idea | Proposed, nothing booked |
| Planning | Date chosen, work in progress |
| Awaiting approval | Submitted to SSF |
| Confirmed | Approved, listing live |
| Done | Event happened, recap pending |
| Recapped | `recap.md` filled in |
| Canceled | Not happening. Keep the folder and note why |

## Slides

- Draft slide text and speaker notes in `deck.md` so the wording can be reviewed before anyone builds slides.
- Build the slides wherever you like (Google Slides, Canva, PowerPoint). Commit only the final `.pptx` export.
- Export the final version as `YYYY-MM-DD-short-name.pptx` into the session folder. Overwrite the same file instead of adding `-v2` or `-final`.

## After the event

Fill in `recap.md` within a week. Attendance and what to change next time matter most. Delete any demo AWS resources so they stop billing.

## Keep it shareable

This repository is public. Do not commit personal contact details, budgets, passwords, or private Drive links. See "What does not go in this repo" in the main [README](README.md).
