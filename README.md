# Doom.like

A retro first-person shooter in the spirit of classic Doom, packed into a single `index.html` file. Everything is generated in code: the textures and sprites are procedural, the weapons in your hands are small 3D models rendered in software, every sound effect is synthesized live with WebAudio, and the heavy-metal soundtrack is played by a virtual band. There are no image or audio files and nothing to install.

The story: in the early 2000s, a programmer receives a strange ICQ attachment and ends up pulled inside the game on his own screen. You fight through three hand-built levels, from Hell to Heaven, to get him back out.

## How to run

1. Download or clone this folder.
2. Open `index.html` in a modern desktop browser (Chrome, Edge, Firefox or Safari). Double-clicking the file works; no server is required.
3. Click inside the game to capture the mouse, then pick **NEW GAME** and a difficulty.

A keyboard and mouse are required. If the framerate drops, lower the resolution under **ESC → Settings**.

## Controls

| Input | Action |
| --- | --- |
| W / A / S / D | Move and strafe |
| Mouse | Aim (click the game to capture the pointer) |
| Left click / Space | Shoot (hold to keep firing) |
| E / Right click | Use: open doors, search cracked walls for secrets |
| 1 – 8 | Select weapon (1 toggles Fist and Chainsaw) |
| Q / Mouse wheel | Cycle weapons |
| M / Tab | Automap |
| Esc | Pause menu (also skips cutscenes) |
| ↑ ↓ + Enter | Navigate menus; ← → adjusts sliders in Settings |

Colored doors need the key of the matching color. Cracked walls often hide secrets, so press **E** on them.

## Features

### Levels
- **Level 1: Hell's Gate.** Find the red skull key. Lava floors burn. Boss: the **Cyber-Demon**, which has three shields (blue, yellow, red) to break before it can be finished off.
- **Level 2: Inside the Machine.** Find the blue and yellow keycards. Coolant floors burn. Boss: the **Spider Mind**, which also has three shields. Sidestep its charge, then hit it hard while it is stunned (double damage).
- **Level 3: Emerald Heaven — The Throne of Light.** Find the red and yellow keys among marble halls, hedges, gold mosaics and stained glass under an open sky. Liquid light floors burn. Boss: the **Archangel Seraphine**, a flying boss with three shields. Dodge her dive and the pillars of light she calls down.
- An illustrated intro story, interludes between the levels and an ending cutscene.

### Weapons
Fist, Chainsaw, SMG, Shotgun, Rocket Launcher, Plasma Rifle, the Devastator (40 energy cells per shot), the Flamethrower (sets enemies on fire) and the BFG (60 cells per shot). Ammo types are bullets, shells, rockets, cells and fuel. Shields block normal hits: flank them, or use explosives, fire or the BFG.

### Enemies
Imps, demons, phantoms, gunners, flying skulls, bloats, knights, drones, turrets and explosive barrels, plus cherubs and shielded paladins in Heaven, and the three bosses. Gunfire wakes monsters that can hear it, and sound carries through open space and open doors.

### Pickups
Health bonus, stimpack, medikit, soul orb (+100 health, up to 200), armor bonus, green armor (absorbs 1/3 of damage) and mega armor (absorbs 1/2). Fuel cans (+25) and fuel tanks (+80) feed the Flamethrower. Kills, items and secrets are tracked for each level.

### Difficulty
| Level | What changes |
| --- | --- |
| Super Easy | Half the demons, and slow. You take half damage. Double ammo. |
| Easy | Fewer, slower demons. You take less damage. Extra ammo. |
| Medium | The game as designed. |
| Hard | More demons, faster and quicker to shoot. The extra demons drop ammo. Tougher bosses. |
| Nightmare | 2.5× the demons, very fast. The extra demons drop ammo. Bosses are nearly twice as tough. |

The map layout is the same on every difficulty. Demons are removed or added in place, and the layout of the fight is deterministic, so restarting a level gives the same enemies in the same places.

### Presentation
- A textured raycasting renderer that draws straight into a pixel buffer, with dynamic lighting, torches, ceiling lights and both indoor and open-sky areas.
- Software-rendered 3D weapon viewmodels with lighting, outlines and ejected casings.
- Decorative props such as braziers, urns and gas tanks, plus ambient particles.
- Pixel-art status bar showing ammo, health, weapons, armor, keys and a reactive face.
- An automap that shows only the places you have seen.
- **Attract mode:** behind the title menu, a bot plays the real game live. It never touches your save.
- A fixed 60 Hz simulation, so the game runs at the same speed on 60, 120 and 144 Hz screens.

### Audio
- Synthesized sound effects with no audio files.
- A procedural metal soundtrack, with major-key power metal and a choir in Heaven and an anthem for the Archangel: modelled guitars and bass through simulated tube amps and speaker cabinets, a rendered drum kit, lead guitar, reverb, delay and a mix compressor.

### Languages
English, Русский, Español and 简体中文. The language is detected from your browser and can be changed under Settings.

### Saving
Progress checkpoints, your settings (language, resolution, mouse sensitivity, SFX and music volume) and your best clear time for each difficulty are stored in your browser's `localStorage`. Use **CONTINUE** on the title screen to resume.

## Settings
- **Resolution:** Low, Medium, High or Ultra. Higher looks sharper; lower runs more smoothly.
- **Mouse sensitivity**, **Sound FX** and **Music** volume sliders.
- **Language.**

## Project layout
```
index.html   the entire game: HTML, CSS and JavaScript in one file
README.md    this file
```

The level maps carry a note that they were generated from `design/build_levels.py`. That script is not part of this folder.
