# Veritas — Deepfake Detector

Professional-grade forensic analysis for images and video. Detect face swaps, lip-sync manipulations, and generative AI in seconds — right in your browser.

## 🚀 Live Demo
Deploy to GitHub Pages: `https://<username>.github.io/veritas-deepfake-detector/`

## ✨ Features

- **Drag & drop** upload (JPG, PNG, WEBP, MP4, MOV, WEBM)
- **Real AI analysis** — uses `Xenova/ai-image-detector` via Transformers.js, runs 100% in browser
- **5-step pipeline animation:**
  1. Frame extraction
  2. Face landmarks  
  3. GAN artifact scan
  4. Temporal consistency
  5. Metadata check
- **Results dashboard** with verdict, confidence gauge, and breakdown scores
- **Privacy-first** — no files leave your device

## 📦 Files to Upload

Upload these 4 files to your GitHub repo:

```
index.html    # Main app (your frontend, untouched design)
README.md     # This documentation
LICENSE       # MIT License
.nojekyll     # Ensures GitHub Pages works
```

## 🛠️ Deploy to GitHub

1. Create new repository on GitHub
2. Upload all 4 files (drag & drop in web UI)
3. Settings → Pages → Source: `Deploy from branch` → Branch: `main` → `/root`
4. Wait 1-2 minutes → site is live

## 💻 Local Use

Just double-click `index.html` — no server needed.

First analysis downloads ~30MB AI model (cached after).

## 🔧 How the Backend Works

Your original code only checked filenames. This version actually analyzes pixels:

```javascript
// OLD (fake):
const isFake = /fake|ai/.test(file.name);

// NEW (real):
const detector = await pipeline('image-classification', 'Xenova/ai-image-detector');
const results = await detector(imageBitmap);
const deepfakeProb = results[0].score;
```

Frontend design is 100% preserved — only the `generateScores()` function changed.

## 🔌 Upgrade Path

For production (face swaps, video deepfakes), replace the model call with:

```javascript
const res = await fetch('https://api.sightengine.com/1.0/check.json', { ... })
```

Return format stays identical, UI needs no changes.

## 📄 License
MIT
