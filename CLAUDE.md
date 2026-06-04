# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is the personal website for the music artist **package_emoji**, served via GitHub Pages at `packageemoji.github.io`. It is a hand-written static site: plain HTML with inline CSS, no build step, no JavaScript framework, no package manager, and no dependencies to install. Content is in Japanese (`lang="ja"`).

## Build / Run / Deploy

- **No build.** Edit the `.html` files directly.
- **Preview locally** by opening a file in a browser, or serve the directory: `python3 -m http.server` then visit `http://localhost:8000`.
- **Deploy** by pushing to the `main` branch — GitHub Pages publishes the repository root automatically. There is no CI, test, or lint tooling.

## Structure

Two standalone pages, each fully self-contained with its CSS in a `<style>` block (there are no shared/external stylesheets):

- `index.html` — landing page and the only entry point. Holds Links, Discography, Mixes, Edits, and a 週報 link. White minimalist theme (Helvetica, black on white).
- `notes.html` — 週報 (weekly notes) blog, newest entry first. Same white minimalist theme as `index.html`.
- `images/` — square album artwork (`.jpg`), referenced by the Discography list in `index.html`.

## Conventions and gotchas

- **Discography lives inline in `index.html`.** Releases are listed directly in the `.discography` section of `index.html` (each as a `.release-row` link), not in a separate page.
- **Google Analytics** (`gtag.js`, ID `G-27HQBW4CBT`) is pasted at the top of every page's `<head>`. Keep it when creating new pages.
- **External links** to Bandcamp / SoundCloud / streaming use `target="_blank" rel="noopener"`.
- **週報 entries** in `notes.html` follow the pattern: a `.entry` div containing an `.entry-date` (format `週報YYMMDD`) and an `.entry-body` with one or more `<p>`. Add new entries at the top.
- `index.html` embeds a SoundCloud "edits" playlist via an `<iframe>`.
