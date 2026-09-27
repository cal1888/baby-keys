# Rainbow Keys

A keyboard-bashing game for babies and toddlers. Every key makes a bouncy shape, a burst of colour and a sound.

![Rainbow Keys](og.jpg)

- **Letters and numbers** pop up a glossy shape with the letter on it. Where it appears matches where the key sits on the keyboard.
- **Each keyboard row has its own sound**: numbers twinkle, the top row rings like bells, the middle row is a xylophone and the bottom row bloops like bubbles. The notes all come from one pentatonic scale, so random mashing still sounds nice.
- **Space** draws a rainbow and rains confetti. **Enter** launches fireworks.
- **Taps and clicks** make little shapes with blinking faces, so it works on phones and tablets too.
- Goes full screen on the first key press. Holding a key down only plays it once, and the volume is capped.

It's one HTML file with no build step and no dependencies. Open `index.html` in a browser to play.

## Analytics

Uses [PostHog](https://posthog.com) in cookieless mode: no cookies and no personal data. It records that a session started, how long it lasted and how many keys were pressed, never which keys. Analytics stays off while `POSTHOG_KEY` in `index.html` is empty.
