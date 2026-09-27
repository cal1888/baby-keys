# Baby Keys

A cozy keyboard game for babies and toddlers. Every key makes a hand-drawn shape pop up with a sound. Play it at [babykeys.link](https://babykeys.link).

![Baby Keys](og.jpg)

## Levels

Pick a level from the settings button in the top-right corner.

- **Free play (1+)**: every letter and number pops up a glossy shape with that letter on it, placed where the key sits on the keyboard. Each keyboard row has its own sound: numbers twinkle, the top row rings like bells, the middle row is a xylophone and the bottom row bloops like bubbles. The notes all come from one pentatonic scale, so random mashing still sounds nice. Space draws a rainbow and Enter launches fireworks. Taps and clicks make little shapes with blinking faces, so this level works on phones and tablets too.
- **Find the letter (2+)**: a bubble shows a letter to find. With a keyboard, press that key; a little keyboard at the bottom lights up where it is. On phones and tablets, tap the matching one of three big letter tiles. Wrong answers just wobble (and fade the wrong tile).
- **Challenge (4+)**: type your name, then pop as many as you can. One wrong answer and it's game over, with your score, best streak, a rank and a high-score board by name. On phones and tablets you tap big tiles: 3, then 4 after 5 pops, 6 after 10 and 8 after 20.

  Points = 10 × difficulty × speed × streak:
  - **difficulty** is log2 of the number of options, i.e. how unlikely a lucky guess is (3 tiles 1.6, 8 tiles 3, full keyboard 4.7);
  - **speed** drains smoothly from 1.0 to a 0.3 floor over 5 seconds, so a slow correct answer always scores;
  - **streak** adds ×0.1 per correct answer in a row, up to ×2.

It goes full screen on the first key press. Holding a key down only plays it once, and the volume is capped.

It's one HTML file with no build step and no dependencies. Open `index.html` in a browser to play.

## Analytics

Uses [PostHog](https://posthog.com) in cookieless mode: no cookies and no personal data. It records which level was played, how long a session lasted, how many keys were pressed, and Challenge scores. It never records which keys were pressed or any player names. Names and high scores are only saved in the browser on that computer.
