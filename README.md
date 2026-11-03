<div align="center">

# 💦 OCum Ascended + Tull/Liquid Pack + GT Softbody: Merged Script Patch

**One `OCumMaleScript` with all three mods' changes, so none of them gets lost.**

`v1.0` · Skyrim SE 1.5.97 · built on **OCum Ascended 4.1.1** · by **That Guy (Coronerra)**

</div>

> 🔞 Adult content. For adults 18+ only.

## What it merges
Each of these mods ships its **own complete `Scripts\OCumMaleScript.pex`**. In MO2 or Vortex only one of them wins, and the others' changes silently disappear. This patch is a single script that contains all of them:

| Source | What it contributes |
|---|---|
| **OCum Ascended 4.1.1** (Aietos) | The base script: orgasm handling, cum textures, cum shots, the cum bar |
| **OCum Ascended - Tull and Liquid Pack Meshes** (Blacksheepo815) | Uses the Tull Animated Creampie and Liquid Pack v2 meshes for vaginal, anal, oral and facial finishes (`StartPie` / `OCumTLPie`) instead of OCum's own creampie meshes |
| **...Tull and Liquid Pack Meshes - Scene Change Fix** (Blacksheepo815) | Re-checks every 2 s and re-equips the Tull/Liquid items that OStim strips on a scene change, so they stay on for the full 60 s |
| **GT - Softbody** OCum patch (Goutou) | 1. Removes the three NiOverride `Urethra` transform calls in `SetUrethra` that break SMP collision ("collision failure")<br>2. Fixes `CalculateCumAreaFromSkeleton` (`smallestDistance = distanceFemaleFace`), so a farther "butt" result can no longer override a closer "face" result |

## ❓ Why this is still needed with OCum Ascended 4.1.1 and Softbody v3.37.2
- GT Softbody v3.37.2's FOMOD says its OCum patch is *"not needed if you use the latest version of OCum."* But **OCum Ascended 4.1.1, the latest version, still has both issues**:
  - `SetUrethra` still calls `NiOverride.AddNodeTransformPosition`, `AddNodeTransformRotation` and `UpdateNodeTransform` on `"Urethra"`.
  - `CalculateCumAreaFromSkeleton` still lacks `smallestDistance = distanceFemaleFace`.
- This was checked function by function against the 4.1.1 script, and confirmed in GT Softbody v3.37.2's `Patch\OCum\Scripts` (those two changes are the only real differences from OCum).
- The Tull/Liquid add-on and its Scene Change Fix were made from the OCum script **without** the GT fixes. GT's patch is plain OCum **without** the Tull/Liquid code.
- So whichever `OCumMaleScript.pex` wins, you lose something. **This patch keeps everything.**

## 📋 Requirements
- [OStim Standalone](https://www.nexusmods.com/skyrimspecialedition/mods/98163) (7.5.1c tested)
- [OCum Ascended](https://www.nexusmods.com/skyrimspecialedition/mods/77506) **4.1.1**
- [OCum Ascended - Tull and Liquid Pack Meshes](https://dwemermods.com/mods/5304) (with its Scene Change Fix)
- [Tull Animated Creampie](https://dwemermods.com/mods/3535) (1.1 tested) and [Predator] Liquid Pack v2
- [GT - Softbody](https://www.nexusmods.com/skyrimspecialedition/mods/152103) (**v3.37.2** tested). Optional: if you use it, you don't need to tick its "OCum" FOMOD patch.

## 📦 Install
1. Download `OCum-Tull-Liquid-Softbody-Patch_v1.0.zip` from [Releases](../../releases/latest). The archive root is `Data`.
2. **MO2:** install it as a mod and place it **below** (so it wins over) OCum Ascended, *OCum Ascended - Tull and Liquid Pack Meshes*, its *Scene Change Fix*, and *GT - Softbody*. You can disable the Scene Change Fix mod; this patch includes it.
3. **Vortex:** install, then set this mod to load **after** all four. When it asks about the `OCumMaleScript.pex` conflict, choose this one.
4. There is no plugin. It's a script only, so it's safe to add mid-save.

## 🧪 Tested on
Only on my modified **Nolvus 6.0.21** (Skyrim SE 1.5.97) with the versions above.

## 🛠️ Source
`Data/Scripts/Source/OCumMaleScript.psc` is the full source. Recompile it with the Papyrus compiler or Caprica, with OStim, OCum, SKSE, NiOverride and PapyrusUtil sources on the import path. Changes are marked `OCumTL:` (Tull/Liquid add-on) and `GT Softbody OCum patch:`.

## 🔗 Related
- 🐺 [Werewolf Overhaul: Proof of Concept](https://github.com/Coronerra/Werewolf-Overhaul-Proof-of-Concept)
- 🌕 [Beast Aware](https://github.com/Coronerra/Beast-Aware)
- 🌙 [OStim Beast Form](https://github.com/Coronerra/OStim-Beast-Form)

## 🙏 Credits and permissions
- **Aietos**: OCum Ascended
- **Blacksheepo815**: OCum Ascended - Tull and Liquid Pack Meshes and its Scene Change Fix
- **Tullius Channel, Emotional Trash Can**: Tull Animated Creampie
- **Predator**: Liquid Pack v2
- **Goutou**: GT - Softbody and its OCum fixes
- **That Guy (Coronerra)**: the merge

This patch contains **modified code** from OCum Ascended, the DwemerMods Tull/Liquid add-on and GT Softbody. Only the merge work is MIT-licensed (see [LICENSE](LICENSE)). Anyone making a finalized or redistributed version should respect those authors' permissions.

*Have fun and Happy Modding!*
