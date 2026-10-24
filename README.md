# Boss Rush — Black Flash Remake, Evil Zach Ultimate Rework, Fella, Jay, Terry, Adrian & The Hover Trio, Hateful Doom and Coolguy17's Rush (v39)

This is the **flat-file** edition. Keep `index.html`, all `.png` files, and all `.mp3` files together in the repository root. The game does not require an `assets/` folder. Keep every filename unchanged.


## Version 39 — Coolguy17's rush

- **Second pass on Coolguy17 #1:** the first encounter's music was not playing, because the fight snapshot left out the track name and the game asked for an undefined track. It now plays Icicle Ignition II. Cooldowns are about 20% shorter, and fire and ice attacks (fire and ice zones, fireballs, ice shards) are picked much more often. The fog now covers the whole screen, including the boss, the players and the HUD, instead of only the background.

- **Rush picker.** The lobby has a RUSH row under the character cards: REGULAR RUSH (the default) and COOLGUY17'S RUSH. The host sets it in the room settings, and every player sees the same choice. The regular rush is unchanged.
- **Coolguy17's roster.** Boss 3 (Evil Spong) is replaced by Coolguy17 #1 (the first encounter). Boss 5 (Evil Zach) is replaced by Coolguy17 #2 (the rematch). Coolguy17 #3 (the second last) comes after the Hover Trio. The other bosses are unchanged, and the boss count becomes 8, so "Start at boss" goes up to 8 in this rush.
- **Coolguy17 #1 — 7,777 HP** (scaled by party size and difficulty). Dashes, fire and ice zones that drop in after a warning, laser sweeps, fireballs, ice shards, and two copies of Evil Spong's attacks (bubble ring and spatula slam). He dodges incoming shots. The map is a snowy forest with fog that covers the screen for a few seconds every 24 seconds. At 10 HP he says "..." and "I'm not ready yet", teleports away, and the upgrade screen follows.
- **Coolguy17 #2 — 17,000 HP** (the rematch, scaled the same way). Spear: a guard that reflects player shots back at the shooter, a counter lunge once the guard drops, a melee thrust with a warning arc, a spear volley (warnings land first, and the spears fly through them 1.2 s later), a three-spear throw, lasers, and two copies of Evil Zach's attacks (burger rain and knife fan). The map is a dark cave with glowing plants. Every 16 to 22 seconds the map darkens and the camera zooms in on a player. He leaves at 10 HP the same way as #1.
- **Coolguy17 #3 — second last, 33,000 HP** (scaled the same way). Pan: a guard that reflects shots, a pan boomerang that arcs out and splits into four mini pans which home in before flying straight, a close-range pan swing that stuns players for 1.2 s, egg lobs that split into eight eggs where they land, a food shower, lasers, fire zones, fireballs and dashes. The map is an orange desert with dunes, a sun and embers. At 0 HP he says "Seems like we're near the end…" and "cya there kid(s)", and the run is cleared.
- **18k speed-up.** When #3 drops to 18/33 of his maximum HP (18,000 at one player, scaled with the party), he says "how about we speed up the process". The last-stand song restarts, a digital countdown of the song's remaining time appears in the background, his attacks hit 20% harder, his cooldowns are 30% shorter, and he uses the pan more often.
- **Explosion ending.** If the song runs out with Coolguy17 still standing, the screen flashes, explosions roll across the arena, the screen fades to black, and the players return to the lobby. The rush stays set to Coolguy17's.
- **Status effects.** Burn (fire): 3 seconds of damage over time. Ice: slows movement, and three ice hits in a row freeze a player for 0.7 s. Stun (pan): the player can't move or attack for 1.2 s. Each has an icon above the player.
- **Trio steal.** In this rush, if the Hover Trio is nearly beaten (under 12% of their combined HP), Coolguy17 #3 interrupts and takes over. There is no upgrade screen in between.
- **Multiplayer.** The fights run only on the host. Clients receive a copy of the fight in each snapshot (`snap().c17`) and draw it, the same way the secret boss works.
- **Assumptions (please check):**
  - Coolguy17 #1 and #2 are not killed. They leave at 10 HP, which matches their death dialogue (they teleport away).
  - Only one track was supplied for #3, so the speed-up restarts PAN FRIED PIZZA rather than playing a separate last-stand song.
  - "Steals all your kills" is read as the Trio being taken over once it is under 12% of its combined HP.
  - The intro cut scenes (Evil Spong being killed and the upgrade-card animation) are simplified to dialogue and a flash.
- **Testing note:** checked headless in Chromium with 29 scripted checks: the roster swap; all three encounters from spawn to their endings; the 10 HP escape; the guard reflect and counter; the rematch darkness event; the Trio steal; the 18k speed-up; the countdown and the explosion back to the lobby; the second-last defeat; status effects; a snapshot round trip for clients; and the regular rush unchanged. Zero page errors. The lobby, all three maps, the spear guard, the pan, the countdown and the explosion were reviewed as screenshots. Not played by hand, so the balance (HP, damage and cooldowns) still needs a real run-through, and the two-browser online session was not run.
- **Known, not changed:** the final fight after Coolguy17 #3 is not built, so the run ends after the second last. The music credits list has no entries for the three new tracks yet; the credits screen already runs past the bottom with ten rows.

## Version 38 — new character: Adrian

