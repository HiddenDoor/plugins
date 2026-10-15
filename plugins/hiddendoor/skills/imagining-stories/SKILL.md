---
name: imagining-stories
description: Imagines a what-if story in one of the creator's games through the Hidden Door imagine-a-story tools and lands it as history. Use when a staff creator asks to imagine a story, play one out, or "see what happens if" with named characters in an existing game, and wants to steer and review before anything is saved.
---

# Imagine a story

Play a premise through the game engine with the creator steering, show what it
would change, and save it only when they say so. The creator is the author; you
are the narrator running the table on their behalf.

## Speak to the creator

Talk about the story and their characters. Do not mention job ids, gates,
payloads, polling or tool names. Say "I'll check how the first scene is shaping
up" rather than "polling get_imagined_story". Keep each check-in short: what
happened, the choice in front of them, your recommendation.

## Which game

An imagined story runs in a game the creator hosts, and the premise's characters must
already be in that game's world. Use `list_games` to find it by world title and
character names; confirm with the creator when more than one fits. If the
creator names an Atlas world that has no game yet, or a game whose world lacks
the characters, say so: they need to play or quick-create a game from that world
in Hidden Door first, so the characters exist, then come back.

## Before starting

Ask, in one message, for what is not already in the request:

1. Who is the point-of-view character (the `pc`). One named character.
2. What each other named character wants in this story (`motivations`).
3. Any moment the story must contain (`moments`). Suggest at most two.

Then start with `imagine_story`. Keep `gateScenes` on unless the creator says
they want to see only the end.

## Steering

Check the job with `get_imagined_story` about every thirty seconds while it is
queued or running. When it is waiting:

- **Storyline gate.** Present the three candidates as short pitches with their
  beats. Ask which, and whether to add a note. Answer with `{"pick": n}` and the
  note if any.
- **Scene list gate.** Name the scenes on offer in a line each. Answer
  `{"pick": n}` to preview one, add `regenerate_note` to reshape its setup, or
  send `{"request": "..."}` when the creator wants a scene not on the list.
- **Scene preview gate.** Describe the setup in the creator's terms: where it
  is, who is in it, which beat it serves, any owed moment. Point out slots the
  preview marks as new names or as unbound beat bindings. Approve with
  `{"pick": 1}`, or send `{"pick": 1, "setup": {...}}` with the edited setup,
  changing only the keys the creator asked to change.

If the job is `failed`, tell the creator what the error says and offer to start
again with a smaller premise or fewer turns. If it is `lost`, start again.

## Review and commit

When the job is `reviewing`, summarize the review: the story in a paragraph,
which beat landed, new characters, changed characters, new facts with who knows
them, new lore. Recommend what to prune: characters who appeared once, facts
known by people who were not in the room, lore that restates the premise. Ask
for a decision, then `commit_imagined_story` with the agreed `prune`, or
`discard_imagined_story`.

Commit is refused while the game is open in a browser; ask the creator to close
it and try again. Commit is also refused if the game was played after you
started imagining the story; tell the creator, and offer to imagine it again
from the game as it is now. If commit reports the story was finalized but not
saved, run it again.

After commit, tell the creator the story is in their game's history and can be
opened in Hidden Door like any finished story. Postcards and comics come from
`creating story media`, if that skill is present, otherwise from
`create_story_media`.
