# PuzzleCam — Gesture Capture

A gesture-controlled photobooth app that runs entirely in the browser. No installation, no backend, and no dependencies to install.

# DESCRIPTION

PuzzleCam captures a photo using your hands as a "frame," turns it into a 3x3 puzzle with a black-and-white photobooth effect, and lets you assemble it using pinch gestures. Once completed, it is saved to a downloadable photo strip.

# SYSTEM REQUIREMENTS

- Browser: Chrome or Edge (recommended), Firefox
- Hardware: Webcam
- Internet connection: Required to load the MediaPipe model (~10MB, only the first time)
- Local server: Required to run the app (it cannot be opened directly as a file)

# CONTROL GESTURES

Gesture| Action
Both hands making a pinch| Freeze the capture area and start the countdown
One hand pinching over a puzzle piece| Drag the puzzle piece
Closed fist (hold)| Save the completed puzzle / Reset the board

# APPLICATION LOGIC

1. Show both hands to the camera and pinch to define the capture frame
2. Hold the pinch during the countdown — the photo is taken automatically
3. The photo is divided into a 3x3 puzzle with a black-and-white photobooth filter
4. Rearrange the pieces using pinch gestures
5. Once completed, make a fist to save it to the photo strip with a shattering animation
6. Download the complete photo strip once you have 3 saved puzzles

# TECHNOLOGY STACK

- "MediaPipe Tasks Vision" (https://developers.google.com/mediapipe) "v0.10.14" — hand landmark detection
- Canvas 2D API — rendering, puzzle pieces, and photobooth effects
- JavaScript (ES Modules) — no frameworks
- CSS Custom Properties — theming and layout

All external dependencies are loaded via CDN. No additional installation is required.

# TROUBLESHOOTING GUIDE

- The camera won't turn on -

Make sure no other application (Teams, Zoom, Discord, etc.) is using the camera in the background.

- The app won't load the model -

Check your internet connection. The MediaPipe model (~10MB) is downloaded from "storage.googleapis.com", and the runtime is loaded from "cdn.jsdelivr.net". If either of these domains is blocked on your network, the app will not start.

- The app displays a black screen -

Make sure you are opening the app from a local server (HTTP), rather than directly from the file explorer.

- The pinch gesture isn't detected -

Make sure you have good lighting and that both hands are visible to the camera. Move your index finger and thumb closer together until the yellow indicator on the screen activates.

# BROWSER COMPATIBILITY

Browser | Support
Chrome / Edge | Recommended
Firefox | Compatible
Safari | Limited (may require additional permissions)
Mobile | Limited (desktop recommended)

# LICENSE

MIT — free to use, modify, and share.