- **New character: Adrian** (the tooth-blob with the boomerang). Lobby card: "Boomerang M1. Last Stand: rise once per boss for 15 s, faster." He has 110 HP.
- **M1: Boomerang.** He throws a boomerang that flies out about 340 px along his aim, slows, and curves back to his live position. It hits each boss once on the way out and once on the way back, for 28 damage per pass (56 on a boss that is in the path both ways). It clears enemy shots it passes within 24 px. Cooldown is 0.95 s. If he is caught or the boomerang has been out for 1.6 s, it is removed.
- **Q: Snap Trap** (9 s cooldown). A dashed ring with two jaws appears about 230 px ahead on the aim line. After 0.9 s the jaws close on that spot: 60 damage to any boss inside, and the boss is **exposed for 4 s**, taking 25% more damage from every source. The label "EXPOSED +25%" shows under the boss.
- **E: Decoy Echo** (12 s cooldown). A faded copy of Adrian stays where he cast it for 5 s. It throws a boomerang at the boss about every 1.1 s, so he can reposition while it works. The decoy's tag sits under its ring.
- **R: Gum Wall** (10 s cooldown). A sticky pink wall, 200 px long, appears about 90 px ahead for 4 s. A boss shot that hits it is sent back at the boss at 1.5x damage.
- **Passive: Last Stand.** On death, if it has not been used yet on this boss, he does not fall. He returns at 45% HP (50 of 110) with 1.2 s of invulnerability, and the revive plays a burst of pink and green rings, sparks, shards and a "LAST STAND!" pop-up. For the next 15 s:
  - All cooldowns are capped at 0.6 s, and abilities re-cast at 0.6 s.
  - His attacks come 1.7x as fast (attack gap 0.95 s becomes about 0.56 s) and hit 1.25x as hard.
  - A timer shows as "LAST STAND 14.5s" above the ability bar and as a pink ring under his feet, which empties as the time runs out.
  - When the 15 s run out he dies for good. If the rest of the team is still alive, he stays down until the next boss.
- **Assumption (please check):** "once" means once per boss, not once per run. The use is reset when each new boss spawns. If you wanted it once per run, this is one line in the reset code.
- **Multiplayer:** all of Adrian's boomerangs, traps, decoys, walls and the Last Stand timer are spawned and timed by the host and sent in each snapshot. Damage is applied by the host only, as for the other characters.
- **Fixes after the first screenshots:** the DECOY tag no longer covers the YOU and HP tags. The EXPOSED label sits under the boss instead of under the top HUD bar. The LAST STAND! pop-up is raised above the YOU tag, and the timer ring moved from over his head to under his feet.
- **Testing note:** checked headless in Chromium: the boomerang's out and return hits and its one-hit-per-pass lock; the Snap Trap damage (60), exposure (3.9 s left right after the snap in the test), and the 25% bonus on the next hit; the decoy's life and boss damage; the wall's reflection; the Last Stand's timer (15 s), HP (50), cooldown cap, faster attacks, death when the timer ends, and no second revive on the same boss. Smoke sweep: 84 combinations including Adrian, no errors. Two-browser multiplayer session over the local PeerJS server, no errors. Six screenshots were reviewed. Not played by hand, and balance (damage and cooldowns) has not been tested against a real player.
- **Known, not changed:** the "Chosen upgrades" line on the vote screen still runs off the edge with many upgrades.

## Version 37 — vote countdown, tie reveal, run upgrade list, meteor and lightning remade

- **Multiplayer vote countdown.** Once everyone has voted, a 3-second "NEXT BOSS IN" countdown runs before the next boss. Votes are locked during it. Solo runs skip the countdown.
- **Tie reveal.** If the votes tie when the countdown ends, the screen shows "TIE!", how many upgrades were tied, and which one won (the random pick), for 2.5 s before the boss. A clear winner goes straight to the boss.
- **Pause menu shows the run's upgrades.** The panel is wider, with an "UPGRADES THIS RUN" list on the right: each upgrade once, with a count if you took it more than once (for example "2x Quick Hands"). Upgrades are shared by the team, so this is the same list for everyone.
- **Meteor Call remade.** Every 10 s a reticle closes in on the boss ring while a burning meteor falls in from the top right. It lands with a white flash, a crater ring that expands and fades, and cracks. The damage is unchanged (120 x dmg).
- **Static Shock remade.** Every 3 s a jagged lightning bolt drops from the top of the screen onto the boss, with a flicker, branches, a glow and a strike ring. The damage is unchanged (30 x dmg).
- **Multiplayer:** the meteor and bolt are spawned and timed by the host, and their state is sent in each snapshot, so online players see the same effect at the same point. Damage is applied by the host only.
- **Testing note:** checked headless with a second player added: a tie (countdown, reveal, boss), a clear winner (countdown, no reveal) and solo (no countdown). Screenshots were checked for the meteor, the bolt, the countdown, the reveal and the pause list. The smoke sweep of 70 combinations ran with no errors, and a two-browser session ran over the local PeerJS server with no errors. Not played by hand, and the vote countdown was not run over a real network.
- **Known, not changed:** the "Chosen upgrades" line on the vote screen runs off the edge once there are many upgrades.

## Version 36 — Patrick rock mode and Eureka, SpongeBob faster, optimisation

- **Patrick: Eureka Burst has a Rock mode variant.** In Rock mode the burst also throws a ring of 8 pet stones outward (10 stones with one Double Tap, and so on). Each stone flies until it hits a boss, at 17.5 damage before boss-side modifiers, and it hits each boss once. SpongeBob mode keeps the plain burst. The lobby card now says "Rock: + stone shower".
- **Patrick: pet rock redrawn.** `Patrick rock.png` is a new lumpy grey stone with a black outline, a glint, cracks and speckles. Same 100 x 100 size and filename.
- **SpongeBob mode fires every 0.5 s** (was 0.8 s). The interval is one constant, `PSB_SHOT`, near the Patrick code.
- **Optimised: Hateful Doom (secret boss 8).** In a profile of the fight, drawing the stage and its particles was the heaviest part of the frame.
  - Particles are drawn without a save, translate, rotate and restore for each one. Points are rotated by hand. This was about a quarter of the frame time.
  - The static vignette is painted once and then blitted. The sun's halo fills only its own box. The floor grid is one stroke. The 64 spokes are batched into one stroke per colour and alpha step.
  - Measured in headless Chromium on the same seeded 600-frame fight, the render went from about 0.99 ms to 0.50 ms per frame on average (p95 1.5 ms to 0.9 ms). The old and new frames differ by 0.33 out of 255 on average.
