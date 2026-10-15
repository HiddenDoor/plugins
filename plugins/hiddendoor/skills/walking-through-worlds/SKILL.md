---
name: walking-through-worlds
description: Walks a creator through how an existing world is represented in Hidden Door, explaining its characters, player possibilities, storylines and rules. Use when the creator asks for a guided tour or accepts a walkthrough after import or creation, with small requested changes handled by developing-worlds.
---

# Walk through a world

Help the creator understand their saved world in Hidden Door. Explain the concepts
through their own content, one topic at a time, and let them steer the conversation.
This is a guided tour, not a schema explanation or an automatic source audit.

## Speak to the creator

Talk about their world and what players can experience. Do not narrate tool
discovery, file reads, schema lookups, IDs or internal checks. Read and inspect
content without announcing each call. Explain technical details only when asked
or when they help resolve a specific problem.

For example, say “Let's look at the stories players can enter,” not “I'll fetch
the storyline collection.” Explain unfamiliar concepts through the world's own
characters and situations. Keep each explanation short, answer questions directly,
and go deeper when requested. Do not fill the tour with implementation caveats,
completion scores or claims about what the source got wrong.

## Scope and other skills

Use this skill when the creator asks for a walkthrough or accepts an offer of one.
`importing-worlds` and `creating-worlds` produce the draft; this skill explains it.
Use `developing-worlds` for a specific change requested during the tour, then resume
here. A direct editing request does not need a walkthrough first.

## Start with the saved world

Use the world ID from the preceding import or creation. Otherwise, find the world
with `list_worlds` and clarify ambiguous matches. Use the authenticated Hidden Door
MCP connection; if missing, direct the creator to https://www.hiddendoor.co/mcp.

Read the saved world with `read_world`. Use `describe_world_fields` to discover
resources and learn what the relevant settings do. Read full records when explaining
their details; collection summaries provide names, not all their content. Follow
pagination as needed. Do not describe unseen records or infer missing settings.

Begin with a short account of the premise as saved, then suggest a starting point:
“We can start with who players can be, then look at the stories they can enter.”
Follow a topic the creator has already chosen instead of asking them to choose again.
Do not deliver the entire tour in one response or require an upfront questionnaire.

## Explain concepts through this world

Use the following topics as a guide, not a checklist to recite. Choose an order
that fits the conversation, skip empty topics, and read more as each topic arises.

- **The premise and feel.** Describe what the world is about and how its stories
  are meant to feel. Use the field reference to distinguish descriptive copy
  from settings that guide play.
- **People, places and things.** Show how named characters, locations and items
  establish the world. Pick a few useful examples rather than repeat the whole
  inventory. Explain factions through their members, interests and conflicts.
- **Who players can be.** Explain the roles and character choices offered to
  players. Distinguish those choices from named characters already in the world.
- **Shared kinds and qualities.** Introduce archetypes through actual examples:
  a kind of creature, profession or other set of shared qualities. Explain which
  characters or player choices use one and what it contributes. The word
  “archetype” can follow that explanation; do not lead with IDs or field names.
- **Stories players can enter.** Introduce storylines as authored starting
  situations and guides for how a story develops. Describe an actual storyline's
  setup, stakes and role for the player. Explain starting or unlocking conditions
  when relevant, using the saved settings and field guidance. Do not present a
  storyline as a fixed script that determines every player action or outcome.
- **How the world works.** Explain relevant lore, physical or magical rules,
  knowledge and secrets through their effect on the experience. Check activation
  conditions before claiming a rule is in effect.

For each topic, connect a short explanation to concrete saved content, then leave
room for the creator's response. For example: “This story starts with the children
abandoned in the forest. Would you keep that as the opening, or start elsewhere?”
Use examples from the world being read, not this example by default. Do not ask
for approval of every record or manufacture problems to prompt an edit.

## Make a requested change, then continue

When the creator asks for a change, use `developing-worlds` with the saved world ID,
the relevant topic or record, and their specific request. Keep the scope small:
changing the opening should not become rewriting every storyline or the world premise.
If the desired change is unclear, resolve that ambiguity before saving.

Let `developing-worlds` handle reading the current values, selecting fields, saving
and checking the result. Afterward, briefly describe what changed and continue the
walkthrough from where it paused, using the saved result rather than stale content.
Do not announce the skill switch or ask for another confirmation of a clear edit.

Questions and reactions alone do not authorise changes. Do not automatically
correct the world while explaining it. If an edit cannot be completed, explain the
specific obstacle and let the creator choose whether to continue the tour.

## Finish when the creator is done

The creator can skip topics, stop, or move into a longer editing session at any
point. Close with a brief recap of requested changes, if any, and the draft link.
Use `https://www.hiddendoor.co/create/{worldId}/vision` unless another environment
is explicitly configured. Do not publish the world or launch a playtest.
