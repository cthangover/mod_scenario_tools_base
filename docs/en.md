# Scenario Authoring Base — scenario files for authoring tools

`scenario_tools_base` is a library shared by the editors that read or write scenario files. It adds no windows; it comes along with the editors that need it.

## Who uses it

The Scenario Editor, the Scene Editor, the Interactive and Light editors, and the RPG map editor.

## What it gives

- **`ScenarioFileService`** — finds the `.scenario` files of every mod (`ScanScenarioFiles`), reads and writes them (folder mods only), parses the header (scene, priority), extracts references (scene switches, locale keys, quests, backgrounds), creates a new scenario for a scene (`CreateForScene`) and builds the scene graph (`BuildSceneGraph`, the data behind the Scenario Editor's graph).
- **`ScenarioSyntaxService`** — the highlighting of the scenario language for the editors' text views (the RPG map editor uses it for event scripts) and a tokenizer for command lines; the Interactive Editor uses it to find which scenario adds an interactive, the Light Editor reads and rewrites the `light_set` line with the file service.

It depends on the dialog runtime (`dialog_base`) for the language itself; neutral file and scene services stay in `tools_base`, so tools that do not touch scenarios do not pull the dialog runtime in.

## Dependencies

`tools_base`, `dialog_base`.