- **Optimised: multiplayer.**
  - The host encodes each snapshot once per tick and sends the same string to every client (`sj` messages). Clients still accept the old `s` format.
  - A client sends input as soon as movement, fire or an ability press changes, instead of waiting up to 33 ms for the next tick. The aim angle still goes on the 33 ms tick.
  - Display smoothing toward the latest snapshot is per second, not per frame. It looks the same at 60 Hz and no longer runs faster on 144 Hz screens or slower at low frame rates.
  - Particle events look up their colour's shape once per event, not once per particle. A 1,000-particle burst takes about 0.13 ms to process, down from 0.31 ms.
  - The snapshot payload is the same size as before.
- **Testing note:** checked headless with two real browser pages joined through a local PeerJS server. The session ran with no errors and the client moved in step with the host. A smoke sweep of 70 combinations (every boss, five characters, both Patrick modes, plus the secret fight in Rock mode) ran with no errors. The Eureka stone shower was checked for count (8), damage (17.5) and kind, and the SpongeBob interval was checked (3 shots in 2 s, which 0.8 s would not give). Not played by hand, and the sandbox has no real internet path, so real latency and balance still need a real run-through. The input-to-screen latency numbers in the sandbox were too noisy to claim an improvement.
- **Not changed, for later:** client-side prediction for your own character (the biggest remaining multiplayer lag), and the host's game pausing when its tab is hidden, because the simulation runs on the render loop.

## Version 35 — full dialogue reference applied

- **Replaced:** every boss intro, phase-change, outro and cameo line, the Coolguy15 / Zach / Jay / Terry / Patrick character lines, the Trio opening, outro and win lines, the secret-boss trigger and win lines, the copy banners, the timeout banner, the encore header, hint and footer, and the Fella field label.
- **Added:** the Boss 4, Boss 5 and Boss 6 extra lines, the Trio crowd line for Fella, the secret-boss trigger ("That's NOT mason…"), the Patrick and Evil Spong scene (plays at the Evil Spong intro when Patrick is in the run), and the Boss 7 final tally.
- **Removed:** the old INTRO, PH, OUTRO, WIN, PARTY_TAUNTS and PARTY_REPLIES arrays, which the reference listed as unused.
- **Changed or cut on purpose:**
  - Slurs and self-harm/insult lines (the "NIG" and "NI-" lines, "tards", "kys").
  - Racial caricature: the mock-accent spellings (Herro, rittle, rike, rost), the "racial caricature" line, and the Chinese-language "I like men / me too" exchange.
  - Dog-eating stereotype lines ("I eat puppies", "neighbours pets"). The solo intro now uses a different joke.
  - Sexual lines ("sucky tongue", "suck balls", "gone gay", "beat me off", "Suck this!").
  - Genocide references in the Fella squad intro.
  - Boss 4's "virgin boy eggs" line (replaced with "soup eggs").
  - Boss 6's "several abuse charges" (now "several charges").
  - "CHINESE STEROID TECHNOLOGY" is now "STEROID TECHNOLOGY".
  - Mother-insult lines are reworded to keep the same joke.
- **Open decisions:**
  - Copy banners: the reference lists six copy attacks. The game also copies four others (SNIPER LINE, SPIRIT CHASE, PINBALL RICOCHET, PIZZA BOOMERANG) that are not in the reference. They are kept.
  - Timeout: the reference says the banner is "It's over." and also that "Time ran out…" is shown instead. The banner now reads "It's over."
- **Testing note:** checked headless: compose() across all 7 bosses, every party size, and every character combination (196 cases) with no errors; the intro and the secret-boss trigger both play and return to the fight; the earlier fight tests still pass.

## Version 34 — bug fix

- **Equipping Patrick no longer crashes:** the state snapshot read `p.m.size` before Patrick's stats were set, so equipping him in the lobby threw "Cannot read properties of null (reading 'size')" every frame. The read is now guarded, matching the existing guard for orbit.

## Version 33 — Patrick: slam, orbiting rocks, Eureka Burst

- **Knife removed:** Patrick no longer draws the generic knife.
- **Belly Flop:** while you hold M1, a ring on the ground shows exactly where you will land and how wide the slam will be. The ring fills as the charge builds. On release Patrick hops up with a shadow that shrinks, squashes on landing, and the slam leaves an expanding shock ring, cracks spreading out, and dust.
- **Damage x1.75:** every Patrick damage source is multiplied by 1.75: slams and aftershocks, orbiting rock chip damage, food that hits bosses, and Eureka Burst.
- **Rock mode (Q):** summons pet rocks that orbit Patrick and block enemy shots. Double Tap adds one more rock. Q does nothing while rocks are already orbiting. They last 12 s, with an 8 s cooldown. The old place-and-swap is gone.
  - Smaller hitboxes: a shot is blocked within about 14 px of the rock's centre (was 26 px), and a rock chips a boss only when touching it within about 30 px (was 58 px).
