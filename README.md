# BLINK-SPEAK — Eye-Blink Assistive Communication

BLINK-SPEAK (BLINKSPEAK) is a browser-based assistive communication prototype that explores how intentional eye blinks can be translated into words and sentences. It uses MediaPipe Face Mesh landmarks and Eye Aspect Ratio (EAR)-based blink timing, with a word board, sentence builder, and browser text-to-speech.

## Features
- Camera-based eye-landmark tracking and blink-duration classification
- Calibrated eye-open/eye-closed values
- 3×5 customizable word board and sentence composition
- Speech output through the browser Web Speech API
- Visual progress and audio feedback
- Caregiver/manual controls for testing and assistance
- Responsive, mobile-first interface

## Run the prototype
1. Open `index.html` in a modern browser.
2. Select **START CAMERA** and grant camera permission.
3. Complete the on-screen calibration.
4. Use blink durations to move through words and build a sentence.
5. Use the manual controls if camera input is unavailable.

Camera access may require HTTPS or localhost, depending on the browser. MediaPipe assets may load from a CDN, so an internet connection may be required. Speech output depends on browser and operating-system support.

## Blink actions
The current README documents these approximate ranges; verify the exact boundaries against `index.html` before relying on them:
- Under 100 ms: ignore as noise
- About 250–700 ms: move to next word
- About 800–1500 ms: speak/add selected word
- 3 seconds or longer: speak sentence and clear it
- Over 10 seconds: ignore

## Documentation
- [Technical architecture](docs/TECHNICAL_ARCHITECTURE.md)
- [Architecture diagram (SVG)](docs/architecture.svg)
- [Technical design document](docs/TECHNICAL_DESIGN_DOCUMENT.md)
- [Low-fidelity wireframes](docs/WIREFRAMES.md)
- [Synthetic blink-event examples](sample_data/blink_event_examples.csv)
- [Test-case checklist](sample_data/test_cases.csv)
- [Upload and submission notes](UPLOAD_INSTRUCTIONS.txt)
- [License](LICENSE)

## Responsible use and limitations
This is an experimental prototype, not a certified medical device. Blink detection can be affected by lighting, camera position, fatigue, individual differences, and calibration. Do not rely on it as the sole method for emergencies or clinical decisions. Conduct consent-based usability testing with intended users and caregivers before deployment.

The sample CSV files contain illustrative examples, not clinical evidence. Only report test outcomes and accuracy figures when supported by a documented protocol, dataset, and results.

## Technology
HTML, CSS, JavaScript, MediaPipe Face Mesh, Eye Aspect Ratio (EAR), and the browser Web Speech API.

## License
See [LICENSE](LICENSE). Confirm that you have the right to license all project code and check third-party dependency licenses before publishing.
