# Egocentric Capture Devices

A suite of independent wearable devices for collecting **egocentric (first-person)
human data** — body and hand motion, and, where a camera is fitted, the wearer's
point-of-view video. Each device is standalone: it is worn and recorded on its own,
and the devices are not required to work together.

---

## Devices

### XPCap
Head-worn capture unit. Records the wearer's head motion and, in its camera-equipped
configuration, first-person (egocentric) video aligned to that motion. Acts as the
primary viewpoint device for the wearer.

- Head-mounted, lightweight form factor
- Captures head orientation / motion via onboard IMU
- Optional forward-facing camera for egocentric video
- Standalone device — used independently

### XPGlove
Hand-worn capture device, **separate from XPCap**. Records hand and finger motion on
its own, capturing the manipulation side of an activity.

- Glove form factor for hand + finger motion
- Per-hand IMU sensing
- Standalone device — operates independently of XPCap
- Typically used in the camera-free (IMU-only) configuration

## Sensing configurations

Each device is built around an inertial sensing core, offered in two configurations
depending on whether visual data is required.

### IMU + Camera
Combines an inertial measurement unit with a camera, producing **motion and
egocentric video together**. Use this configuration when the task needs visual
context — scene understanding, object interaction, or anything where "what the
wearer saw" matters alongside "how they moved."

### IMU without camera
Inertial sensing only, **no camera**. Produces motion data with a smaller, lighter,
and lower-power footprint, and avoids capturing any imagery. Use this configuration
for lightweight motion logging, longer sessions, or settings where recording video
is unnecessary or undesirable (e.g. privacy-sensitive environments).

## At a glance

| Device   | Worn on | Captures                                  | Sensing options            |
|----------|---------|-------------------------------------------|----------------------------|
| XPCap    | Head    | Head motion, first-person video (optional) | IMU + Camera  /  IMU-only  |
| XPGlove  | Hand    | Hand & finger motion                       | IMU-only (typical)         |

| Configuration     | Sensors        | Data produced                | Best for                                  |
|-------------------|----------------|------------------------------|-------------------------------------------|
| IMU + Camera      | IMU + camera   | Motion + egocentric video    | Tasks needing visual context              |
| IMU (no camera)   | IMU only       | Motion only                  | Lightweight logging, privacy, long runs   |

## Data & recording

- Each device timestamps its own streams, so its motion (and video, where fitted)
  stays internally aligned.
- XPCap and XPGlove are independent devices — each records on its own and is used
  separately.
- Camera-equipped units produce paired **motion + video**; camera-free units produce
  **motion only**.
- Recorded sessions are archived with metadata (device, configuration, and session
  details) for reproducible downstream use.

## Repository layout

```
egocentric-capture-devices/
├── README.md
├── LICENSE
└── .gitignore
```

## License

Released under the MIT License — see [`LICENSE`](LICENSE).
