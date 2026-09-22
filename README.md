# Shiny Hunt Counter -- Made by MoonFlower

This is a Pokémon shiny hunt counter.

It's an all-in-one web app solution to keeping track of all your hunts across every game and Pokémon generation, with 0 downloads required.

## Features:

- A Pokédex that stores a sorted, visual, and animated collection of all Pokémon you choose to hunt.
- A Living Dex to fill out and overview all shiny Pokémon across every generation — tap any tile for that Pokémon's info, and toggle "Hide uncaught" to see only what you've found.
- Separate tabs for Active, Paused, and Completed hunts, so your roster stays organized as hunts wrap up.
- A visual odds estimate that displays your cumulative chance at obtaining a shiny, which updates in real time as you add to the counter — including method-specific tiers for chain-based hunting (SOS chaining, Poké Radar, Dynamax Adventures, and more).
- The ability to manually set the counter to a starting number of your choosing.
- The ability to upload your own custom sprite/3D model in a .gif format, for any Pokémon you add to your Living Dex collection/hunt — including a picker for regional forms (Alolan, Galarian, Hisuian, Paldean) where one applies.
- Can automatically fetch sprites from an online database through one button click using just the Pokémon's name, should you not choose to upload your own.
- A detailed Pokémon info popup showing your own hunt stats (encounters, time spent hunting, start/end dates) alongside in-game data pulled live — abilities, evolution requirements, level-up moveset with PP, and wild encounter locations/rates.
- An automatic session timer that tracks total time actively spent hunting each Pokémon, accumulating across sessions — with editable start/end dates for picking up a hunt already in progress.
- Phase tracking: log a "Phase 1," "Phase 2," etc. whenever a different shiny shows up while you're hunting, without losing or interrupting your original hunt's progress — with the option to also add the phased Pokémon to your Completed dex, carrying over the hunt's encounter count and time.
- A customizable counter key, so you can increment your encounter count with a single keypress instead of clicking.
- Controller support — increment, decrement, and navigate the whole app with a gamepad (see [Controller Controls](#controller-controls) below).
- Live OBS integration — push your active hunt's sprite, name, encounter count, and hunt timer straight onto your stream in real time (see [OBS Integration](#obs-integration) below).
- A "Mark shiny found" button that celebrates with confetti and a jingle, and marks the Pokémon in your Pokédex as caught.
- Data export/import to a CSV spreadsheet file for backups — opens right up in Excel, Google Sheets, or Numbers.
  - Data is also stored locally, in case you forget to export to a file.
- Short, but sweet, sound effects.
- A light and dark mode.
- Mobile support coming soon.

## How to Use

1. Visit: https://moonflowah.github.io/Shiny_Counter/
2. Click to open the program.
3. Enter the name of the Pokémon you want to hunt down in the indicated text box field.
4. If you don't have a custom sprite/3D model .gif to add, click the "Try Fetch Shiny" button to try and fetch the sprite from the database.
   - If the fetch doesn't work, double check the Pokémon name spelling.
   - If the spelling is correct and the fetch still doesn't work, it isn't in the database and a custom sprite .gif file is required.

   > Custom sprite/3D model .gif files can easily be obtained from this site: https://projectpokemon.org/home/docs/spriteindex_148/

5. After a link is fetched from the database, or your custom sprite is uploaded, click the yellow "Add Pokémon" button at the bottom.
6. The counter at the top should display the newly added Pokémon of your choosing when selected from the Pokédex, and the counter will be free to use.

## OBS Integration

The Settings tab has an OBS Integration panel that connects directly to OBS's built-in WebSocket server and keeps your active hunt's sprite, name, encounter count, and hunt timer updated live on stream — no plugins required.

**Setup:**

1. In OBS, go to **Tools > WebSocket Server Settings**, make sure the server is enabled, and note the port and password (if you've set one).
2. In OBS, add the sources you want the tracker to update:
   - A **Browser Source** for the sprite.
   - **Text (GDI+/FreeType 2)** sources for the name, encounter count, and/or hunt timer — add as many or as few of these as you want synced.
3. In the app, open the **Settings** tab and expand **OBS Integration**.
4. Enter your server address (e.g. `ws://localhost:4455`) and password, then click **Connect**.
5. Pick which OBS source each field should update from the dropdowns (Sprite / Name / Count / Timer).
6. Turn on **"Keep all of the above updated live"** to have the tracker push updates automatically as you hunt.

Once connected, the sprite is pushed as a clean, transparent shiny image (regional forms included) rather than the animated GIF, so it composites over your overlay with no black or white box behind it.

## Controller Controls

Connect any standard gamepad and it's picked up automatically — a "Controller connected" message appears once it's detected.

- **A** — +1 encounter
- **B** — -1 encounter
- **X** — toggle "Mark shiny found"
- **Y** — open the info popup for your active hunt
- **D-pad Up / Down** — move the active-hunt selection through your current tab's roster
- **D-pad Left / Right** — switch between the Active / Paused / Completed / Living Dex tabs
