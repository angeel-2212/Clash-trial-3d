# Clash Trial

A skill-based sword fighting game that runs in the browser. No install, no build step: open `index.html` and fight.

- **`index.html`**: the 3D game (Three.js). The main version.
- **`clash-2d.html`**: the original 2D side-view prototype, with 8 weapons and air combat.

## 3D: how it plays

Inspired by Sekiro and Sword Art Online. Read the enemy's body (there are no warning icons), time your parries, and win the blade-on-blade exchanges.

| Input | Controller | Action |
| --- | --- | --- |
| WASD | Left stick | Move (strafe when locked on) |
| Mouse | Right stick | Look |
| Tab / middle click | R3 | Lock on |
| Left click | RB | Attack. The rhythm of your clicks picks the move |
| Right click / F | LB | Tap = parry, hold = block |
| Shift | B | Roll |
| Space | A | Jump (clears sweeps) |
| Q / E | RT / LT | Sword skills. Press the other one at the end to chain them |
| C | D-pad down | Switch stance |
| 1-4 | D-pad left/right + up | Belt items: throwing knife, whetstone, iron tonic, swift draught (Adventure) |
| E | Y | Talk / rest (out of combat) |
| R | X | Drink a flask, or respawn after dying |
| K | Start | Loadout (pauses) |
| O | Back | Settings: rebind keys, sensitivity, FOV, volume, graphics quality |
| 1-6 | | Spawn an enemy type (Arena) |

### Combo rhythm (default deck)
- `L-L-L`: normal string
- `L-L-pause-L`: guard crush (smashes blocks)
- `L-pause-L-L`: rising cut, then a falling cut that punishes off-balance enemies

### Core systems
- **Clashes and exchanges:** swing into their swing as it releases and the blades collide. Chain collisions into an exchange; even clashes lock blades.
- **Parry rules:** a parried light hit = 0.2s stagger. A parried heavy or skill = a STR clash.
- **Anti-spam:**
  - Repeated moves go stale.
  - Enemies learn your patterns. Your opener counts for half, since every string starts with it.
  - Clicks wasted mid-swing count as mashing.
  - Whiffs and mid-windup hits get punished.
  - Combo pips above your skills show where you are in the string and what a pause would do next.
- **Sword skills:** a glowing pre-motion, a motion you can't cancel, then a freeze. Skills gain mastery, you can learn enemy skills by deflecting every hit, and there are counter skills.
- **Stances:** same moves, different timing.
  - **Flow:** faster swings and rolls, easier perfect links, lighter hits.
  - **Rooted:** slower and heavier, wins clashes, and light hits don't stagger you mid-swing.
- **Enemy weapons:**
  - **Axe:** heavy swings can't be deflected (roll them), and deflecting a light swing doesn't stagger.
  - **Mace:** shreds your guard when you block it.
- **Wounds:** low HP makes everything slower and heavier.
- **Use-based stats:** STR, SPD, VIT and DEF grow from how you fight.

## Modes

### Adventure
The open-world mode. It saves automatically in your browser.

- **Emberhold**, the hub town:
  - **Bram the smith:** sells gear.
  - **Bounty board:** pays out for kills and challenges.
  - **Shrine:** heals you and sets your respawn point.
  - **Practice ring:** spar against any enemy you've met, or a training dummy that shows combo damage totals. No gold, no stats, no dying.
- **Quests:**
  - **The Missing Scout:** for Captain Hale.
  - **Bram's Masterwork:** for Bram.
  - **Old Debts:** for Mara. It's tied to Vesk.
- **Floor 1, the Ashen Wilds:**
  - 7 enemy camps. Enemies wait until they see you: sneak up for an **ambush**, or pull back and they walk home.
  - Floor boss: the Ashen Warden.
- **Floor 2, the Rime Pass:**
  - **Reavers:** twin blades, with deliberately late hits.
  - **Sentinels:** halberd charges and spins, and their guard recovers fast.
  - Floor boss: the Rimeborn King.
- **Floor 3, Cinderfall:** a burning city.
  - **Cinder Zealots:** maces, and they speed up as they bleed.
  - **Ashbound Executioners:** axes.
  - Floor boss: a pair, **Ash & Ember**. Kill one and the other goes berserk.
- **Rivals:**
  - **Vesk:** remembers your habits.
  - **Gorrun:** resists whatever hurt him most last time.
  - Beat either one on your third meeting to take his gear.
- **Elite camps:** about a quarter of camps come back led by an elite. They pay triple gold and drop a new move or a mantra.
- **Boss rematches:** beaten floor bosses can be called back, stronger each time. Rematches are the only way to get the Phantom, Sunder and Tempest mantras.
- **Gear changes how you fight:** reach, swing frames, clash strength, rolls and guard drain. Unique weapons are dropped by bosses and rivals or forged for quests.
- **Loot:** enemies drop things you walk over to pick up.
  - **Materials:** Iron Scrap, Rimesteel Shards and Cinder Cores. Bram uses them to upgrade your weapons up to +5.
  - **Belt items:** throwing knives (interrupt a light attack mid-windup), whetstones (+20% damage), iron tonics (guard holds longer) and swift draughts (faster movement and rolls).
  - **Flask shards:** three of them add a permanent flask charge, up to 6.
  - **Gold pouches.**
  - **Trinkets:** every enemy type has its own. You get two trinket slots.
- **Death:** you drop your gold where you fell. Get back to it before you die again. Stats and skills stay.

### Your build (press K)
- **Combat deck:** pick which move sits in each part of your string: 3 click slots and 2 pause slots. Moves you can learn: Lunge, Wide Arc, Whirlwind.
- **Mantras:** attach one to a sword skill to change how it works.
  - Echo: one extra hit.
  - Swift: faster windup.
  - Brutal: harder hits.
  - Retreat: hop out of the freeze.
  - Leech: heal on hit.
  - Linked: easier chaining.
  - Breaker: every hit is a guard crush.
  - Phantom, Sunder, Tempest: from rematches only.
- **Talents:** earned by how you fight, not picked.
  - Steady Hand: deflect streaks.
  - Iron Grip: blade lock wins.
  - Ghost Step: perfect dodges.
  - Executioner: deathblows.
  - Predator: ambushes.
  - Last Stand: low-HP kills.

### The Trial
8 rooms ending in the Warden boss. Dying resets the Trial and costs a bit of your stats. There's an optional **Hardcore** mode with permadeath.

### Arena
Endless waves.

## Graphics
Three quality levels in Settings:

- **Low:** no shadows, fastest.
- **Medium:** shadows.
- **High:** shadows plus bloom, with full grass and particle density.

Bloom loads the three.js post-processing scripts from jsDelivr.

## Play it from a link (GitHub Pages)
Repo **Settings → Pages → Deploy from a branch → main / root**. Then the game lives at `https://<your-username>.github.io/<repo-name>/`.
