# Everything Is Outdated

**A terminal game about the things you keep meaning to update.**

[Play Everything Is Outdated](https://everythingisoutdated.dev/)

You are dropped into a simulated developer machine with a lot of outdated
software. Explore the terminal, discover what's installed, and figure out how
to bring everything up to date. The clock is running.

## The challenge

Find the available package managers and use them to update as much as you can.
A live dashboard tracks what you've discovered and upgraded, what's left, and
your elapsed time.

There is no checklist of answers here: discovery is part of the game.

For another challenge, ask an AI agent with browser-use or computer-use
capabilities to play and see if it can crack the game.

## How it works

The browser displays a simulated terminal alongside the dashboard. Commands are
handled by a server-side simulation, which tracks your game session and sends
the results back to the browser.

The simulated Bash shell and basic Unix utilities are deliberately limited.
Some commands, options, and shell features are unavailable or behave
differently from a real system.

**Your commands do not run on your computer or update its software.**

## Running on Cloudflare

- The browser interface is served using
  [Workers Static Assets](https://developers.cloudflare.com/workers/static-assets/).
  Cloudflare also manages the custom domain and HTTPS certificate.
- A [Cloudflare Worker](https://developers.cloudflare.com/workers/) handles
  session and command requests, runs the simulation, and returns terminal
  output and dashboard updates. The simulation and package catalogue stay on
  the server rather than being included in the browser assets.
- Each game session has its own SQLite-backed
  [Durable Object](https://developers.cloudflare.com/durable-objects/) to
  persist progress. The browser remembers the session ID so a game can be
  resumed; sessions expire after seven days of inactivity.

This repository is a spoiler-free introduction; it does not contain the game
implementation or solutions.
