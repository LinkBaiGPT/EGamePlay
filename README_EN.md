# EGamePlay

EGamePlay is a Unity-based combat framework that focuses on building flexible ability and skill systems.
The project is currently being refactored around version 3.0 and keeps the original data-driven skill
configuration workflow intact while redesigning runtime logic using an Entity-Component-System (ECS)
approach provided by the [EcsNode](https://github.com/m969/EcsNode) library.

## Unity version
- Developed and tested with **Unity 2022.3.53f1**. Using a different editor release may require manual
dependency updates.

## Demo scenes
Open the following scenes from the `Assets` folder to explore the sample content:
- `Assets/GameResources.RpgExample/Scenes/RpgExample.unity` – an RPG combat showcase.
- `Assets/GameResources.RpgExample/Scenes/ExecutionLinkScene.unity` – the skill editor playground.

## Creating a skill (quick reference)
1. Add a new row to `Excel/AbilityConfig.xlsx` with the desired skill identifier and parameters.
2. In the Unity Project view, right-click **Ability/AbilityConfig** to create a matching ScriptableObject
   asset. Configure the skill effects in the inspector.
3. Right-click **Ability/Execution** to create the execution asset that defines the presentation fragments.
4. Attach the skill to a `CombatEntity` at runtime and trigger casts through `SpellComponent`.

## Using EGamePlay in another project
Make sure the project contains **Odin Inspector** and define the `UNITY` scripting symbols required by the
plug-in. Copy these directories into the target Unity project and resolve any conflicts as needed:
- `Assets/Gizmos`
- `Assets/Game.Model`
- `Assets/Game.System`
- `Assets/Game.ThirdParty`
- `Assets/Unity.EditorScripts/Editor`
- `Assets/Unity.Scripts/UnityMono/EGamePlay`
- `Assets/Plugins/Editor/npoi`
- `Excel`

## ET framework integration notes
When integrating with ET 8.1, move the folders into the appropriate ET assemblies, separating business
logic and view logic. Add the `EGAMEPLAY_ET` scripting define symbol and remove the legacy `ETHelper`
files if they conflict with the framework’s existing workflow.

For more documentation and development notes, refer to the [Chinese README](README.md) and the
[project wiki](https://github.com/m969/EGamePlay/wiki).