- **Eureka Burst (E, replaces Think Hard):** Patrick thinks for 1 s (a lightbulb glows over him and the burst range fills in), then bursts. The burst clears enemy shots within about 190 px and damages bosses in range. His next belly flop hits 50% harder for 5 s. Cooldown 14 s.
- **Mode label:** "ROCK MODE" or "SPONGEBOB MODE" now shows above the ability bar, not on the character.
- **SpongeBob heal:** 1.5–3.5% of max HP per food (was 1–3%).
- **Testing note:** checked headless: orbit radius and blocking, the second-Q block, the charge ring, a real mouse-held charge that hops and slams (11 cracks), Eureka timing, the clear and buff, heal range 1.9–3.8%, all 26 upgrades, and screenshots. Not played by hand, so balance still needs a real run-through. Eureka's damage and the 1.75x multiplier are unverified against the bosses' HP.

## Version 32 — Patrick: 105 HP, Rock and SpongeBob modes

- **HP:** Patrick now has 105 HP (was 160).
- **Switch Mode (R):** flips between Rock mode and SpongeBob mode. It has a short cooldown, and Ghost Step halves it. A label above Patrick shows the current mode. **Gas Cloud is gone:** R was the only free key, so the third key became the switch.
- **Rock mode (Q):** the pet rock from before. Q places it, and Q again swaps places with it.
- **SpongeBob mode (Q):** SpongeBob pops in where Patrick stands and stays for 5 seconds. Every 0.8 s he fires a food item (burger, or one of the Jay food sprites) at the nearest player.
  - Food that touches a player heals them 1–3% of their max HP.
  - Food that touches a boss does 5 damage.
  - Only one SpongeBob can be out at a time. He has a 10 s cooldown after placing.
- **Effects:** SpongeBob bobs and pops in with an overshoot. He squashes and stretches on each shot, with a muzzle ring and sparks. Food spins with a trail, and heal numbers float up when it lands.
- **Upgrades in SpongeBob mode:** Double Tap fires an extra food per volley. Big Bite makes SpongeBob and the food bigger. Piercing adds 25% per level to heals and boss damage.
- **Testing note:** checked headless (mode switch, duplicate blocking, the 5-second lifetime, the 2.9% heal, all 26 upgrade configurations, and a screenshot). Shot cadence was checked by reading the timer, not by counting shots. Not played by hand, so the balance still needs a real run-through.

## Version 31 — Patrick remade from scratch

Patrick's old kit borrowed too much from other characters, so the whole kit is new. None of it is a copy of Coolguy15, Zach, Jay or Terry.

- **Stats:** 160 HP, speed 205.
- **Passive, Stillness:** standing still for one second builds a rock stance (+30% damage dealt, -25% damage taken). Moving drops it. A grey ring shows when it is active.
- **Basic attack, Belly Flop:** hold to charge (up to 1.2 s), release to leap along your aim. The leap distance and the shockwave both grow with the charge. The shockwave hits each boss once and clears enemy shots. Double Tap adds aftershocks, and Ghost Step halves the recovery. A pink ring shows the charge.
- **Q, Pet Rock:** plants a rock where Patrick stands. It chips bosses and blocks enemy shots for 12 s. Press Q again to swap places with the rock, which is then used up.
- **E, Think Hard:** every enemy shot on screen freezes for about 2.2 s (Double Tap adds 0.4 s), then resumes at its old speed.
- **R, Gas Cloud:** a cloud 150 px in front of Patrick for 5 s (Double Tap adds 1.5 s). It heals every player inside it by 2% per 0.5 s and burns bosses.
- **Upgrades:** damage, speed, HP, regen, crit, lifesteal, shield, shock, berserker, rush, meteor, revive, time warp and Snack Time work through the shared code. Piercing boosts the shockwave, the rock and the gas burn. Big Bite grows the shockwave, rock and cloud. Cooldown Crunch shortens the three abilities. Ghost Step halves the Belly Flop recovery. Explosive Rounds applies to the shockwave.
- **Note:** the SpongeBob sprite is no longer used by Patrick. The file is still in the folder.
- **Testing note:** checked headless (every mechanic on its own, the 24-upgrade sweep, a 4-second real loop, and a screenshot). Not played by hand, so the balance still needs a real run-through.

## Version 30 — Patrick joins the roster

- **Patrick** (150 HP, speed 215, the tank). Sprites are the ones you supplied: the idle frames, the walk frames, the rock and SpongeBob.
- **Passive:** 10% of incoming hits are shrugged off.
- **Pebble Flick (attack):** rock projectiles that use every bullet upgrade: Double Tap (multi), Piercing Rounds, Big Bite (size), Lucky Strike (crit) and Explosive Rounds.
- **Yoink! (Q):** throws SpongeBob along his aim. He swats boss shots out of the air, hits each boss once on the way out and once on the way back, then returns to Patrick.
- **Nap Time (E):** heals 25% of max HP over 3 seconds at 60% speed. Snack Time, Cooldown Crunch and the other cooldown upgrades apply.
- **Rock Roll (R):** a roll that is invulnerable and hits each boss once. Ghost Step cuts its cooldown.
- **Upgrades:** all 24 were run against him headlessly with no errors. The generic ones (damage, speed, HP, regen, crit, lifesteal, shield, shock, berserker, rush, meteor, revive, time warp) apply through the shared code.
- **Story:** Patrick has his own lines in the intro, phase, outro and win dialogue.
- **Testing note:** checked headless (every upgrade, every attack and ability, a run of the real loop, and the lobby). Not played by hand, so the balance still needs a real run-through.

## Version 29 — Hateful Doom health scales with the party

