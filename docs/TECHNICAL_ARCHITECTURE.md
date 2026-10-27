# BLINKSPEAK — Technical Architecture

## Purpose
BLINKSPEAK is a browser-based assistive communication prototype that maps intentional eye-blink durations to word-board actions and spoken output. It is a prototype, not a certified medical device.

## High-level flow

```text
User's eye → Camera stream → MediaPipe Face Mesh landmarks
                                  ↓
                         Eye Aspect Ratio (EAR)
                                  ↓
                       Blink timing / thresholds
                                  ↓
                 Word-board and sentence state
                                  ↓
                    On-screen text + Web Speech API
```

## Components
1. **Presentation layer:** HTML/CSS interface, word grid, sentence display, progress indicator, caregiver/manual controls.
2. **Camera and vision layer:** Browser camera permission and video stream; MediaPipe Face Mesh provides eye landmarks.
3. **Signal processing:** EAR is computed from eye landmarks; calibration helps adapt thresholds to the current user and camera setup.
4. **Interaction logic:** Blink duration is classified into actions, then updates the selected word or sentence.
5. **Output layer:** Visible sentence and optional speech via the browser Web Speech API; audio cues provide feedback.

## Blink mapping documented in README
- Under 100 ms: ignore as noise.
- 250–700 ms: advance to the next word.
- 800–1500 ms: speak/add the selected word.
- 3 seconds or longer: speak sentence and clear it.
- Over 10 seconds: ignore.

Exact thresholds and edge-case handling should be verified against the current `index.html` before changing the implementation.

## Runtime and dependencies
- Runs in a modern browser; camera access requires user permission and may require a secure context such as HTTPS or localhost.
- MediaPipe assets may be loaded from a CDN; internet access may therefore be required depending on the current HTML configuration.
- Speech output depends on browser and operating-system speech synthesis support.

## Privacy and safety
Camera frames are used for live blink detection in the browser. Do not claim that data never leaves the device unless network behavior and third-party asset requests have been audited. Do not use as the sole method for emergency communication or clinical decision-making. Provide caregiver/manual alternatives and validate with intended users before real-world deployment.

## Suggested validation metrics
Measure intended-action accuracy, false activation rate, missed blink rate, time to communicate a message, calibration time, and user/caregiver usability feedback. Record device, lighting, distance, browser, sample size, and test protocol for reproducibility.