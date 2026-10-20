# Boss Rush — Black Flash Remake, Evil Zach Ultimate Rework & Fella (v13)

This is the **flat-file** edition. Keep `index.html`, all `.png` files, and all `.mp3` files together in the repository root. The game does not require an `assets/` folder. Keep every filename unchanged.


## Version 13 — Black Flash, laser, and Boss 6

- Evil Zach's Black Flash is rebuilt around a committed, aimed dash. The attack only triggers its full-screen impact-frame cinematic on a confirmed hit; the cutscene uses stark black/white/red frames, a black-core slash, fractured cursed-energy lightning, manga speed panels, impact shock rings, and a `BLACK FLASH / 黒閃` title.
- Evil Zach uses his M1 slash / reverse slash / stab combo more frequently and pressures the player more aggressively.
- Evil Zach's ultimate laser has a new compressed-singularity charge, a narrow layered beam with red/black energy strands, fast pixel slugs, lens glints, electrical cuts, strong source flare, arena shake, and a clearly preserved safe pocket on the right. The actual hit lane is narrow and matches the slim core; players caught by it take 5 damage at each 0.05-second tick and are temporarily movement-locked. The ultimate track fades to silence by 10 seconds while the laser continues for 16 seconds.
- Added **Fella**, Boss 6, with the supplied sprite and `Vs. Randy boss 6.mp3` soundtrack, a baseball stadium arena, baseball-bat three-hit combo, telegraphed rush, heavy slam, ketchup volleys / sauce curtains, and minion throws. Ketchup puddles slow movement while inside them rather than causing hidden repeated damage.
- Added Fella's dialogue, phase interactions, character-specific / party-size taunts, boss-select entry, and achievement. Network snapshots now carry slow-puddle state and Fella's attack animation state.

## Publish with GitHub Pages

1. Upload all files in this folder to the root of your GitHub repository (not into a nested folder).
2. Commit the files.
3. In **Settings → Pages**, select **Deploy from a branch**, branch `main`, folder `/(root)`.
4. Open the published Pages URL and hard-refresh with `Ctrl+F5`.

## Controls

Default keys (all of them can be rebound in **Settings → Controls**, two slots per action):

- **WASD / Arrow keys** — move
- **Mouse / Click** — aim and attack
- **Q / E / R** — character abilities
- **H** — show or hide collision hitboxes
- **M** — mute or unmute
- **P** — pause in solo boss fights
- **1 / 2 / 3** — select an upgrade
- **Esc** — open or close Settings (also the SET button in a fight, or SETTINGS on the title screen)

## Settings menu

Everything saves automatically in the browser (localStorage) and is client-side only, so it is safe in multiplayer.

- **Audio** — Master, Music and Sound Effects volume from 0% to 200%, mute, mute when the window is unfocused, test sound.
- **Gameplay** — Auto Shoot, Auto-Use Abilities, Auto Aim (strength 10–100%, target priority, target marker), fire button (any / left / right), solo game speed 50–150%, auto-pause on focus loss, skip dialogue (host), hitbox view.
- **Visual** — screen shake 0–200%, flash intensity, particle amount, glow, ambient sparkles, boss auras, vignette, damage flash, low-HP pulse, damage numbers and size, FPS counter, control hints, crosshair style / size / color, hide system cursor, Performance and Quality presets.
- **Controls** — rebind movement, abilities, keyboard attack, upgrade voting, pause, mute, hitboxes, and keys that toggle Auto Shoot / Auto Aim / FPS.
- Opening Settings pauses a solo fight. In multiplayer the game keeps running, but your character stops responding while the menu is open.

Audio playback starts after the first click or key press because browsers require a user interaction before audio can play. The Phase 4.5 visualizer reads the soundtrack's live frequency data when the browser's Web Audio API is available.


## Zach M1 and attack-effect remake

- Zach's basic knife attack is now a repeating **slash → reverse slash → stab** combo. The two slash animations travel in opposite directions; the stab has a forward-thrust animation and a 1.25-second recovery after the animation.
- Each M1 strike creates its own directional hitbox. Press **H** to see the hitbox for the current strike, and each strike can hit a boss only once.
- Multiplayer snapshots include Zach's M1 animation and hitbox state so other players can see the combo.
- Attack particles now render as context-appropriate bubbles, shards, sparks, streaks, healing crosses, and diamonds instead of uniform squares. Projectile trails and glows are tinted to match their projectile type.

## Balance and party-dialogue update

- Boss 4's Bao now starts at **2,400 HP**, matching Boss 1, and UnCoolguy16 starts at **3,500 HP**, matching Boss 2. Difficulty, multiplayer, and loop scaling still apply. The Alliance Link no longer heals the surviving boss above those baseline health totals; the survivor gets its next attack sooner and keeps the existing faster movement behaviour.
- Boss dialogue now branches for solo, two-player, and larger-party runs. Coolguy15 and Zach each have their own reactions; mixed-character parties get both voices, while unselected character dialogue is not added. This also updates the Phase 4.5 last-stand response and the victory conversation.

## Update highlights

- Revised story continuity: UnCoolguy16's broken regulator causes the pressure pulse; Evil Spong's bubble wards contain the flood; the core creates two combat echoes; defeating them begins the timed purge; Evil Zach is the core's final player-like combat echo.
- Boss health is balanced across the roster, including Boss 4 returning to the Boss 1 / Boss 2 health baselines.
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

