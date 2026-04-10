# 👻 Someone Is Watching

A psychological horror web experience that turns your own webcam into the source of fear.

Built for the DEV April Fools Challenge (#418challenge), this project pranks users by making them feel like they're being watched… by themselves.

---

## 🎥 Demo

🔗 [https://sneh1117.github.io/someone-is-watching/](https://sneh1117.github.io/someone-is-watching/)

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

After **30 seconds** of relentless tension, it ends with:

"I saw everything."

---

## ⏱️ Experience Timeline

Phase 1 (0–8s): Awareness builds ("The camera is recording...")
Phase 2 (8–15s): Subtle creepy face appears in background
Phase 3 (15–22s): Ghost from past frames manifests
Phase 4 (22–30s): Full horror — glitch effects, high opacity ghost
Phase 5 (30s): Final reveal

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

```js
function captureGhostFrame() {
  const tempCanvas = document.createElement('canvas');
  const tempCtx = tempCanvas.getContext('2d');
  tempCtx.drawImage(video, 0, 0);
  ghostFrames.push(tempCanvas);
}
```

Ghost Rendering

```js
function startGhostEffect() {
  const randomFrame = ghostFrames[Math.floor(Math.random() * ghostFrames.length)];
  ghostCtx.globalAlpha = ghostOpacity;
  ghostCtx.filter = 'blur(4px) brightness(1.5)';
  ghostCtx.drawImage(randomFrame, offsetX, offsetY);
}
```

Procedural Face

```js
function drawCreepyFace() {
  faceCtx.fillStyle = '#ddd';
  faceCtx.ellipse(faceX, faceY, faceSize * 0.7, faceSize, 0, 0, Math.PI * 2);

  faceCtx.fillStyle = '#000';
  faceCtx.ellipse(leftEyeX, eyeY, eyeSize, eyeSize * 1.3, 0, 0, Math.PI * 2);
}
```

---

## 🎨 Design Choices

* Grayscale video feed — Found-footage horror aesthetic
* Courier New font — Surveillance system vibe
* RGB glitch effects — Psychological unease
* Punchy 30-second pacing — Maximum dread, zero filler
* Your own face as the horror — Uncanny and unsettling

---

## 😈 Why This Exists (April Fools Logic)

This project is intentionally delightfully useless.

It:

* Solves no real problem
* Tricks users into scaring themselves
* Turns curiosity into regret

The horror comes from a simple idea:

"What if your webcam didn't show the present… but the past?"

---

## 🏆 Challenge Submission

Category: Community Favorite

Why it fits:

* Highly shareable prank
* Creative use of browser APIs
* Generates real reactions (not cheap jump scares)
* Safe and harmless
* Works across devices
* Over in 30 seconds — short enough to send to someone mid-conversation

---

## 🔒 Privacy Note

* Camera access is explicitly requested
* No data is stored or transmitted
* Everything runs locally in the browser

No surveillance. Just illusions. 👁️

---

## 🚀 Getting Started

1. Clone the repo:
   ```
   git clone https://github.com/sneh1117/someone-is-watching.git
   ```

2. Open `index.html` in your browser

3. Allow camera access

4. Regret your decisions 👻

---

## 💡 Pro Tip

Send this to a friend at 11 PM with:

"Hey, check out this cool camera effect I built." 😈

It's only 30 seconds. They'll never see it coming.

---

## 🧑‍💻 Author

Built with:

* Insomnia
* Too many horror movies
* Questionable late-night testing on friends
