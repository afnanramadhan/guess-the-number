# Guess the Number

A simple, responsive browser game built with plain HTML, CSS, and JavaScript. No dependencies, build step, server, or external requests.

## Play locally

Clone or download this repository, then open `index.html` in your browser.

```sh
git clone https://github.com/afnanramadhan/guess-the-number.git
cd guess-the-number
```

## Rules

- A new game generates a random integer between 1 and 100, inclusive.
- Enter a guess and click **Make a guess**, or press Enter.
- The game tells you **Too high!** or **Too low!**.
- Each valid guess counts as an attempt. Invalid input does not count.
- A correct guess displays the number and total attempts.
- Click **Start a new game** to reset and generate a new number.

## Input validation

Blank input, letters, decimals, negative numbers, exponent notation, and numbers outside 1..100 are rejected with an accessible error message. Surrounding whitespace is trimmed.

## Code notes

All source code is in `index.html`, including comments explaining random-number generation and the event-driven game loop. Each form submission is one loop iteration; this avoids a blocking `while` loop. The game stops accepting guesses after a win until restarted.

The interface supports keyboard input, screen-reader status announcements, mobile screens, and reduced-motion preferences. Guess history is kept only for the current game.

## Hosting

This repository contains a static website, but creating the repository does not automatically deploy it. To publish a hosted site, use GitHub Pages (if available for your account and repository visibility) with the `main` branch and root folder, or another static host.

## Test checklist

- Submit blank input, `abc`, `0`, `101`, `1.5`, `1e1`, and `-1`: show an error; attempts remain unchanged.
- Submit valid guesses: count every valid submission and show directional feedback.
- Guess correctly: show the total attempts and disable the guess form.
- Start a new game: clear guesses, reset attempts, and enable the form.
- Confirm the random-number formula includes both 1 and 100.
