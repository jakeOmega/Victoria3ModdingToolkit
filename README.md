# Victoria 3 Modding Tools

This project provides a set of Python tools for modding the strategy game Victoria 3. The tools allow you to efficiently process, manipulate, and analyze the game's data files, enabling you to create mods and customize the game experience.

## Features

- Parse and load game data files from both the base game and mod directories
- Manipulate and modify game data using a convenient and intuitive API
- Compare and detect differences between base game data and mod data
- Generate and apply JSON-based patch files for easy distribution and sharing of mods
- Seamlessly integrate mod data with the base game data for a unified modding experience

## Usage

1. Update the `base_game_dir` and `mod_dir` variables in the `mod_state.py` file to point to the appropriate directories for your Victoria 3 installation and mod files.

2. Import the necessary classes and create an instance of the `ModState` class:
   ```python
   from mod_state import ModState

   mod_state = ModState(base_game_dir, mod_dir)
   ```

3. Access and manipulate game data using the provided methods:
   ```python
   # Get data for a specific entity type
   buildings_data = mod_state.get_data("Buildings")

   # Modify game data
   buildings_data['new_building'] = {...}

   # Save changes to a JSON patch file
   mod_state.save_changes_to_json("path/to/changes.json")
   ```

4. Apply the JSON patch file to the base game data:
   ```python
   patched_mod_state = ModState(base_game_dir, "path/to/changes.json", diff=True)
   ```

5. Generate modified game data files:
   ```python
   patched_mod_state.update_and_write_file("Buildings", "path/to/mod/buildings/output.txt")
   ```

## Acknowledgements

- The Victoria 3 game and its data files are the property of Paradox Interactive.
- This project is an unofficial modding tool and is not affiliated with or endorsed by Paradox Interactive.
