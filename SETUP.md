# Almanac v2.1 setup — PROTOTYPE

No plugins. Works on desktop and mobile.
Check you're in the right vault before copying anything in.

- New vault: sections 1, 2, 3, 4.
- Vault already on v2.0: section 5, then 3 and 4.

## 1. Copy (2 min)
- `Templates/`, `Bases/`, `Tending.md` → vault root.
- Make empty folders: `Seeds/`, `Tasks/`, `Shoots/`, `Branches/`, `Trees/`, `Reference/`. (Views go by `type`, not folder, so a note in the wrong folder still works.)
- Optional: copy `examples/` in to see the views working, then delete it.
- Fresh vault only: `obsidian-config/types.json` → `<vault>/.obsidian/types.json`.
  Existing vault: set these by hand instead (property menu → type): created_on, due_on, finished_on, visited_on, next_visit_on = Date; interval_days = Number.

## 2. Core plugins (2 min) — Settings → Core plugins
- **Templates** on; template folder `Templates`.
- Settings → Files & links → Default location for new notes → **In the folder specified below**: `Seeds`.
- **Bases** on.
- Settings → Editor → Properties in document → **Hidden** (edit properties from the File properties side panel, or straight in a view's table).
- Optional: copy `obsidian-config/snippets/hide-templates.css` and `hide-bases.css` into `<vault>/.obsidian/snippets/`, then Settings → Appearance → CSS snippets → turn on either or both. One hides `Templates/`, the other `Bases/`: they are config. The base files are the views; notes embed them by name.
- Settings → Hotkeys: give "Templates: Insert template" a hotkey (e.g. Ctrl+T; the steps below assume it).
- Mobile: Settings → Toolbar → add "Create new note" and "Templates: Insert template". Bookmark `Tending`.

## 3. Use
Templates come in two sorts:
- **Kind templates** (Seed, Task, Shoot, Branch, Tree) make a note into that kind. Insert one **once** per note: inserting it again resets `state` and `created_on`.
- **State templates** (Active, Dormant, Blocked, Done, Pruned) set `state`, whatever it was. Done and Pruned also stamp today into `finished_on`. Health states (Healthy, Thirsty, Overwatered, Uneven) are typed: Obsidian suggests values already used.

- **Seed**: Ctrl+N → short title (the cursor starts there) → Ctrl+T → Seed. URLs and detail go in the body; titles can't hold `: / \ ? * " < > |`. One note per Seed.
- **Sorting a Seed**: open it → Ctrl+T → Task / Shoot / Branch / Tree (sets `type`). Optionally move it to its folder. Into a Note: delete the `type` property, move to `Reference/`. Letting it go: delete it.
- **Task**: Ctrl+N → short title → Ctrl+T → Task. Set `shoot` to `"[[Some Shoot]]"`, or leave it empty for a Loose Task. Starts Dormant. Picking it up: Ctrl+T → Active. Finishing: Ctrl+T → Done (or Pruned to let it go). Stuck: Ctrl+T → Blocked, and say why in the body.
- **Shoot**: Ctrl+N → title → Ctrl+T → Shoot. Set `branch` to `"[[Some Branch]]"`, or leave it empty for a Loose Shoot. Never a Tree. States as for Tasks; say why it's Blocked (and link the blocker) in Description.
- **Branch**: Ctrl+N → title → Ctrl+T → Branch. Set `tree` to `"[[Some Tree]]"` (required). Starts Healthy. Cutting it from the Tree: Ctrl+T → Pruned (soft delete).
- **Tree**: Ctrl+N → title → Ctrl+T → Tree.
- **Tending**: open `Tending`. Seeds to sort, Active Shoots grouped by Branch ("due" marks anything due today or earlier), the Standup list (Tasks finished since the last working day plus everything open, grouped by Shoot, Active first), Trees with Visit due.
  Each vault can tailor its own `Tending.md`. Without a standup (e.g. a personal vault), swap `![[Tasks.base#Standup]]` for `![[Tasks.base#Open]]`.
- **Visit**: open the Tree. Look over Roots, North Stars and the Branches table; set each Branch's state in the table; drill into a Branch or two if you want. Add a row at the top of Tree Remarks (`| one Branch getting all the water; the other is dry | 2026-11-28 |`), then set the Tree's `state`, `visited_on` and `next_visit_on`.
- **Clean-up** (whenever you like): `Tasks.base#Pruned`, `Shoots.base#Finished`, `Branches.base#Pruned` list what's been pruned. Keep anything worth keeping, delete the rest.

## 4. First check (2 min)
Make a test Tree, a Branch on it, a Shoot on the Branch and a Task for the Shoot.
- The Branch shows in the Tree's Branches table.
- Set the Shoot Active: it shows on `Tending` under its Branch, with its Tree in the tree column. If the tree column shows an error, note it in the friction log.
- Set the Task Active, then Ctrl+T → Done: `state` becomes Done and `finished_on` today, and it stays on the Standup until the next working day.

## 5. Moving a v2.0 vault onto v2.1 (about 20 min)
Confirm the vault's full path first. Back it up if it holds anything you'd miss.
1. **Copy** the new `Templates/`, `Bases/` and `Tending.md` over the old ones (replace). Make a `Branches/` folder. Re-apply any tailoring you'd made to `Tending.md`.
2. **Rename properties across the vault** (Properties view, or the "All properties" list in the side panel → right-click a property → Rename): `for` → `shoot`, `due` → `due_on`, `done` → `finished_on`, `ended` → `finished_on`, `visited` → `visited_on`, `next_visit` → `next_visit_on`. If renaming `ended` onto the existing `finished_on` is refused, rename it on each Shoot by hand.
   Then set property types as in section 1 (finished_on etc. = Date).
3. **Branches**: for each Branch line on a Tree, make a Branch note (Ctrl+N → its name → Ctrl+T → Branch), set `tree` and `state`. Then delete the old checklist.
4. **Shoots**: set `branch` to the Branch note as a link (`"[[Branch name]]"`), and delete the `tree` and `tended` properties. A Shoot with no Branch is a Loose Shoot: leave `branch` empty. Optionally reshape the body into Description, Goals, Tasks (`![[Tasks.base#For this Shoot]]`), Questions, Links; the old `## Tasks` embed (`#For this`) no longer exists, so swap it either way.
5. **Tasks**: any Task whose `shoot` points at a Tree becomes a Loose Task: empty its `shoot`. Delete `blocked` (views ignore it if you leave it).
6. **States on Tasks**: open `Tasks.base` (or `Tending`) and set `state` in the table: finished ones Done; ones you're working on Active; stuck ones (blocked ticked) Blocked; the rest Dormant. Shoots keep their states; any Pruned or Done Shoot already has `finished_on` from step 2.
7. **Trees**: reshape the body into Roots, North Stars, Branches (`![[Branches.base#On this Tree]]`), Questions, Links, Tree Remarks. Move old Remarks into the table, newest first: `| remark | YYYY-MM-DD |`.
8. Run the first check (section 4).
