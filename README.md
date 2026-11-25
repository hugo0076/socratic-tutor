# socratic-tutor

A Claude Code plugin that turns Claude into a strict Socratic tutor: it places your
starting level with a short diagnostic, tracks a 0-5 skill map per subskill, teaches
by asking one question at a time, re-tests earlier material without warning, and
only finishes after a final mixed assessment.

## Install

From a GitHub repo containing this folder:

```bash
claude plugin marketplace add <owner>/<repo>
```

```bash
claude plugin install socratic-tutor@socratic-tutor-marketplace
```

Or try it without installing:

```bash
claude --plugin-dir /path/to/socratic-tutor
```

## Use

Start a session and ask to be taught, for example `teach me SQL window functions`
or `quiz me on Bayes' theorem`. You can also invoke it directly with
`/socratic-tutor:socratic-tutor <topic>`.

One-off questions ("explain X", "what is X") are answered normally and do not start
a tutoring session.

Commands during a session:

| Say | Effect |
| --- | --- |
| `show progress` | Render the skill map |
| `harder` / `easier` | Adjust difficulty |
| `just tell me` | Skip Socratic mode for the current question only |
| `save state` | Emit a block you can paste into a new session to resume |
| `resume from:` + saved block | Restore and continue |
