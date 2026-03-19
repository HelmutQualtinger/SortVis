# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file sorting algorithm visualizer (`index.html`) — no build step, no dependencies, pure HTML/CSS/JS.

## Running

Open `index.html` directly in a browser. No server required.

## Architecture

Everything lives in `index.html` as inline `<style>` and `<script>` blocks.

**Core pattern — generator-based stepping:**
Each sorting algorithm is a generator function that `yield`s a step descriptor `{ type: 'compare'|'swap', indices: [...] }` after every atomic operation. A single shared runner calls `.next()` either once (Step button) or repeatedly via `setTimeout` (Run mode). This decouples algorithm logic from animation timing cleanly.

**Key globals:**
- `array` — the live integer array being sorted (mutated in place)
- `colorMap` — precomputed HSL colors indexed by value rank (rebuilt on shuffle/resize)
- `generator` — current algorithm generator instance
- `running` — boolean controlling the run loop
- `delay` — ms between steps, derived from speed slider (exponential scale)

**Rendering:**
Bars are `<div>` elements inside a flex container. `render(compareSet, swapSet)` repaints all bars each step — height via `flex-basis`, color from `colorMap`, glow via `box-shadow` for compare (yellow) and swap (pink) highlights.

**Adding a new algorithm:**
Write a generator function `function* mySort(arr)` that yields `{type, indices}` after each compare/swap and mutates `arr` in place. Add it to the `algorithms` map and the `<select>` element.
