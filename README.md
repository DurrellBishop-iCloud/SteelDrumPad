# BLE Keyboard Sound Pad

A fast, responsive web app that plays audio when keys are pressed from a BLE HID keyboard.

**Version:** 1.0.0

## Features

- **Low-latency audio** using Web Audio API
- **Works offline** - no external files needed
- **Safari/iOS compatible** - handles audio context restrictions
- **Responsive design** - works on Mac and iPhone
- **Visual feedback** - pads light up when pressed

## Supported Keys

| Key | Sound |
|-----|-------|
| A | C4 (Middle C) |
| B | D4 |
| C | E4 |
| D | G4 |
| E | C5 (High C) |

## Usage

1. Open the web app in Safari
2. **Tap anywhere** to enable audio (required on iOS)
3. Connect your BLE keyboard
4. Press keys A, B, C, D, E to play sounds

## Hosting on GitHub Pages

1. Create a new repository on GitHub
2. Push this folder to the repository
3. Go to Settings → Pages
4. Select "main" branch and "/" (root) folder
5. Your app will be at: `https://yourusername.github.io/repo-name/`

## Local Testing

Open `index.html` directly in a browser, or use a local server:

```bash
cd webapp
python3 -m http.server 8000
```

Then open: http://localhost:8000

## Customization

### Change Sounds

Edit the `KEY_CONFIG` object in the JavaScript:

```javascript
const KEY_CONFIG = {
    'a': { frequency: 261.63, label: 'C4' },   // Change frequency in Hz
    'b': { frequency: 293.66, label: 'D4' },
    // ...
};
```

### Add More Keys

1. Add to `KEY_CONFIG`
2. Add a new `.pad` div in the HTML

## Technical Notes

- Uses **Web Audio API** for lowest latency
- Synthesizes sounds in real-time (no audio files to load)
- Audio context created on user interaction (Safari/iOS requirement)
- Exponential decay envelope for natural sound

## Browser Compatibility

- Safari (Mac) ✓
- Safari (iOS) ✓
- Chrome ✓
- Firefox ✓
- Edge ✓
