# Robot App — Design Document

A single-page web app that simulates a Logo-like environment where a robot follows a sequence
of visual instructions. After the demo, kids stand up and "become the robot" following the same
instructions physically.


## Architecture

Single file: `robot.html` — vanilla HTML + CSS + JS, zero dependencies, opens in any browser.


## Layout

Two-panel responsive layout:

| Left Panel: "Orders for the Robot" | Right Panel: "Robot's World" |
|---|---|
| Instruction palette (clickable icons) at top | Canvas area with grid background |
| Numbered instruction list below | Cute robot character |
| PLAY / CLEAR buttons at bottom | Colored trail as robot moves |


## Instruction Set

| # | Name | Icon | Color | Action |
|---|---|---|---|---|
| 1 | Move Forward | Up arrow | Green | Move 1 step in facing direction |
| 2 | Move Backward | Down arrow | Red | Move 1 step backward |
| 3 | Turn Left | Curved left arrow | Blue | Rotate 90 degrees left |
| 4 | Turn Right | Curved right arrow | Orange | Rotate 90 degrees right |
| 5 | Run! | Fast-forward | Lime/bright green | Move 4 steps forward (like running) |
| 6 | Sing! | Music note | Purple | Play a short melody, robot wiggles |
| 7 | Clap! | Hands | Yellow | Clap sound + visual effect |
| 8 | Jump! | Kangaroo | Pink | Robot bounces in place |


## Instruction Palette

- Row of big, rounded, colorful buttons at the top of the left panel.
- Each button has a large icon and a short label underneath.
- Clicking a palette button appends that instruction to the program list below.
- Each instruction in the list shows: line number (1, 2, 3...) + colored icon + label.
- Instructions in the list can be removed by clicking an X on each one.


## Execution Behavior

- Big green PLAY button starts execution.
- Instructions execute one at a time, top to bottom.
- Current instruction highlights (glow/pulse) during execution.
- ~1 second per instruction for the action animation.
- ~0.5 second pause between instructions (clear gap so kids see the sequencing).
- After all instructions finish, a small celebration (confetti).
- CLEAR button removes all instructions and resets robot to center.


## Robot Character

- Top-down view with a round robot that has eyes indicating direction, so kids can see which
  way it's "looking."
- Antenna with a colored tip.
- Trail: rainbow cycling colors, drawn as thick rounded lines behind the robot.


## Visual Design

- Background: light, cheerful gradient.
- Fonts: rounded, bold, large (kid-friendly).
- Everything has rounded corners, soft shadows.
- Buttons have hover/click animations (scale up slightly).
- Robot canvas has a subtle grid so movement is visible.
- Bright, saturated colors throughout.


## Sound

- Sing: a short fun melody (Web Audio API — a few notes).
- Clap: white noise burst simulating a clap (Web Audio API synthesized).
- Movement: subtle "boop" for each step.
- Jump: higher-pitched boop.
