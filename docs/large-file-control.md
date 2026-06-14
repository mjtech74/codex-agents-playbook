# Large File Control

Large files are not automatically bad, but they are often where agent changes pile up too easily.

## Warning Levels

- 600+ lines: inspect split candidates.
- 900+ lines: prefer a split plan or immediate extraction.
- 1200+ lines: avoid adding new responsibilities.

## Common Extraction Points

- seed data assembly
- modal state
- collection controllers
- validation maps
- submit helpers
- API mappers
- panel components
- table column definitions
- browser-only interaction hooks

## Decision Rule

Ask:

1. Is this file supposed to orchestrate, render, validate, submit, and store state all at once?
2. Is the new change adding a new responsibility?
3. Can the new responsibility be named as a hook, helper, component, or module?

If yes, split before the file becomes harder to reason about.

## If You Do Not Split

Log why:

- the change is tiny and local
- the file already owns this exact responsibility
- a split would be riskier in this cycle
- the next split target is documented