## Zach pixel stab animation update

- Reworked Zach's stab into a visible pull-back, fast forward lunge, and recovery/recoil pose.
- Replaced smooth glowing thrust ribbons with grid-aligned pixel tiles, chunky hit flashes, square debris and pixel foot-dust.
- Made stab hit particles render as crisp square pixels with a warm gold/orange/ivory palette.

## Encore, Evil Zach and maps remake

- **Dialogue** rewritten to be lighter and funnier. All Core / Purge / Warden lore is gone: Bao and UnCoolguy16 simply team up for a rematch, and Phase 4.5 is their entrance-music encore.
- **Phase 4.5 remake ("The Encore")**: Bao and UnCoolguy16 now stand in the top corners and throw 12 waves built from their own attacks. Boss 1: Dumpling Downpour, Chopstick Crossing, Steam Pistons. Boss 2: Bullet Curtain, Pipe Lattice, Sniper Alley. Boss 4 duo moves: Twin Sweep, Steam Blossom, Regulator Overload, Echo Crossfire, Alliance Spiral, and Ladle & Pipe Smash.
- **Visualizer remake**: gold (Bao) and red (UnCoolguy16) stage with spotlights, kitchen steam, a dumpling-and-bullet equalizer, a sound ribbon linking the two hosts, and a dumpling and bullet orbiting the centre. It is drawn behind players and projectiles so it never hides attacks. The OVERDRIVE bar and label are removed (the loud-music effects still scale with intensity).
- **Boss 5 remake**: Evil Zach keeps dodging player fire, but fights with stolen Zach moves. Combo Strike is a telegraphed slash, reverse slash and stab. The rest are Knife Whirl, Copycat Trail (ghost stabs where you recently stood), Burger Toss, Knife Juggle, Clone Circle, Backstab and Final Cut (phase 3), alongside some of his old knife attacks.
- **Boss maps**: each arena now has its own set dressing. Kitchen (tiles, lanterns, steamers, stove flames), pipe room (pipes, warning lamps, vents, hazard stripes), underwater (light rays, kelp, coral, jellyfish, bubbles), alliance stage (banners, footlights, split floor) and Evil Zach's dojo (mirrors, spotlights, knife scars, audience).


## Evil Zach ultimate, cactus attack & last stand update

- The pre-Phase 4.5 dialogue is rewritten as a desperate last stand.
- Boss 2 can call down falling cactus hazards with warning markers and green pixel-style effects. During the pipe spin, UnCoolguy16 actively closes distance on the player instead of staying planted.
- When Evil Zach reaches 0 HP, he interrupts the defeat with the line “Let’s larp.” He teleports to the far-left center, flashes the ultimate artwork with a 3-second fade, charges for 1 second, then fires a 16-second, full-width layered laser. The laser shakes/flashes the screen and has a tiny marked safe pocket at the far-right center. Outside that pocket, it deals 5 damage every 0.05 seconds and locks player movement. Evil Zach is defeated when the beam ends.
- The ultimate uses the included `Nande (evil zach ultimate).mp3` track and pauses the boss music while firing. Music pauses while the game is paused, Settings is open, or the browser tab is unfocused.


## Evil Zach combat and ultimate fix (v12)

- **Smaller laser:** Evil Zach's ultimate beam is now a narrow horizontal lane rather than a screen-filling column of damage. The visible core and collision band match more closely, and the safe zone is clearly marked at the right-center edge. Players outside the beam are not damaged by it. Players intersecting the beam take 5 damage every 0.05 seconds and are locked while caught in it.
- **Ultimate timing/audio:** after the “Let's larp” dialogue and teleport to the far-left center, the ultimate artwork flashes and fades over 3 seconds, followed by a 1-second charge and a 16-second laser. The supplied `Nande (evil zach ultimate).mp3` track fades from 10 seconds into silence at 13 seconds; the laser continues to 16 seconds. Boss music remains muted during the beam. Audio pauses while the game is paused, Settings is open, or the browser tab is unfocused.
- **Boss select/music:** the lobby's “Start at boss” control now cycles through all five bosses. The chosen boss track is restarted when a run starts, including Boss 2's `m2` music.
- **More aggressive Evil Zach:** his movement closes distance sooner, and he selects the three-hit M1 combo more often with a shorter recovery.
- **Black Flash:** a new telegraphed dash attack aims toward the active player. A confirmed hit deals damage and triggers a 2.65-second impact cutscene with impact-frame flashes, speed lines, jagged red/white cursed-energy bolts, screen shake, and a bold BLACK FLASH title. A missed dash does not trigger the cinematic.

The game remains a flat-file project: keep `index.html`, every image, every soundtrack, and this README together in the repository root.


## Boss Rush update (v13)

- **Tomato sauce puddles:** staying in a ketchup puddle now deals 1 damage every 0.25 seconds. Damage ticks while the player remains inside; shields still absorb one tick.
- **Evil Zach ultimate:** the horizontal laser is much wider and brighter, with a larger, clearly labelled safe pocket at the far right. Screen shake, rapid flashes, and excess beam particles have been toned down. The ultimate track stays audible for the full 16-second beam and fades during its final 0.35 seconds.
- **Fella, boss six:** added bouncing baseball-bat volleys, delayed multi-point sauce geysers that launch extra globs, and a two-pass stampede that paints damaging sauce trails. The new attacks have warning cues so players can react and dodge.
