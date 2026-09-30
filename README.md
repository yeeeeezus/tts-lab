# tts-lab

**A studio for the speech synthesis already inside your browser.**

Live: **https://yeeeeezus.github.io/tts-lab/**

## What it does

- **Voice picker** over every `speechSynthesis` voice your browser/OS exposes, with local/remote and default flags shown.
- **Rate, pitch, volume** sliders with live values — the three real parameters of the Web Speech API.
- **Live word highlighting** driven by `onboundary` events, so you can see pacing, not just hear it.
- **Copyable recipe** — the exact JSON settings, or a two-line JS snippet to reproduce the voice anywhere.
- Estimates duration from word count and rate; graceful state when no voices are available.

## Why

Hosted text-to-speech is metered per character, and the interesting new open voice models need infrastructure. The browser's built-in engine — boring, free, offline, private — never went away. What it lacks is a tuning bench: finding the exact rate/pitch/voice combination inside a `<select>` and three sliders scattered across a settings page is miserable. This is that bench, in one static file with zero dependencies.

## Honest limits

- Voice quality is whatever your OS/browser provides (Chrome/Edge on desktop are best; minimal Linux installs may expose **zero voices** — the page says so instead of pretending).
- The Web Speech API **cannot export audio files**. Record with your OS if you need a file.
- Voices load asynchronously in Chrome; the page polls and refreshes the list.

## Development

Nothing to build — open `index.html`, or:

```console
$ python3 -m http.server 8000
```
