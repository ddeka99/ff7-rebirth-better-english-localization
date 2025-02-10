# FF7 Rebirth - Better English Localization

Check progress on the [FF7 Rebirth English Localization Progress](https://docs.google.com/spreadsheets/d/1A6S3sNYxN7QMl2264053-AeXuMtmaZicaE6KibpsUT8/edit?gid=0#gid=0).

This repository is dedicated to developing a more faithful English localization for *Final Fantasy VII REBIRTH*.

## Overview

*Final Fantasy VII REBIRTH* is the sequel to *Final Fantasy VII Remake* and a part of the original 1997 *Final Fantasy VII* game. The original script is in Japanese, and the official English localization by Square Enix takes significant creative liberties. This has led to changes in character personalities, plot details, and context that diverge from the original script.

While localization is crucial, it should remain faithful to the source material. The goal of this project is to create an English localization that aligns more closely with the Japanese script while maintaining readability and coherence.

## Approach

Since I do not know Japanese, I will utilize Large Language Models (LLMs) to assist with translation. Specifically, I plan to use **GPT-4o global** provided by **Azure** to generate translations that preserve the original intent and nuances of the Japanese script.

## External Tools

This project relies on several external tools to aid in the localization process. These tools are stored in the local repository but excluded from version control:

### 1. ff7r-text-tool

**Link:** [GitHub Repository](https://github.com/matyamod/ff7r-text-tool)

This tool is used for modifying text data within the game's `.uasset` files.

- Download the latest release and extract it.
- Run `GUI.exe`.
- The GUI provides two key functions:
  - **Export:** Extracts text from the game's `*_TxtRes.uasset` files and saves it as `.csv` or `.json`.
  - **Import:** Modifies an existing `*_TxtRes.uasset` file with updated text and saves it in the `imported` folder.

### 2. FModel

**Link:** [Official Website](https://fmodel.app/)

This tool allows viewing Unreal Engine game packages, folder structures, and assets.

- Download and run the `.exe`.
- Set the game directory to `FINAL FANTASY VII REBIRTH`.
- The game’s archives are located in `FINAL FANTASY VII REBIRTH\End\Content\Paks`.
- Each archive consists of `.pak`, `.utoc`, and `.ucas` files.
- Using FModel, load these archives to explore the game’s folder structure.
- The text files are located at: `End/Content/Text/US/` and `End/Content/Text/JP/`.
- Extract `.uasset` text files such as `4000-MIDGR_TxtRes.uasset` for modification.

### 3. UnrealReZen_V01

**Link:** [NexusMods](https://www.nexusmods.com/finalfantasy7rebirth/mods/194)

This tool is used for repackaging modified `.uasset` files into `.pak` mods.

#### Steps

1. Run `FF7Rebirth UnrealReZen Companion.bat`.
2. Configure paths in the terminal:
   - `gamePaksFolderConfig`: Set this to `<some-parent-location>/FINAL FANTASY VII REBIRTH\End\Content\Paks`.
   - `modFolderConfig`: Set this to where your mod is, e.g., `<some-parent-location>/BetterEnglishLocalization_P`. Within this, the modified `.uasset` files are stored, e.g., `<some-parent-location>/BetterEnglishLocalization_P/End/Content/Text/US/4000-MIDGR_TxtRes.uasset`.
   - `modOutFolderConfig`: Set this to the output mod directory, e.g., `<some-parent-location>/FINAL FANTASY VII REBIRTH\End\Content\Paks\~mods`.
3. Run the tool to generate the `BetterEnglishLocalization_P` mod archive, which includes `.pak`, `.utoc`, and `.ucas` files.
4. The game will now load the modified dialogue from the `~mods` directory.
