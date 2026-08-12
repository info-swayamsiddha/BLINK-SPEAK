# BLINK-SPEAK
# 👁️ BLINK-SPEAK — Simple Eye Blink Communicator

Blink-speak is a lightweight, browser-based assistive communication tool that enables patients to speak using only eye blinks. It uses real-time computer vision (MediaPipe Face Mesh) to detect blinks and translate them into words and sentences.

No installation, no server, and no app store required — just a single HTML file that runs entirely in the browser.

---

## ✨ Features

- **🎥 Camera-based Blink Detection** — Uses MediaPipe Face Mesh to track eye landmarks and compute the Eye Aspect Ratio (EAR) in real time.
- **📋 Customizable Word Board** — A 3×5 grid of common words (easily editable in the source).
- **💬 Sentence Builder** — Accumulate multiple words into a sentence before speaking.
- **🔊 Text-to-Speech** — Speaks selected words or full sentences using the Web Speech API.
- **🎵 Audio Feedback** — Distinct beeps confirm actions (next word, speak, sentence, error).
- **⚡ Real-Time Progress Bar** — Visual feedback showing how long the eye has been closed and what action will trigger on release.
- **🎯 Automatic Calibration** — Guides the user to calibrate open-eye and closed-eye EAR values for accurate detection.
- **🛠️ Caregiver Panel** — Manual override controls for testing, training, or assisting the patient.
- **📱 Mobile-First Design** — Touch-friendly, full-screen layout optimized for phones and tablets propped in front of the patient.
- **🔒 Screen Wake Lock** — Prevents the device screen from going to sleep during use.

---

## 🚀 Getting Started

1. **Download** `index.html` to your device.
2. **Open** it in a modern web browser (Chrome, Edge, Safari, or Firefox).
3. Tap **"START CAMERA"** and allow camera access when prompted.
4. Follow the **Calibration** steps:
   - Keep your eye **open** and tap **START**.
   - Keep your eye **closed** and tap **NEXT**.
5. The word board appears. Blink to communicate!

&gt; **Tip:** Prop the device 30–50 cm from the patient's face in good, even lighting for best results.

---

## 🎮 How to Use

| Blink Duration | Action |
|---|---|
| **¼ – ¾ second** (Short) | Move to the **next word** |
| **¾ – 1½ seconds** (Long) | **Speak** the currently selected word & add it to the sentence |
| **3+ seconds** (Very Long) | **Speak the full sentence** and clear the board |
| **&lt; 100 ms** | Ignored as noise |
| **&gt; 10 seconds** | Ignored (assumes the user looked away) |

### Visual Feedback
- The **progress bar** at the top fills up while your eye is closed and changes color to show what action is ready:
  - 🟢 Green → Next word
  - 🔵 Blue → Speak word
  - 🔴 Red (pulsing) → Speak sentence
- The **selected word** is highlighted with a green border in the grid.
- The **sentence** being built is shown in the top bar.

---

## 🛠️ Caregiver / Manual Controls

Tap the **⚙️ gear icon** to open the caregiver panel. This provides:

- **NEXT Word** — Manually advance the highlight.
- **SPEAK Word** — Manually speak the selected word.
- **SPEAK Sentence** — Manually speak the accumulated sentence.
- **CLEAR Sentence** — Erase the current sentence.
- **RESET Highlight** — Return to the first word.
- **CAL Calibrate** — Re-run the EAR calibration.
- **VOICE ON/OFF** — Toggle text-to-speech.
- **HOLD TO SIM. BLINK** — Hold this button to simulate a blink (useful for testing without a patient).
- **TOGGLE CAMERA VIEW** — Show/hide the debug camera overlay.

---

## 📝 Customizing the Word Board

Open `index.html` in any text editor and find the `WORDS` array near the top of the `&lt;script&gt;` section:

```javascript
const WORDS = [
    "WATER", "FOOD", "MEDICINE",
    "HELP", "BATHROOM", "PAIN",
    "COLD", "HOT", "YES",
    "NO", "THANK YOU", "SORRY",
    "HELLO", "GOODBYE", "LOVE"
];