- **Health:** Hateful Doom starts with 16,666 HP (was 9,999). Each player beyond the first adds 50% more: 2 players = 24,999, 3 players = 33,332, and so on.
- **Balance note:** the fight still lasts exactly as long as his song (157 s). Solo, that needs about 106 damage per second, so retune `SEC_TIME` or the health multiplier if it is too hard.

## Version 28 — Hateful Doom: harder to dodge, more chaos

- **Shorter warnings:** every warning in the secret fight is 28% shorter (`SEC_HARD.warn`), and so are the sweep, gaze and pulse telegraphs (`SEC_HARD.tele`).
- **Faster, wider dark shots:** dark bullets fly 25% faster and have a 20% bigger hit radius. Most of them also bend: a random curve that straightens out after about 1.4 s. Spears, homing and boomerang shots stay straight.
- **Faster casting:** enrage is 1.7 (was 1.35). Each cast has a 30% chance of being followed almost at once by another.
- **More live hazards:** up to 14 can be on screen at once (was 9).
- **Chaos shots:** about every 2.2 s (randomly 1.3 to 3.5 s), a black shot is warned at a random screen edge and fires inward at the nearest player. In phase III it fires two.
- **Frozen Echoes** launches at the same higher speed as the other dark shots.
- **Tuning:** all of the numbers above are in one `SEC_HARD` block just under `SEC_LIE`. Set `warn` and `tele` to `1` to get back the old telegraph times.
- **Testing note:** checked headless (every move fired in phase III, a 9-second run of the real loop with chaos shots, no errors). Not played by hand, so the difficulty still needs a real run-through.

## Version 27 — Hateful Doom: eclipse visualizer, particle storm, stranger moves

- **New visualizer ("the eclipse"):** a black sun sits in the middle of the secret stage. Spectrum spokes ring it (red on the left, blue on the right). Each beat throws a shockwave out of the sun and sheds shards. Hi-hats tear the screen with glitch slices, and the floor equalizer is split red and blue. The sun's red and blue fringes pull apart on the bass.
- **Particles everywhere in the secret fight:**
  - Ash and embers drift up the whole fight.
  - Every hit bursts into shards, pixels and sparks (a bigger burst on crits).
  - Phase changes and every new move throw a burst.
  - Dashes and spike eruptions burst on arrival.
  - Gravity wells drain particles inward, sweeps spit sparks along the beam, sigils bleed, shadow orbs trail, and loud spokes throw sparks.
  - Dark bullets leave streaks, and his aura throws sparks.
  - The particle budget is capped, so the Particle Amount setting and the Performance Preset still apply.
- **Three new moves (Hateful Doom now has 21):**
  - **Three of Him** (`THREE OF HIM`): he splits into three identical dark copies that swap places every half second. Only one is real. A red ring flickers under the real one now and then, and his motes stream only from him. When the swapping stops, the real one fires a fan and each copy fires one aimed shot.
  - **Frozen Echoes** (`FROZEN ECHOES`): a ring of black shots hangs around him. Each one wakes in turn and snaps toward whoever is nearest at that moment. Stand still near the ring and it hits you.
  - **Reverse Sweep** (`REVERSE SWEEP`): a black beam sweeps out, then turns round and sweeps back, so the same ground can be hit twice.
- **Misleading banners:** about 1 move in 5 is announced with the name of a different move. The chance is set by `SEC_LIE` near the top of the Hateful Doom section (set it to `0` to turn this off).
- **Balance note:** the three new moves add pressure in phase III, because the Frozen Echoes ring can block new casts while it is pending. Tune `SEC_LIE`, the `dur` in Three of Him, and the `at` timings in Frozen Echoes if the fight feels unfair.
- **Testing note:** checked headless (every move fired once, a timed run of the real loop, and screenshots of the visualizer and the new moves). Not played by hand, so the feel and balance still need a real run-through.

## Version 26 — Trio HP cut, Hateful Doom rework

- **Less HP for the Hover Trio:** Will 2,600 (was 3,800), Jackson 3,000 (was 4,400) and Mason 3,400 (was 5,000). They still scale with difficulty and party size. Tune the `hp` values in the boss 7 entry of the `BD` table.
- **Hateful Doom has 18 moves (8 new):** Grave Spikes (black spikes erupt under players), Gravity Well (a singularity drags everyone in, then implodes), Curse Sigil (sigils lock onto players and follow them), Phantom Double (two shadow copies sweep across and fire), Reaper Crescent (a scythe arc, with a second arc in Phase III), Eclipse Gaze (a line tracks the nearest player, locks, then fires a black beam), Black Sun (a growing sphere of darkness bursts into a ring of black flame) and Death March (black lanes strike one after another across the arena).
- **Copy rebuilt:** the copied boss's sprite flickers over him for a moment, then the black version fires. The banner names the source boss and the move. A copy never repeats straight after the last one, and in Phase III he copies two moves. The copies are rebuilt from the real sprites (dumplings, bullets, bubbles, knives, bats, sauce, ghosts, twigs and pizza).
- **Fixes:**
  - Hunter Chain's shots were the bright red sprite. They are black now.
  - Hunter Chain's stun did nothing. Afterwards he is EXPOSED for 1.6 s and takes 50% more damage (shown on the health bar).
  - Shadow Orbs were cyan. They are black now.
  - Shadow Dash had no warning. The landing spot is marked (his sprite drops into it), then he vanishes, reappears and slashes through a visible arc.
  - Spear Volley's hitbox now matches its lane.
  - Sweep telegraphs are red in this fight instead of yellow.
