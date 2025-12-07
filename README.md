# Freaky Ahh CVision: Gesture-to-GIF but with Brainrot Energy

Realtime cam: you mug, you move, you get a meme GIF slapped next to your face. Built with **Python + OpenCV + MediaPipe Holistic + NumPy + ImageIO**. Powered by pure zoomer neurons.

## What it does (sparknotes)
- Quick nod = blink gif, clap clap.
- Hands up, tuff pose, rubbing hands, finger-on-mouth thinking — it all maps to matching reaction GIFs.
- Stable transitions so it doesn’t flip out like a laggy TikTok filter.
- Full GIF playback; no frame-skipping crime.

## Setup (trust the process)
1) Use Python **3.11** (mediapipe likes that). 
2) Install deps:
	```bash
	py -3.11 -m pip install --upgrade pip
	py -3.11 -m pip install mediapipe opencv-python imageio numpy
	```
3) Run it:
	```bash
	py -3.11 freak_detector.py
	```
	Smash **Q** to yeet the window.

## Folder lore
```
FreakyAhhCVision/
├─ freak_detector.py   # main brainrot engine
├─ assets/             # the reaction GIF stash
└─ README.md           # you are here
```

## Gestures → GIFs (vibe chart)
| Gesture    | How to trigger                          | GIF |
| ---------- | --------------------------------------- | --- |
| tuff       | Hands different height + spaced wrists  | tuff.gif |
| thinking   | Index finger near mouth                 | thinking.gif |
| idea       | Index pointing up                       | idea.gif |
| blink/nod  | Fast downward head bop                  | blink.gif |
| tongue     | Mouth gap past threshold                | tongue.gif |
| hands_up   | Both hands above nose                   | hands_up.gif |
| rubbing    | Index tips close together               | rubbing_hands.gif |
| neutral    | Nothing spotted                         | black screen |

## Under the hood (quick nerd dump)
- MediaPipe Holistic gives face + both-hand landmarks.
- Nose history catches speedy nods → blink trigger.
- Mouth gap and finger-to-mouth distance for tongue/thinker.
- Gesture history smoothing so it doesn’t spaz-switch every frame.
- GIFs preload once; blended with `cv2.addWeighted` for smooth vibes.

## If it acts goofy
- **GIFs missing?** Check filenames in `assets/` match the table.
- **Cam dead?** Swap `VideoCapture(0)` to `VideoCapture(1)`.
- **Laggy GIFs?** Drop `gif_fps` or shrink cam/GIF sizes.

Made by **Abs** 
