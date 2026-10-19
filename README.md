# Boss Rush — Lore, Boss Combat & Phase 4.5 Update

This is the **flat-file** edition. Keep `index.html`, all `.png` files, and all `.mp3` files together in the repository root. The game does not require an `assets/` folder. Keep every filename unchanged.

## Publish with GitHub Pages

1. Upload all files in this folder to the root of your GitHub repository (not into a nested folder).
2. Commit the files.
3. In **Settings → Pages**, select **Deploy from a branch**, branch `main`, folder `/(root)`.
4. Open the published Pages URL and hard-refresh with `Ctrl+F5`.

## Controls

- **WASD / Arrow keys** — move
- **Mouse / Click** — aim and attack
- **Q / E / R** — character abilities
- **H** — show or hide collision hitboxes
- **M** — mute or unmute
- **P** — pause in solo boss fights
- **1 / 2 / 3** — select an upgrade

Audio playback starts after the first click or key press because browsers require a user interaction before audio can play. The Phase 4.5 visualizer reads the soundtrack's live frequency data when the browser's Web Audio API is available.

## Update highlights

- Revised story continuity: UnCoolguy16's broken regulator causes the pressure pulse; Evil Spong's bubble wards contain the flood; the core creates two combat echoes; defeating them begins the timed purge; Evil Zach is the core's final player-like combat echo.
- Boss health increased across the roster.
- Each boss has extra attack patterns. Evil Spong's active attack pool is bubble-based: aimed bubble sprays, pressure mines, radial waves, bubble prisons, rotating bubble patterns, tsunami volleys, bubble meteors, tornadoes, popping bubbles, geysers, and refraction volleys.
- Boss 4's two enemies have separate health bars and use their original solo attack pools, with additional coordinated duo attacks.
- Phase 4.5 is a 93.179-second survival phase timed to the supplied *Overdue* MP3. It cycles through eight map-wide attack patterns, updates warnings, hazards, and projectiles during the phase, and draws a live audio-reactive spectrum with additional arena effects.
- Evil Zach still evades player fire and now has additional knife patterns.

## Notes

The game uses PeerJS for online rooms and needs a working internet connection for the PeerJS library. The included game and media files are all intended to sit alongside `index.html` in the repository root.

## Remake update (bosses 3-5)

- Lore after boss 2 rewritten: Evil Spong is the Warden of the Ward Chambers, the Pressure Core wakes and builds echo guardians, the Purge hunts the exit, and Evil Zach is the core's final player-echo test.
- Boss 3: new Bubble Helix and Bubble Collapse attacks.
- Boss 4: new duo attacks (Twin Sweep, Regulator Overload, Steam Blossom, Echo Crossfire).
- Boss 4.5: new music-reactive visualizer (warp tunnel, kaleidoscope rays, mirrored spectrum ring, waveform ribbons, beat shockwaves, burst particles, lens flare, beat flash).
- Boss 5: new Afterimage Barrage, Knife Rain and Prediction Grid attacks.

## Overhaul update

- Lore rewritten end to end around the Hearth Core ("The Grand Steamer").
- Boss 4 rebuilt: three phases driven by combined health, Alliance Link (survivor heals 25% and enrages when one partner falls), choreographed movement per phase, new Link Beam attack.
- Boss 1: remade Steam, new Dumpling Flower, Steam Piston, Chopstick Cross. Boss 2: new Sniper Lines, Bullet Rings, Pipe Storm. Boss 3: remade Bubble Spray.
- New ambient effects: boss auras, drifting motes, vignette.

## Menus, achievements and Purge update

- Fixed a load-order bug that left the game blank on open (Link Beam was registered before the attack table existed).
- New title screen with Play, Host Online, Join Room (paste a link or code), Achievements and Music Credits.
- Achievements (12) are saved in the browser and shown as pop-up toasts. Music credits list every track. Add original artist names to the `MC` list in `index.html`.
- Rebuilt multiplayer lobby: room code chip, copy link, player slots with host marker, styled character cards, room settings, pulsing Start and a Leave button.
- Phase 4.5: 12 attack waves instead of 8, attack pace follows the music's intensity, and effects scale through CALM, RISING, FRENZY and OVERDRIVE (edge sparks, lightning, chromatic rings, strobe lines, comets, screen shake).

## Balance and robustness update

- Boss health reduced about 15%. Boss attacks are slightly easier (damage x0.88, projectiles 8% slower, telegraphs 10% longer).
- Boss 1 gains Ladle Combo, Rolling Pin, Dumpling Bounce, Steam Valve and Broth Tide.
- New melee attacks: Pipe Smash and Gun Whip (boss 2), Spatula Slap (boss 3), Tag Team Smash (boss 4), Knife Flurry (boss 5).
- UnCoolguy16 picks gun attacks more often.
- The game now draws immediately with a loading bar, shows a red error banner if the script fails, and explains when PeerJS cannot load.

## Hitbox, Evil Spong and lore update

- Evil Spong now shows his own portrait in dialogue (it used Bao's before).
- Evil Spong uses his spatula in phase 1: Spatula Throw, Spatula Spin and Spatula Slap.
- Player hitbox 20 to 15 px. Boss hitboxes about 18% smaller (boss 4 partner 55 to 44 px). Press H in game to see them.
- Lore rewritten: every boss wants the players dead. Bao is a vain theatrical chef, UnCoolguy16 a bitter deadpan saboteur jealous of "cool", Evil Spong a cold formal warden, Evil Zach a smug mimic. Their grudges against each other drive the dialogue.
