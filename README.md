# ElectroCAD Studio (Android) — v1.1.0

Schematic editor + PCB 2D + 3D board view + live DC circuit simulator, packaged as an Android WebView app.
All UI/logic lives in `app/src/main/assets/index.html` (editor) and `sim.html` (Sim Lab).

## Build the APK

**Option A — Android Studio:** File → Open → this folder → wait for Gradle sync → Build → Build APK(s).
APK: `app/build/outputs/apk/debug/app-debug.apk`

**Option B — Command line** (JDK 17 + Android SDK installed, `ANDROID_HOME` set):
```
./gradlew assembleDebug        # Linux/Mac
gradlew.bat assembleDebug      # Windows
```

**Option C — GitHub (no local SDK):** push this folder to a GitHub repo → Actions tab →
"Build APK" runs automatically → download `ElectroCAD-debug-apk` artifact.

## Quick test without building
Open `app/src/main/assets/index.html` in Chrome (desktop or phone) — everything works in a browser too.

## What's in v1.1.0
- Real DC simulation (Modified Nodal Analysis): resistors, pots, switches, LEDs (Vf by colour),
  diodes, batteries, VCC rails, voltmeter, ammeter, scope probe. Short-circuit detection,
  LED overcurrent / resistor power warnings, wire colour = voltage, dots = real current direction.
- 3D board view (orbit by drag, pinch/scroll zoom), auto-sized PCB board.
- Custom parts (+ New Part: name, prefix, footprint, any pin list).
- Undo/Redo (Ctrl+Z / Ctrl+Y), autosave (restored on next launch), Save/Open project JSON.
- BOM grouped by value with quantities; Android saves to `Downloads/ElectroCAD/`.
- Pinch-to-zoom on touch, rotated footprints in PCB view, Test Circuit report panel.