- **Menace:** he leans toward the nearest player more in each phase, dark motes stream into him, a glitch slice tears across him now and then, the background beats like a heart (faster each phase), and every move is announced by name.
- **Flash:** each new move starts with a flash, a shock ring and sparks, and the Black Sun, Gravity Well and Eclipse Gaze end in bursts and beams.
- **Limit:** he holds his next move while nine or more hazards are on screen, so phase III does not stack up unfairly.
- **Testing note:** these changes were checked headless (every move, every copy, a full 157-second fight, the win path and snapshot serialisation) and by looking at rendered frames. They have not been played by hand, so balance and feel still need a real run-through.

## Version 25 — Hateful Doom overhaul, pause menu, admin panel

- **Hateful Doom cutscene:** Will and Jackson are at their last HP. Mason walks up to Will and strikes him, Will collapses, then Mason strikes Jackson and he collapses too. Will's last words, "your not mason", play from the ground. Mason then turns dark through a red and blue flash and the secret stage fades in.
- **Hateful Doom transition:** a short blackout, a red flash, the dark sprite swap and the switch to the secret music, all in one timed sequence.
- **Projectile fix:** projectiles keep moving during the secret fight. They used to freeze because the secret branch returned before the projectile update.
- **Pause menu (Esc):** opens Resume, Settings, Restart Run, Back to Lobby (in multiplayer, host only, shown in a run), and Title Screen. Esc or Resume closes it. Solo fights pause; multiplayer fights are only overlaid. Settings returns you to the pause menu.
- **Admin panel:** type `coolguy186` on any screen to open it. Options: God mode, infinite abilities, full heal, clear upgrades, give any upgrade to every player, kill the current boss, and start any boss. Esc closes it.
- **Hateful Doom timer:** a large red clock. Under 60 s it pulses faster, under 20 s it glitches and shakes, and it plays a warning tick each second under 30 s.
- **Hateful Doom attacks:** three new attacks: Hunter Chain (six aimed black shots), Night Nova (a dense black burst), and Shadow Orbs (black orbs that circle him, then fly at the players). The Void Pulse is nerfed: slower, smaller, 8 damage, and the second ring only appears in phase II.
- **Timer runs out:** the screen slowly pixelates over 4.5 seconds, then you are sent back to the lobby.
- **Harder Hateful Doom:** faster enrage (1.35x), more and faster projectile volleys, shorter telegraphs, wider sweeps, bigger sweep damage (24), and 30% more damage taken from all sources.

## Version 24 — Terry tweak, achievements rebuilt

- **Terry:** the money gun now deals 2 damage per shot (was 3).
- **Achievements:** the screen is a scrollable list with a progress bar and scrollbar. Scroll with the mouse wheel or drag the list.
- **New achievements (9):** Burger Break (pick up a burger), Power Up (choose an upgrade), Second Wind (get revived), Ouch (a player goes down), Close Call (survive a hit under 10% health), Solo Act (defeat a boss alone), Punching Bag (take 150 damage in one run), Heavy Hitter (deal 3000 damage in one run), Loop Champion (defeat a boss on a second loop).


## Version 23 — Secret boss 8: Hateful Doom

- **How to unlock:** leave Mason for last. When the second of Will and Jackson falls while Mason is still alive, the secret cutscene plays: Mason finishes them off, Will says "your not mason", and Mason transforms.
- **Hateful Doom** has 9999 HP. The fight lasts exactly as long as `Hateful_Doom_secret_boss_8.mp3` (157 s). If the song ends first, you lose instantly, with a short cutscene.
- His sprite alternates between `Mason Dark 1 (secret boss 8).png` and `Mason Dark 2 (secret boss 8).png` every 0.22 s.
- **Pitch-black attacks:** Black Fire Rain (marked spots burst into rings of black flame), Spear Volley (black spears fall through telegraphed lanes), Eclipse Spiral, Void Pulse (rings of darkness), Shadow Dash (he vanishes, reappears beside you and slashes), Umbral Sweep (a black beam), and **Copy**, which fires a random attack from another boss rebuilt in black, with a banner naming the source.
- **Stage:** a darker, greyer alley with red and blue accents. The gradient, bars and ribbon react to the music's spectrum.
- **Phases:** at 66% and 33% health he attacks faster, fires bigger volleys and wider sweeps, and a banner announces each phase.
- **Achievement:** Hateful Doom (defeat him before the song ends). Added a credit line for the track.
- **Balance note:** 9999 HP in 157 s needs about 64 effective damage per second. Tune this in `SEC_TIME` and the HP in `secTransform` if it is too hard.
- **Not yet tested:** multiplayer with a second client, and the cutscene visuals (checked through the state machine and the fight screenshots, not by watching the cutscene frames).


## Version 22 — Boss 7 remake: new stage, all-new attacks

