# Moon's Shiny Counter

This is a Pokémon shiny hunt counter.

It's an all-in-one web app solution to keeping track of all your hunts across every game and Pokémon generation, with 0 downloads required.

## Features:

- A Pokédex that stores a sorted, visual, and animated collection of all Pokémon you choose to hunt.
- A Living Dex to fill out and overview all shiny Pokémon across every generation — tap any tile for that Pokémon's info, hover over a tile to see its number and name, and toggle "Hide uncaught" to see only what you've found.
  - Switch between the National Dex and regional Pokédexes (Paldea, Galar, Alola, Hisui) to track a single game's dex.
  - Add any Pokémon you haven't started hunting straight from its Living Dex tile, with the "Add to my hunts" button in its info popup.
- Separate tabs for Active, Paused, and Completed hunts, so your roster stays organized as hunts wrap up.
- A Stats tab with your hunting totals, personal records (fastest shiny, most encounters, longest hunt), a hunting-streak heatmap, and a timeline of every completed hunt, grouped by month.
- A visual odds estimate that displays your cumulative chance at obtaining a shiny, which updates in real time as you add to the counter — including method-specific tiers for chain-based hunting (SOS chaining, Poké Radar, Dynamax Adventures, and more).
  - A hunt ETA showing how many encounters a shiny takes on average at your odds, plus a time estimate based on your current pace.
  - Your hunting method is remembered for each Pokémon, so switching between hunts keeps the right odds.
- The ability to manually set the counter to a starting number of your choosing.
- The ability to upload your own custom sprite/3D model in a .gif format, for any Pokémon you add to your Living Dex collection/hunt — including a form picker for regional forms (Alolan, Galarian, Hisuian, Paldean) and other alternate forms (like Giratina's Origin Forme, the Therian Formes, and Gigantamax) where one applies.
- A Mega Evolution picker in each hunt's edit menu — choose a Mega (like Mega Charizard X) and the sprite, OBS sync, and trading card all switch to that Mega.
- A sprite style picker in each hunt's edit menu: Animated 2D, Static 2D, or the Pokémon's 3D model — plus "Your own sprite" for hunts with an uploaded sprite, which is always kept so you can switch back to it. Styles a Pokémon doesn't have are greyed out.
- Can automatically fetch sprites from an online database through one button click using just the Pokémon's name, should you not choose to upload your own — including Pokémon with special forms or punctuation in their names (Giratina, Landorus, Mr. Mime, Farfetch'd, and so on).
- A detailed Pokémon info popup showing your own hunt stats (encounters, time spent hunting, start/end dates) alongside in-game data pulled live — abilities, evolution requirements, Mega Evolutions (with their shiny sprites, types, and Mega Stones), Gigantamax forms, level-up moveset with PP, and wild encounter locations/rates.
  - Flip through every form and sprite style of a Pokémon with the switchers under its sprite — the popup remembers your last pick for each Pokémon.
  - Click any Pokémon in the Evolution section to jump to its own info popup.
- An automatic session timer that tracks total time actively spent hunting each Pokémon, accumulating across sessions, and counts up in days, hours, and minutes. It switches from "hunting" to "hunted" once the shiny is found.
  - Edit a hunt's time (days / hours / minutes / seconds) and its start/end dates from the edit menu — handy for picking up a hunt already in progress.
- Free-text notes for each hunt — jot down your location, method, or the story behind the find.
- Phase tracking: log a "Phase 1," "Phase 2," etc. whenever a different shiny shows up while you're hunting, without losing or interrupting your original hunt's progress — with the option to also add the phased Pokémon to your Completed dex, carrying over the hunt's encounter count and time.
- A customizable counter key, so you can increment your encounter count with a single keypress instead of clicking.
- Controller support — increment, decrement, and navigate the whole app with a gamepad (see [Controller Controls](#controller-controls) below).
- Live OBS integration — push your active hunt's sprite, name, encounter count, and hunt timer straight onto your stream in real time (see [OBS Integration](#obs-integration) below).
- A "Mark shiny found" button that celebrates with confetti and a jingle, and marks the Pokémon in your Pokédex as caught.
  - Tag a find as a square shiny or a star shiny.
- Shareable trading cards: turn any completed hunt into a downloadable trading-card image, with a holo foil border, a frame colored by the Pokémon's type, your hunt stats, your notes as flavor text, and a collector number.
  - Cards open in an interactive viewer with a rainbow foil that follows your mouse or finger, with the Pokémon's animated sprite playing on the card.
  - Download a card as a PNG, or as an animated GIF when the sprite is animated. On phones, cards can also be shared straight from the viewer.
  - Legendary and mythical Pokémon get premium cards: a gold (legendary) or iridescent (mythical) metallic border, a starfield background, a rainbow art window, a tier badge, and extra glitter in the viewer.
- Profiles (save slots): keep a separate Pokédex, Living Dex, stats, and settings for each game or save file, and switch between them instantly.
- Confirmation popups before deleting a hunt or a profile, so nothing gets removed by accident.
- Data export/import to a CSV spreadsheet file for backups — opens right up in Excel, Google Sheets, or Numbers.
  - Optional auto-backup that downloads a fresh backup file on a timer you choose.
  - Data is also stored locally, in case you forget to export to a file.
- Short, but sweet, sound effects.
- A light and dark mode.
- Custom icons that look the same on every device, instead of your phone's or computer's emoji.
- Mobile support coming soon.

## How to Use:

1. Visit: https://moonflowah.github.io/Shiny_Counter/
2. Click to open the program.
3. Enter the name of the Pokémon you want to hunt down in the indicated text box field.
4. If you don't have a custom sprite/3D model .gif to add, click the "Try Fetch Shiny" button to try and fetch the sprite from the database.
   - If the fetch doesn't work, double check the Pokémon name spelling.
   - If the spelling is correct and the fetch still doesn't work, it isn't in the database and a custom sprite .gif file is required.

   > Custom sprite/3D model .gif files can easily be obtained from this site: https://projectpokemon.org/home/docs/spriteindex_148/

5. After a link is fetched from the database, or your custom sprite is uploaded, click the yellow "Add Pokémon" button at the bottom.
6. The counter at the top should display the newly added Pokémon of your choosing when selected from the Pokédex, and the counter will be free to use.

## OBS Integration:

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

Once connected, the sprite is pushed as the animated shiny GIF (regional forms included) with a clean, transparent background, so it composites over your overlay with no black or white box behind it.

**Extra options:**

- **Compact mode** — sends a single "Name · Count · Timer" line to one text source instead of using three separate sources, for a smaller overlay.
- **Milestone alerts** — every set number of encounters (100 by default), the sprite source briefly switches to a celebration graphic before going back to your Pokémon. This needs a sprite source picked.
- **LCD count style** — styles the count source in the same bold, digital-screen font as the tracker.

## Controller Controls:

Connect any standard gamepad and it's picked up automatically — a "Controller connected" message appears once it's detected.

- **A** — +1 encounter
- **B** — -1 encounter
- **X** — toggle "Mark shiny found"
- **Y** — open the info popup for your active hunt
- **D-pad Up / Down** — move the active-hunt selection through your current tab's roster
- **D-pad Left / Right** — switch between the Active / Paused / Completed / Living Dex / Stats / Settings tabs
