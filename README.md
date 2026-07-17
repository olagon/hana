# hana

A task manager you can paste anything into. Drop in a full email, meeting
notes, or a single line like "call the vet Friday" and hana pulls out the
real tasks, merges them with what you already have, and keeps everything
moving forward.

**Use it live:** [add your published artifact link here]

## What it does

- **Paste anything.** hana reads emails, notes, and plain text, then shows
  the tasks it found for a quick review before anything is added.
- **Smart merging.** If a pasted item matches a task you already have, hana
  updates that task instead of creating a duplicate.
- **Dates handle themselves.** New tasks land on today unless the text names
  a deadline. Unfinished tasks move to today each time hana opens, so
  nothing slips into the past.
- **Projects without ceremony.** Tag a task with a project and filter your
  list with one tap.
- **Nothing locked in.** Export your tasks to a small JSON file and import
  them into any other copy of hana.
- **Private by design.** Each user gets their own task list tied to their
  own Claude account. Lists never mix, even on a shared link.

## How it runs free

hana is built as a Claude artifact. Inside claude.ai, artifacts can call
Claude without an API key, and usage counts against each user's own Claude
plan. That means no server, no API bill, and no per-user cost for whoever
publishes it. Any Claude account works, including the free tier. Claude
Sonnet 4.6 handles the reading.

## Running your own copy

The whole app is a single React component, `hana.jsx`, written for the
Claude artifact runtime.

1. Open the live link above and press **Remix** to get your own editable
   copy, or paste the contents of `hana.jsx` into a new claude.ai chat and
   ask Claude to render it as an artifact.
2. Make it yours. Ask Claude for any changes you want.
3. Press **Publish** in the artifact panel to get a shareable link.

Two features only exist inside Claude artifacts: the keyless calls to
Claude and the built-in persistent storage (`window.storage`). Hosting this
file anywhere else means replacing both with your own API backend and
storage layer.

## Feature ideas

Ping [Olin Lagon on LinkedIn](https://www.linkedin.com/in/olinlagon/).
Improvements are pushed to the live copy, so everyone using the link gets
updates automatically.

## License

MIT. See [LICENSE](LICENSE).

Built with Claude by [Olin Lagon](https://www.linkedin.com/in/olinlagon/).
