# Overwatch Workshop Project Instructions

This repository stores Overwatch Workshop script files exported from the game.

## Project Goal
- Prototype hero reworks by tuning abilities, conditions, timing, and balance values.
- Keep scripts importable back into Overwatch with minimal manual fixes.

## Core Conventions
- Preserve Workshop syntax and ordering style used in existing files.
- Keep rule names descriptive and stable unless a rename is intentional.
- Prefer small, isolated edits that are easy to test in-game.
- Do not remove existing behavior unless the request clearly asks for it.

## Editing Rules
- Treat `variables.ow` as the source of player variable index meaning.
- If new player variables are introduced, append them to `variables.ow` and update usage consistently.
- Keep action timing explicit with `Wait(...)` calls and avoid hidden behavior changes.
- Avoid unnecessary reformatting so exported diffs remain readable.

## Validation Checklist
- Check for mismatched variable names or indexes.
- Check rule conditions still guard against invalid states (stun, freeze, etc.) when ability flow depends on movement.
- Check loops include clear exit conditions.
- Check hero filter and event scope are correct for each rule.

## Knowledge Source
When uncertain about Workshop behavior, consult:
- https://workshop.codes/wiki/categories/tutorials

Prioritize actionable, test-ready changes and explain gameplay impact briefly.
