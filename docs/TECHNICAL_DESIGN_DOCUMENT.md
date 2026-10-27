# BLINKSPEAK — Technical Design Document

**Project type:** Browser-based assistive communication prototype  
**Primary interface:** `index.html`  
**Core technologies:** HTML, CSS, JavaScript, MediaPipe Face Mesh, Web Speech API

## 1. Problem
People who cannot reliably speak or use their hands may need a low-cost way to communicate basic needs. BLINKSPEAK explores intentional eye blinks as a hands-free input method.

## 2. Proposed solution
The app obtains camera permission, detects facial landmarks, estimates eye openness using Eye Aspect Ratio (EAR), and classifies eye-closure duration into commands. Commands select words, add words to a sentence, or speak a completed sentence.

## 3. User flow
1. Open the page in a compatible browser.
2. Start the camera and grant permission.
3. Complete open-eye/closed-eye calibration.
4. Use blink durations to navigate and select words.
5. Review the composed sentence on screen.
6. Use speech output or caregiver controls as needed.

## 4. Functional requirements
- Display a selectable word board.
- Detect eye landmarks from the camera stream.
- Calibrate or configure blink-detection thresholds.
- Provide visual/audio feedback for recognized actions.
- Build, speak, and clear a sentence.
- Provide manual caregiver/test controls.
- Handle camera permission and unsupported-browser cases clearly.

## 5. Non-functional requirements
- Touch-friendly responsive interface.
- Low-latency feedback suitable for communication.
- Graceful behavior when camera or speech synthesis is unavailable.
- Clear user control over camera activation.
- Accessible text, visible state, and alternative manual controls.

## 6. Data and state
The prototype primarily processes a live video stream and transient UI state: calibration values, current word index, current sentence, blink start time, and voice/control settings. Confirm actual storage and network behavior by inspecting the current implementation before making privacy claims. The CSV files in `sample_data/` are illustrative synthetic data, not clinical evidence.

## 7. Error cases
- Camera permission denied or camera unavailable.
- Poor lighting, face outside frame, or unreliable landmarks.
- Calibration performed incorrectly.
- Natural blink or prolonged eye closure misclassified as a command.
- Speech synthesis unavailable or muted.

## 8. Testing plan
Test camera startup/denial, calibration, each blink-duration category, sentence composition, speaking/clearing, manual controls, small-screen layout, and browser compatibility. Store actual results and test conditions; do not label tests as passed unless they were run and recorded. The current sample test CSV is a template/summary and must be updated with evidence before formal claims.

## 9. Limitations and responsible use
This is an experimental prototype, not a medical device. Blink timing varies by person, fatigue, eye condition, lighting, and camera position. It must not be the sole channel for emergency alerts. Conduct consent-based usability testing with intended users and caregivers, and seek accessibility/clinical review before deployment.

## 10. Future work
Personalized calibration, dwell-time alternatives, configurable vocabulary, multilingual speech, false-positive reduction, offline asset packaging, accessibility evaluation, and structured user testing.