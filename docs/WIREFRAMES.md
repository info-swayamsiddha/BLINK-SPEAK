# BLINKSPEAK — Low-fidelity Wireframes

These text wireframes describe the intended layout; they are not pixel-perfect screenshots. Confirm each control against the current `index.html`.

## A. Start and calibration
```text
┌─────────────────────────────────────────────┐
│ BLINKSPEAK                    Camera status │
├─────────────────────────────────────────────┤
│                                             │
│              Camera preview                 │
│                                             │
│  Calibration: eyes open → eyes closed       │
│  [ Start Camera ] [ Start / Next ]           │
│  Status / permission / calibration guidance │
└─────────────────────────────────────────────┘
```

## B. Communication board
```text
┌─────────────────────────────────────────────┐
│ Sentence: WATER PLEASE                      │
│ Blink progress bar / action hint             │
├─────────────────────────────────────────────┤
│ [ WATER ] [ FOOD ]  [ MEDICINE ]             │
│ [ HELP  ] [ BATHROOM ] [ PAIN ]              │
│ [ COLD  ] [ HOT ]   [ YES ]                  │
│ [ NO    ] [ THANK YOU ] [ SORRY ]            │
│ [ HELLO ] [ GOODBYE ] [ LOVE ]               │
├─────────────────────────────────────────────┤
│ [Speak sentence] [Clear] [Caregiver controls]│
└─────────────────────────────────────────────┘
```

## C. Caregiver/manual panel
```text
┌─────────────────────────────────────────────┐
│ Caregiver controls                          │
│ [Next] [Speak word] [Speak sentence]        │
│ [Clear sentence] [Reset highlight] [Calibrate]│
│ [Voice on/off] [Simulate blink] [Camera view]│
└─────────────────────────────────────────────┘
```

## Interaction notes
- Show the currently selected word clearly.
- Keep the sentence and blink progress visible.
- Make manual controls easy to reach without relying on eye input.
- Display camera permission, calibration, and detection status in plain language.
- Validate the actual layout with people who use assistive communication.