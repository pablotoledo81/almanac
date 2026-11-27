# Almanac

Obsidian templates for the Almanac: tending life and work for balance, not productivity.

A hand-run Obsidian system for noticing where attention goes across the lasting areas of life and work. It tracks Tasks and Shoots, shows how they relate to the areas of life you care about, and nudges you to reflect, so your choices about where time and attention go are more conscious. It is a manual system first: everything works by hand, on desktop and mobile. Core Obsidian only: Templates and Bases, no community plugins.

- `SETUP.md`: install, daily use, and moving a v2.0 vault onto v2.1
- `Templates/`: one per kind of note (Seed, Task, Shoot, Branch, Tree) and one per state (Active, Dormant, Blocked, Done, Pruned)
- `Bases/`: the views (Seeds, Tasks, Shoots, Branches, Trees), embedded by name
- `Tending.md`: the daily Tending page
- `obsidian-config/`: property types and a CSS snippet that hides the config folders
- `examples/`: a dummy Seed, Tasks, Shoot, Branches and Tree, to see the views working

**This repo holds templates, views and documentation only. Nothing personal or work-related, ever; examples are dummies with generic names.**

Versions are git tags: v2.0 (first prototype), v2.1 (from its feedback), v2.2 (after the retro). v2.1 is a trial: its words and rules may change at v2.2.

## Words (v2.1 trial)

| Kind | What it is | Time horizon | Looked at in |
| --- | --- | --- | --- |
| **Tree** | An area of life that needs regular care and attention to thrive and grow (Health, Work, Family) | Life-long | Visits, Seasonal walks |
| **Branch** | A lasting theme that grows a Tree (Parenting on Family, Pensions on Finance) | Years to decades | Visits |
| **Shoot** | A short, focused effort that grows a Branch, or stands alone | Days to months | Tending |
| **Task** | A concrete action for a Shoot, or standing alone | Minutes to hours | Tending |
| **Seed** | Anything captured but not yet given a place | Until sorted | Tending |

- **Loose Task / Loose Shoot**: a Task with no Shoot, a Shoot with no Branch. Placed deliberately nowhere; not a Seed.
- **Roots**: on a Tree, why it matters: the foundations that keep it healthy and stable. Branches are growth; Roots are foundations.
- **North Stars**: on a Tree or Branch, the direction it is growing in. Not goals with an end; those are Shoots.
- **Tree Remark**: a dated line or two written on a Visit: how's it going here?
- **Note**: anything kept for its own sake, in `Reference/`.

### What links to what

| | No link | Shoot | Branch | Tree |
| --- | --- | --- | --- | --- |
| Task | allowed | allowed | no | no |
| Shoot | allowed | no | allowed | no |
| Branch | no | no | no | required |
| Tree | (top) | no | no | no |

A Shoot names only its Branch; its Tree is read through the Branch.

### States

- **Tasks and Shoots**: Active (working on it now), Dormant (exists, not being worked on now: resting or not started; new ones start here), Blocked, Done, Pruned.
- **Trees**: Healthy, Thirsty, Overwatered, Uneven, Dormant.
- **Branches**: Healthy, Thirsty, Overwatered, Dormant, Pruned.
- **Pruned** is a soft delete, on Tasks, Shoots and Branches: the note stays, out of the everyday views, until a clean-up decides what to keep and deletes the rest.
- Done and Pruned stamp `finished_on`.

### Rhythms

- **Tending**: daily, about 5 minutes, plus through the day: Seeds, Active Shoots, Tasks.
- **Visit**: weekly, 15 to 30 minutes, one Tree and maybe a Branch or two. Trees and Branches only, no Shoots or Tasks.
- **Seasonal walk**: about an hour, every Tree.
