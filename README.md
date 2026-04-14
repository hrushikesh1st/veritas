<img width="1470" height="804" alt="Screenshot 2026-04-14 at 12 36 00 PM" src="https://github.com/user-attachments/assets/b570c36e-e421-49cb-83fe-dde7d2cdb385" />
# Veritas — Deepfake Detector

Professional-grade forensic analysis for images and video. Detect face swaps, lip-sync manipulations, and generative AI in seconds — right in your browser.

## Live Demo
`https://hrushikesh1st.github.io/veritas-deepfake-detector/`

## Features
- Drag & drop upload (JPG, PNG, WEBP, MP4, MOV, WEBM)
- Real AI analysis using Transformers.js — runs 100% in browser, no server
- 5-step pipeline: Frame extraction → Face landmarks → GAN artifact scan → Temporal consistency → Metadata check
- Results dashboard with verdict, confidence gauge, and forensic breakdown
- Privacy-first: files never leave your device

## Quick Start

1. Download `index.html`
2. Double-click to open in browser
3. Upload an image or video
4. First run downloads AI model (~30MB, cached after)

## Deploy to GitHub Pages

1. Create new repository named `veritas-deepfake-detector`
2. Upload `index.html` and this `README.md`
3. Settings → Pages → Source: `main` branch → `/root`
4. Site goes live at https://hrushikesh1st.github.io/veritas-deepfake-detector/

## How It Works

The backend analyzes actual pixels, not filenames:

```javascript
const detector = await pipeline('image-classification', 'Xenova/ai-image-detector');
const results = await detector(image);
Previous demo versions only checked filenames. This version uses a real on-device model.

Files
index.html — Complete app (HTML, CSS, JS in one file)
README.md — This file
License
MIT — free for personal and commercial use

Disclaimer
This tool provides probabilistic analysis and should not be used as sole evidence for legal or journalistic decisions without expert review.

---

**Download ready-made file:** [README.md](container:///mnt/data/README-hrushikesh1st.md)

Just upload this with your `index.html` to the repo `veritas-deepfake-detector` and your live URL will be exactly as shown above.
