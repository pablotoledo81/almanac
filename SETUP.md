# Almanac prototype templates — PROTOTYPE, throwaway

No plugins. Works on desktop and mobile.
Check you're in the right vault before copying anything in.

## 1. Copy (2 min)
- `Templates/`, `Bases/`, `Tending.md` → vault root.
- Make empty folders: `Seeds/`, `Trees/`, `Shoots/`, `Tasks/`, `Reference/`.
- Optional: copy `examples/` in to see the views working, then delete it.
- Fresh vault only: `obsidian-config/types.json` → `<vault>/.obsidian/types.json`.
  Existing vault: set these by hand instead (property menu → type): due, done, tended, ended, visited, next_visit = Date; blocked = Checkbox.

## 2. Core plugins (2 min) — Settings → Core plugins
- **Templates** on; template folder `Templates`.
- Settings → Files & links → Default location for new notes → **In the folder specified below**: `Seeds`. (No Unique note creator: timestamp names had to be renamed anyway.)
- **Bases** on.
- Settings → Editor → Properties in document → **Hidden** (edit properties from the File properties side panel).
- Copy `obsidian-config/snippets/hide-templates.css` into `<vault>/.obsidian/snippets/`, then Settings → Appearance → CSS snippets → turn it on. It hides `Templates/` and `Bases/` (the base files are the views; notes embed them by name).
- Settings → Hotkeys: give "Templates: Insert template" a hotkey (e.g. Ctrl+T; the steps below assume it).
- Mobile: Settings → Toolbar → add "Create new note" and "Templates: Insert template". Bookmark `Tending`.

## 3. Use
- **Seed**: Ctrl+N → type a short title (the cursor starts there) → Ctrl+T → Seed. URLs and extra detail go in the body; titles can't hold `: / \ ? * " < > |`. One note per Seed. Seeds show at the top of `Tending`.
- **Sorting a Seed into a Task**: open it → Insert template → Task (adds the Task properties) → set `type` to `task`, set `for`, move it to `Tasks/` (optional: views go by `type`, not folder).
  Into a Shoot / Note / Tree: same idea with that template (Notes: drop `type`, move to `Reference/`). Letting it go: delete it.
- **Task you already know is a Task**: Ctrl+N → short title → Ctrl+T → Task (it lands in Seeds/; views go by `type`, so leaving it there is fine).
  Set `for` to `[[Shoot]]`, `[[Tree]]`, or leave it empty (Loose Task). Done: Insert template → Done (stamps today into `done`). Stuck: tick `blocked`.
- **Shoot**: new note in `Shoots/` → Insert template → Shoot. `tree: "[[Example Tree]]"`, `branch: Example Branch A`. Ending it: state Done/Pruned + `ended`.
- **Tending**: open `Tending`. Top Shoot first; set its `tended` to today when you've looked at it.
- **Visit**: open the Tree, look over Branches, Shoots, Tasks; add a Remark at the top of Remarks
  (`- 2026-11-28 · Uneven · one Branch getting all the water; the other is dry`), set `state`, `visited`, `next_visit`.

## 4. First check (1 min)
Capture a test Seed and sort it into a Task for a test Shoot on a test Tree. Check whether Insert template merges the Task properties into the Seed or duplicates `type`: note which.
Then check the Task appears on the Shoot. If it doesn't, `file.hasLink` isn't seeing property links and the filters need to match on `for` instead.
