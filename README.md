# Barrel Bears

*A splashy, fast-moving rescue game inspired by classic arcade fun.*

Barrel Bears is an arcade-style catching game inspired by Atari's Kaboom. Mama Bear moves along the treetops dropping her cubs, and the player moves a barrel to catch them before they hit the forest floor. The game speeds up as you progress, testing your reflexes and precision.

---

## Gameplay

Mama Bear moves back and forth across the top of the screen, dropping bear cubs as she goes. The player controls a wooden barrel at the bottom of the screen, sliding it left and right to catch each falling cub. Catching a cub earns a point and creates a blue water splash. Missing a cub costs a barrel (life) and creates a red splash.

Catch enough cubs to advance to the next level, where Mama Bear moves faster, cubs fall quicker, and they drop more frequently.

## Controls

- **Desktop**: Move the mouse left and right to position the barrel. Click to start. Press R to restart.
- **Mobile**: Slide your finger left and right to move the barrel. Tap to start. Tap to restart after game over.

## Scoring

- Each cub caught = 1 point
- Catch 10+ cubs per level to advance (increases each level)
- You start with 3 barrels (lives)
- Miss a cub and you lose a barrel
- Game ends when all barrels are lost

## Difficulty Progression

Each level increases:
- Mama Bear's movement speed (caps at 9)
- Cub falling speed (caps at 11)
- Cub drop frequency (minimum interval of 18 frames)
- Cubs needed to advance (10 + 2 per level)

---

## The Story

Once upon a time in the Georgia mountain forests, where tall trees sway and waterwheels turn, there lived a busy Bear family. Mama Bear was brave, strong, and very determined. Every morning, she and her fluffy cubs climbed the tallest trees in the forest, searching for sweet, golden honey hidden among the branches.

But today was a special day. The cubs had decided they were ready for their first big swim in the creek. There was just one problem -- there were so many cubs, and they were all eager to get down right now. Mama Bear did what any clever bear would do: she gently tossed her cubs down from the trees toward a big barrel of cool, refreshing water.

That is where you come in. Mama Bear needs your help to safely catch every cub before they tumble onto the forest floor.

---

## Technical Details

### Architecture

Barrel Bears is a single-file HTML5 Canvas game with no external dependencies. All game logic, rendering, audio management, and input handling are contained in one `index.html` file. It runs in any modern browser on desktop or mobile.

### Development Process

The game was developed iteratively through conversational AI-assisted coding using Kiro. The process followed this pattern:

1. **Concept**: Started as a Kaboom clone, then re-themed to Barrel Bears with a mama bear, falling cubs, and a wooden barrel catcher in a forest setting.

2. **Scaffolding**: The initial game structure was generated with a customizable asset system, Canvas rendering loop, and mouse/touch input handling.

3. **Iterative refinement**: Each feature was added and tuned through conversation:
   - Default graphics were drawn for mama bear (with body, head, ears, snout, eyes, and paws), falling cubs (round bears with ears and face), and a wooden barrel (curved body, metal bands, wood grain, dark opening)
   - Forest background with trees, trunks, foliage, ground, and grass tufts
   - Blue water splash on catch, red splash on miss
   - Barrel dimensions increased to 80x50 for a more barrel-shaped appearance
   - Cub size doubled to 40x40 for better visibility
   - Speed and difficulty curves tuned across multiple iterations
   - Mobile touch controls added with pull-to-refresh prevention
   - Splash screen with box art support and click/tap to start
   - Background music with start/stop on game events
   - Game border color matched to forest green theme

4. **Asset integration**: All graphics and sounds are loaded through a centralized `CUSTOM_ASSETS` configuration object. Each asset has a fallback -- if the file is missing, a default drawn graphic or no sound is used.

5. **Deployment**: The game is hosted on GitHub Pages as a static site with assets in an `/assets/` subfolder.

### Key Technical Features

- **Responsive layout**: Canvas scales to fit mobile screens with `100vw` width
- **Touch and mouse input**: Mouse controls on desktop, touch slide on mobile, both coexist
- **Splash screen**: Supports custom box art that fills the game area, with instruction text overlaid
- **Background music**: Loops during gameplay, stops on game over, restarts on new game
- **Particle effects**: Splash particles on catch (blue) and miss (red) with fade-out
- **Customizable assets**: Every visual and audio element can be replaced via the config object

### Asset System

All custom assets are defined in the `CUSTOM_ASSETS` object at the top of the script:

```javascript
const CUSTOM_ASSETS = {
    mamaBearImage: 'assets/bomber.png',
    cubImage: 'assets/bomb.png',
    barrelImage: 'assets/barrel.png',
    backgroundImage: 'assets/background.png',
    boxArtImage: 'assets/box-art.png',
    catchSound: 'assets/catch.mp3',
    missSound: 'assets/miss.mp3',
    levelUpSound: 'assets/levelup.mp3',
    gameOverSound: 'assets/gameover.mp3',
    backgroundMusic: 'assets/music.mp3',
};
```

Set any value to `null` to use the default fallback.

### Image Specs

| Asset | Dimensions | Format | Notes |
|---|---|---|---|
| Mama Bear | 64 x 48 px | PNG w/ transparency | Moves along the top of the screen |
| Cub | 40 x 40 px | PNG w/ transparency | Falling object |
| Barrel | 80 x 50 px | PNG w/ transparency | Player-controlled catcher |
| Background | 640 x 480 px | PNG or JPG | Full canvas background |
| Box Art | 640 x 480 px or similar | PNG or JPG | Splash screen |

### Sound Specs

| Asset | Duration | Format | Notes |
|---|---|---|---|
| Catch | 0.1-0.3 sec | MP3 | Cub safely caught |
| Miss | 0.3-0.5 sec | MP3 | Cub missed |
| Level Up | 0.5-1.0 sec | MP3 | Level advance |
| Game Over | 1.0-2.0 sec | MP3 | All barrels lost |
| Music | 30-120 sec | MP3 | Loops continuously |

### File Structure

```
barrel-bears/
  index.html
  story.html
  README.md
  assets/
    bomber.png
    bomb.png
    barrel.png
    background.png
    box-art.png
    catch.mp3
    miss.mp3
    levelup.mp3
    gameover.mp3
    music.mp3
```

---

## Links

- [Play the Game](https://dosswerks.github.io/barrel-bears/)
- [Story and Instructions](https://dosswerks.github.io/barrel-bears/story.html)
- [Listen to the Full Soundtrack](https://distrokid.com/hyperfollow/andrewdoss1/music-from-karvers-korner-the-legend-of-dukes-gold)
- [AndrewDoss.com](https://andrewdoss.com)

## Credits

Concept, design, art direction, story, and audio: Andrew Doss

Game engine and code: Built with Kiro AI-assisted development

Hosted on GitHub Pages
