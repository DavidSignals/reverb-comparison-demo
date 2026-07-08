# Reverb Comparison Demo

Interactive web demo created to validate and visualize the results presented in the accompanying reverb research article. The project compares four versions of the same source material — Dry, Plugin A, Plugin B, and Neoverb — through browser-based listening tests, real-time spectral monitoring, average spectral comparison, and compact objective metrics [file:132][file:37].

[cite:134]

## Overview

This repository contains a static web application designed for GitHub Pages deployment. Its goal is to make the practical effect of the reverb models easier to inspect by combining direct listening with visual analysis in a single browser-based interface [file:132][file:37].

The demo focuses on nine signal categories: impulse, bell, snare, vocal, vocal woman, sine, pink noise, white noise, and acoustic guitar [file:133]. Each category includes four rendered versions so that the behavior of the different reverbs can be assessed under the same source conditions [file:133][file:132].

## Features

- Signal selector for the full nine-signal test set [file:133].
- Four integrated audio players for Dry, Plugin A, Plugin B, and Neoverb [file:133].
- Real-time spectral monitoring using the browser audio engine and FFT analysis [file:132].
- In-browser average spectral comparison across the four versions of the selected signal [file:132].
- Compact metrics table with peak, RMS, and spectral centroid values computed directly in the web app [file:132].
- Static deployment workflow suitable for GitHub Pages, with all media stored locally in the repository [memory:123].

## Repository Structure

```text
reverb-comparison-demo/
├── reverb-demo.html
└── assets/
    ├── impulse_dry.wav
    ├── impulse_A.wav
    ├── impulse_B.wav
    ├── impulse_neoverb.mp3
    ├── bell_dry.wav
    ├── bell_A.wav
    ├── bell_B.wav
    ├── bell_neoverb.mp3
    ├── snare_dry.wav
    ├── snare_A.wav
    ├── snare_B.wav
    ├── snare_neoverb.mp3
    ├── vocal_dry.wav
    ├── vocal_A.wav
    ├── vocal_B.wav
    ├── vocal_neoverb.mp3
    ├── vocal_woman_dry.wav
    ├── vocal_woman_A.wav
    ├── vocal_woman_B.wav
    ├── vocal_woman_neoverb.mp3
    ├── sine_dry.wav
    ├── sine_A.wav
    ├── sine_B.wav
    ├── sine_neoverb.mp3
    ├── pinknoise_dry.wav
    ├── pinknoise_A.wav
    ├── pinknoise_B.wav
    ├── pinknoise_neoverb.mp3
    ├── whitenoise_dry.wav
    ├── whitenoise_A.wav
    ├── whitenoise_B.wav
    ├── whitenoise_neoverb.mp3
    ├── acoustic_guitar_dry.wav
    ├── acoustic_guitar_A.wav
    ├── acoustic_guitar_B.wav
    └── acoustic_guitar_neoverb.mp3
```

The application expects all audio files to be stored inside the `assets/` folder at the repository root, using the naming pattern `signal_condition.ext` [conversation_history:1]. WAV is used for Dry, Plugin A, and Plugin B, while MP3 is accepted for Neoverb in the current dataset [file:133].

## Naming Convention

Use the following pattern consistently for every signal group [conversation_history:1]:

- `signal_dry.wav`
- `signal_A.wav`
- `signal_B.wav`
- `signal_neoverb.mp3`

Recommended base signal names:

- `impulse`
- `bell`
- `snare`
- `vocal`
- `vocal_woman`
- `sine`
- `pinknoise`
- `whitenoise`
- `acoustic_guitar`

## Running the Demo

This is a static project. No backend and no Python runtime are required for deployment; all analysis shown in the demo runs directly in the browser [file:132].

### Local preview

Open `reverb-demo.html` in a browser after placing the audio files in `assets/`. If the browser blocks direct local decoding for some files, preview through a lightweight local server.

Example with Python:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/reverb-demo.html
```

### GitHub Pages deployment

1. Create a repository, for example `reverb-comparison-demo` [memory:123].
2. Upload `reverb-demo.html` to the repository root [conversation_history:1].
3. Upload the full `assets/` folder with all audio files [conversation_history:1].
4. In GitHub, enable **Pages** from the repository settings and publish from the main branch root [memory:123].

## Purpose in the Research Context

The repository is intended as a companion demo for the article, allowing listeners to inspect whether the practical behavior of the proposed and compared reverbs aligns with the article’s claims about spectral behavior, density, and audible differences under controlled source material [file:132][file:37].

This format is useful because it combines subjective listening with direct visual evidence, making it easier to communicate the results of the study to supervisors, reviewers, and technical audiences [file:37][file:102].

## Technical Notes

- The web app performs real-time spectral monitoring with browser audio analysis nodes [file:132].
- The comparison plot estimates compact average spectra for Dry, A, B, and Neoverb directly in JavaScript [file:132].
- The metrics table provides lightweight numerical descriptors rather than a full offline research pipeline, which keeps the demo self-contained for web deployment [file:132].
- File naming must match exactly, including the dot before `.wav` or `.mp3`, otherwise the corresponding player will fail to load [file:133].

## Credits

Research, audio preparation, and comparative framework by David Rábago. The web demo was prepared as a presentation layer for validating the findings discussed in the associated reverb article [file:132][file:37].
