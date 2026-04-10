# 👻 Someone Is Watching

A psychological horror web experience that turns your own webcam into the source of fear.

Built for the DEV April Fools Challenge (#418challenge), this project pranks users by making them feel like they’re being watched… by themselves.

---

## 🎥 Demo

🔗 [https://github.com/sneh1117/someone-is-watching/](https://sneh1117.github.io/someone-is-watching/)

⚠️ Warning: This experience is genuinely creepy.
Best experienced alone, with headphones, in a dark room.

---

## 🧠 Concept

The experience starts innocently:

"This experience requires camera access."

Once granted, users see their live webcam feed… but things slowly begin to feel off.

* A delayed version of their own face appears behind them
* A pale, unnatural figure emerges from the darkness
* Glitching messages warn: "IT'S RIGHT BEHIND YOU"

After 70 seconds of escalating tension, it ends with:

"I saw everything."

---

## ⏱️ Experience Timeline

Phase 1 (0–15s): Awareness builds ("You've been here for 3 seconds...")
Phase 2 (15–30s): Subtle creepy face appears in background
Phase 3 (30–50s): Ghost from past frames manifests
Phase 4 (50–70s): Full horror — glitch effects, high opacity ghost
Phase 5 (70s): Final reveal

---

## ⚙️ Tech Stack

* HTML / CSS / JavaScript (Vanilla)
* Canvas API — Rendering ghost overlays and effects
* getUserMedia API — Webcam access (with permission)
* Web Audio API — Ambient horror soundscape

~900 lines of pure vanilla code. No frameworks. No dependencies.

---

## 🏗️ Architecture

* 3 Canvas Layers:

  1. Webcam feed (background)
  2. Ghost overlay
  3. Procedural creepy face

* Frame Buffer System:

  * Stores recent webcam frames
  * Reuses them to create the "ghost" effect

* Phase-Based Timeline:

  * Triggers effects at specific timestamps

---

## 🧪 How It Works

Frame Capture (Ghost Memory)

function captureGhostFrame() {
const tempCanvas = document.createElement('canvas');
const tempCtx = tempCanvas.getContext('2d');
tempCtx.drawImage(video, 0, 0);
ghostFrames.push(tempCanvas);
}

Ghost Rendering

function startGhostEffect() {
const randomFrame = ghostFrames[Math.floor(Math.random() * ghostFrames.length)];
ghostCtx.globalAlpha = ghostOpacity;
ghostCtx.filter = 'blur(4px) brightness(1.5)';
ghostCtx.drawImage(randomFrame, offsetX, offsetY);
}

Procedural Face

function drawCreepyFace() {
faceCtx.fillStyle = '#ddd';
faceCtx.ellipse(faceX, faceY, faceSize * 0.7, faceSize, 0, 0, Math.PI * 2);

faceCtx.fillStyle = '#000';
faceCtx.ellipse(leftEyeX, eyeY, eyeSize, eyeSize * 1.3, 0, 0, Math.PI * 2);
}

---

## 🎨 Design Choices

* Grayscale video feed — Found-footage horror aesthetic
* Courier New font — Surveillance system vibe
* RGB glitch effects — Psychological unease
* Slow burn pacing (70 seconds) — Builds tension instead of jump scares
* Your own face as the horror — Uncanny and unsettling

---

## 😈 Why This Exists (April Fools Logic)

This project is intentionally delightfully useless.

It:

* Solves no real problem
* Tricks users into scaring themselves
* Turns curiosity into regret

The horror comes from a simple idea:

"What if your webcam didn’t show the present… but the past?"

---

## 🏆 Challenge Submission

Category: Community Favorite

Why it fits:

* Highly shareable prank
* Creative use of browser APIs
* Generates real reactions (not cheap jump scares)
* Safe and harmless
* Works across devices

---

## 🔒 Privacy Note

* Camera access is explicitly requested
* No data is stored or transmitted
* Everything runs locally in the browser

No surveillance. Just illusions. 👁️

---

## 🚀 Getting Started

1. Clone the repo:
   git clone [https://github.com/sneh1117/someone-is-watching.git](https://github.com/sneh1117/someone-is-watching.git)

2. Open index.html in your browser

3. Allow camera access

4. Regret your decisions 👻

---

## 💡 Pro Tip

Send this to a friend at 11 PM with:

"Hey, check out this cool camera effect I built." 😈

---

## 🧑‍💻 Author

Built with:

* Insomnia
* Too many horror movies
* Questionable late-night testing on friends
