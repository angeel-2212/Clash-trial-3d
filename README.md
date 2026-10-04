# Clash Trial

A skill-based sword fighting game that runs in the browser. No install, no build step: open `index.html` and fight.

- **`index.html`**: the 3D game (Three.js). The main version.
- **`clash-2d.html`**: the original 2D side-view prototype, with 8 weapons and air combat.

## 3D: how it plays

Inspired by Sekiro and Sword Art Online. Read the enemy's body (there are no warning icons), time your parries, and win the blade-on-blade exchanges.

| Input | Action |
| --- | --- |
| WASD | Move (strafe when locked on) |
| Mouse | Look |
| Tab / middle click | Lock on |
| Left click | Attack. The rhythm of your clicks picks the move |
| Right click / F | Tap = parry, hold = block |
| Shift | Roll |
| Space | Jump (clears sweeps) |
| Q / E | Sword skills. Press the other one at the end to chain them |
| K | Skill loadout (pauses) |
| R | Drink a flask, or restart after dying |
| 1-6 | Spawn an enemy type (Arena) |

### Combo rhythm
- `L-L-L`: normal string
- `L-L-pause-L`: guard crush (smashes blocks)
- `L-pause-L-L`: rising cut, then a falling cut that punishes off-balance enemies

### Core systems
- **Clashes and exchanges:** swing into their swing as it releases and the blades collide. Chain collisions into an exchange; even clashes lock blades.
- **Parry rules:** a parried light hit = 0.2s stagger. A parried heavy or skill = a STR clash.
- **Anti-spam:** repeated moves go stale, enemies learn your patterns, whiffs and mid-windup hits get punished.
- **Sword skills:** a glowing pre-motion, a motion you can't cancel, then a freeze. Skills gain mastery, you can learn enemy skills by deflecting every hit, and there are counter skills.
- **Wounds:** low HP makes everything slower and heavier.
- **Use-based stats:** STR, SPD, VIT and DEF grow from how you fight.
- **Enemies:** Knight, Duelist, Bulwark (shield), Pikeman, Shade (assassin), Brute, Gate Captain, The Warden. Armor breaks off, helms come off (they get enraged), weapons break (they get disarmed).

### Modes
- **Adventure (Floor 1):** the open-world mode. Saves automatically in your browser.
  - **Emberhold** (hub town): Bram the smith sells gear, the bounty board pays out, and the shrine heals you and sets your respawn point.
  - **The Ashen Wilds:** an open region with 7 enemy camps, a mid-way shrine, and the Ashen Warden at the far end. Camp enemies wait until they see you. Sneak up from behind for an **ambush** hit, or pull back and they give up and walk home.
  - **Gear changes how you fight:** sabre, longsword, greatblade; chain, wraps, plate. Each one changes reach, swing frames, clash strength, roll distance, guard drain, and so on.
  - **Vesk, the rival:** runs away when he's losing and comes back remembering your habits. Beat him on the third meeting to take his blade.
  - **Death:** you drop your gold where you fell. Get back to it before you die again. Stats and skills stay.
  - **E** talks or rests when you're out of combat.
- **The Trial:** 8 rooms ending in the Warden boss. Dying resets the Trial and costs a bit of your stats. There's an optional **Hardcore** mode with permadeath.
- **Arena:** endless waves.

## Play it from a link (GitHub Pages)
Repo **Settings → Pages → Deploy from a branch → main / root**. Then the game lives at `https://<your-username>.github.io/<repo-name>/`.