- **New stage** for boss 7: a midnight food alley with a checker floor, neon frames, spotlights and rising steam.
- **Will** (aura): **Spirit Chase** (ghosts that home in on you), **Aura Orbit** (orbs circle him, then fire at you), **Zig-Zag Bugs** (bugs that wiggle as they fly), **Chakra Pulse** (rings expand out, so stay between them).
- **Jackson** (gunner): **Reload Barrage** (six shots, then he reloads for 1.6 s and takes 50% more damage, shown as RELOADING), **Twig Sweep** (a telegraphed beam that swings across the arena), **Pinball Rounds** (bullets that bounce four times), **Ruler Grid** (telegraphed lanes with one safe lane).
- **Mason** (food): **Pizza Boomerang** (slices fly out and swing back to him), **Burger Drop** (burgers land and leave slowing sauce), **Sausage Roll** (he rolls at you and leaves a greasy trail, and can't act while rolling), **Hot Dog Split** (hot dogs burst into pieces when they run out of range).
- The four map attacks from v21 are unchanged.

## Version 21 — More Boss 7 attacks and map hazards

- **Will** has two new attacks: **Ghost Wave** (a ring of ghosts that curl away) and **Bug Swarm** (bugs that bounce around the arena).
- **Jackson** has two new attacks: **Twig Volley** (spinning twigs) and **Ruler Snipe** (a telegraphed line).
- **Mason's** attacks are all food, as of v20.
- **Map attacks** happen on their own timer during the boss 7 fight, separate from the bosses: **Food Rain** (falling food with landing marks), **Bug Horde** (bugs sweep across), **Ruler Slam** (a full-width line with a safe gap) and **Sauce Flood** (slowing sauce puddles). They come more often as the bosses lose health.
- New sprite files in the root: `Ghost (boss 7).png`, `Twig (boss 7).png`, `Bug (boss 7).png`, `Ruler (boss 7).png`.

## Version 20 — Boss 7: The Hover Trio

- **Boss 7 is three bosses fighting at once:** Will (3,800 HP), Jackson (4,400 HP) and Mason (5,000 HP). Each has its own health bar, and the fight ends when all three are down. HP scales with difficulty and party size like the other bosses.
- **Intro cutscene** (plays with the *Suffocate In Dust II* track, which replaces the normal boss intro):
  - 0–16 s: a black screen with a clock in the middle that ticks once a second.
  - 16 s: Will walks in and hovers, giving off aura sparks, for 9 s.
  - After that, Jackson walks in from the left and Mason from the right.
  - Will: "we found them boys". Jackson: "damn son". These lines cannot be skipped, not even with the skip setting.
  - The screen flashes and the fight starts.
- **Attacks** (boss 7 has 13 in total, four more than before). Will: aura rings, aimed sparks and slams. Jackson: gunfire, ricochet shots and pinpoint blasts. Mason: an all-food set (flying snacks, a dumpling ring, a chopstick line, sauce splats, bouncing burgers, falling eggs and spinning pizzas). Phases follow the combined HP of the three.
- Timings are in the `T7` constant in the script (`clock`, `walk`, `hover`, `pair`), and attacks are in `TRI_FIRE`.
- New files that must sit in the root with `index.html`: `Will (boss 7).png`, `Jackson (boss 7).png`, `Mason (boss 7).png`, `Suffocate_In_Dust_II_boss_7.mp3`.
- Beating boss 7 unlocks the **Triple Threat** achievement. Its victory dialogue and music credit were added too.

## Version 19 — Terry the Hustler, Jay tuning, upgrade balance

- **Iron Will** is now +20 max HP and -15% speed (was +60 HP, -10% speed).
- **Second Chance** revives at 25% HP with 1 s of invulnerability (was 50% HP, 2 s).

- **Character select** is now a two-column grid that grows with the roster. Cards shrink to a compact layout once there are more than four characters, and the player list no longer overlaps the cards.
- **Upgrades for Terry:** Double Tap, Piercing Rounds and Explosive Rounds all work on his money gun and coins. Cooldown Crunch and Snack Time apply to all his abilities.
- **Terry** is a new playable character (support-damage hybrid, class **Hustler**): **110 HP**, speed 240. Pick him in the lobby (four cards now: Coolguy15, Zach, Jay, Terry).
- **Money gun (left click):** rapid-fire cash. A bill fires every **0.07 s** for **3** damage each. Upgrades that add multishot fan the bills out.
- **Q — Lucky Coin (9 s cooldown):** flips a fan of **five** spinning coins. Each coin deals **9** damage and bounces off the walls twice.
- **E — Briefcase Bomb (12 s cooldown):** throws a briefcase that flies for **4 s**. It deals **20** damage each time it hits the boss (the boss can be hit again every 0.45 s while the case is over it). Every time it bounces off an edge it sprays money in all directions. At 4 s it explodes into a ring of cash for **12** damage per bill. The case glows green in its last second.
- **R — Cash Shield (10 s cooldown):** a 3 s green shield. Boss projectiles that touch Terry are blocked and fired back at the boss as cash bills. Shield blocks projectiles only, not lasers, sweeps or Black Flash.
- Terry's sprites (idle 1/2, walk 1/2, money gun, money bill, coin, briefcase) are used as supplied. Terry has his own lines in the intro, phase, outro and victory dialogue.

### Jay changes

- **Food damage** is now **6–9** for every snack projectile: flicked snacks, Food Barrage snacks that hit the boss.
- **Pan melee** (close-range swing) now does **13** damage per hit. The Pan Boomerang still does 20 per hit.
- **80 HP** (was 90).
- **Upgrades:** Double Tap throws an extra snack per flick, and Piercing Rounds adds 25% snack damage per stack.
- **Basic attack is slightly slower:** 0.32 s between attacks (was 0.25 s).
- **Watermelon snack:** each snack thrown (flick or barrage) has a **0.5%** chance to be the watermelon, drawn bigger. Set `MELON_CHANCE` in the script to change this.
- **Walk and idle animations fixed.** The walk used to alternate between the walk sprite and an idle frame, so it barely moved. There are now two walk frames with stepping legs, and the idle alternates between two frames with a breathing stretch.

## Version 18 — Jay, the support cook

- **Jay** is a new playable character (support): **90 HP**, speed 245. Pick him in the lobby card row (three cards now: Coolguy15, Zach, Jay).
- **Pan attack (left click):** up close, Jay swings his frying pan in a wide arc (10–20 damage per hit, with a swing trail and impact sparks). Further away, he flicks a random snack out of the pan at your aim (10–20 damage). **0.25 s** between attacks. In multiplayer, a snack that hits a teammate heals them for **2–4%** of their max HP.
- **Q — Food Barrage (20 s cooldown):** Jay winds up for **0.75 s** (moving at reduced speed), then flings **11 snacks** (orange, sausage, pizza, egg) that arc onto random spots on the map. A snack that hits the boss deals **10–20** damage. A snack lying on the ground heals any player who touches it for **3–5%** of their max HP, and it fades after 12 s.
- **E — Pan Boomerang (10 s cooldown):** the pan flies out at the boss and loops, hitting it **4 times over 1.5 s** for **20** damage each, then glides back to Jay. Jay can't attack while the pan is out. The pan also knocks away boss projectiles it passes through.
- **R — Box Hide (7 s cooldown):** Jay climbs into a cardboard box for **3 s**. He turns semi-transparent, and boss attacks (projectiles, sweeps, lasers, Black Flash, sauce puddles) pass straight through him. He can still move and attack while hidden.
- Only three Jay frames (idle 1, idle 2, walk) were supplied, so the walk cycle alternates between them with the usual bob and squash. Five snack sprites are used for the food pieces.
- New sound cues for the swing, pan hits, the snack toss and landing, the boomerang, the box, and the heal.
- Jay has his own lines in the intro, phase, outro and victory dialogue (solo, mixed with the other characters, and in parties).
- The lobby's character cards and player panel were resized to fit three characters.

## Version 17 — bigger bat, sauce puddles, more attacks

- **Fella's bat** is about 70% bigger. Bat Sweep now lunges Fella toward you through the strike, leaves a crimson crescent that sweeps the arc, shows bat afterimages, and shakes the screen on contact.
- **Sauce puddles** are 60% larger on screen and in collision. Standing in one deals **1 damage every 0.15 seconds** (it applies to any puddle, whoever made it) and still slows you.
- **Evil Zach** has three new attacks: **Knife Rain** (knives drop onto telegraphed spots near you), **Knife Spiral** (an expanding spiral of knives), and **Shadow Slash** (blinks beside you and slashes through). Knife Rain appears from phase 1, Knife Spiral from phase 2, and Shadow Slash from phase 3.
- **Fella** has three new attacks: **Foul Ball** (a ball that ricochets off the walls up to four times), **Sauce Fastball** (a telegraphed line and a fast sauce bullet), and **Vertical Pitch** (two top-down pitch lanes). Foul Ball appears from phase 1, Sauce Fastball from phase 2, and Vertical Pitch from phase 3.

## Version 16 — hitboxes, Evil Zach ultimate, Black Flash aftershock, and a new Fella

- **Boss attack hitboxes** are about 12% smaller than the shapes drawn for them: projectiles, melee sectors, area hazards, and the Black Flash and charge bodies. Boss and player bodies are unchanged. Press **H** to compare the new shapes.
- **Evil Zach ultimate:** the laser rift is about 20% taller (it now spans y 140–400) and its danger band follows the visible rift. The *Nande* track plays for **17 seconds**: full volume until 14 s, a 3-second fade, silent at 17 s. The laser now lasts the same 17 seconds, so the music and the beam end together.
- **Black Flash aftershock:** after the cutscene, a black cut stays across the arena with a thin red afterglow, pixel shards drift out from the contact point, and a white shock ring fades. Multiplayer snapshots carry it.
- **Finisher (lethal FINAL CUT) reworked:** the arena dims to near-black, a crimson diagonal cut widens across the screen, Evil Zach strikes in from the right, the FINAL CUT title slams in, and the screen cuts to black before the aftershock.
- **Fella (boss 6) remade** with a new attack set and three phases:
  - *Warm-Up:* Bat Sweep (two-hit arc, the second sweep leaves a sticky sauce puddle), Sauce Bunt (three bottles that bounce off the walls twice), Slide Rush (slides across the field, leaving a slow trail), Bullpen Pitch (telegraphed pitch lanes).
  - *Bullpen:* adds Minion Relay (staggered minion sprint) and Sauce Rain (six puddles land left to right, each with a splash).
  - *Walk-Off:* adds Walk-Off Slam (landing with three shockwave rings) and Lob Homer (telegraphed landing circle, then a sauce burst). Final phase moves faster.
  - The HUD shows the phase and Fella's HP. Fella's dialogue was rewritten for the new attacks.

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


## Version 14 updates
- Rebuilt dialogue composition for one, two, three, and four players. Dialogues react to the selected Coolguy15/Zach roster, and several sequences include boss-to-boss banter and continuity cameos.
- Evil Zach Black Flash now deals a flat 44 damage, has a distinct lethal FINISHER cutscene, and includes new impact, crack, boom, and finisher sound cues.
- Evil Zach's ultimate now fills the central band of the arena, leaving upper and lower escape corridors; the center-right safe pocket has been removed.
- Reworked Fella into The Grand Slam Menace with a stadium arena, ketchup-pitch slow shots, Grand Slam multi-lane bat projectiles, and a Home Run finisher-style swing, with phase-specific visuals and higher health.


## v15 update
- Tightened shared player and attack collision envelopes slightly, including the Black Flash dash and Fella's bat attacks.
- Rebuilt Evil Zach's ultimate visuals around a broad, telegraphed central rift with top/bottom escape lanes; the collision field follows the visible danger band.
- Rebuilt Black Flash's cutscene into a manga-panel impact sequence, added more timed impact sounds/effects, and kept the lethal FINAL CUT finisher.
- Reworked Fella into a three-inning boss with curving ketchup curveballs, Dugout Ambush lane volleys, a Walk-Off attack, faster final-phase movement, and new inning dialogue.
