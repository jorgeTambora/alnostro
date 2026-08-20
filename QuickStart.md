# SVP Quick-Start

This quick guide shows how to use the Al Nostro Social Video Pipeline (SVP).

## 1) Install & Launch
- Python 3.11+
- `pip install -r requirements.txt`
- (Windows TZ): `pip install tzdata tzlocal`
- Optional: `pip install Pillow opencv-python`
- Run: `python svp.py`

## 2) Set Up
- **Choose…** a watch folder.
- **Settings**:
  - General: watch folder, IANA timezone (e.g. `America/New_York`)
  - Features: transcription, speaker crops, thumbnails, scheduling
  - Scheduling: daily time, schedule by default
  - Limits: jobs/min (0 = unlimited)

## 3) Connect Accounts
Use **Accounts ▾**:
- Legacy Accounts Dialog (original UI) or Accounts Hub
- YouTube / Instagram / TikTok / X OAuth
- Tokens are stored in Windows Credential Manager or `data/secrets.json`

## 4) Publish / Schedule (YouTube)
- Select file → set title/description/tags/thumbnail
- Publish now or schedule at your daily time

## 5) Thumbnails
- **Platforms ▾ → Thumbnail Preview**: type a title, pick an optional frame, Generate
- Output: `data/runtime/thumbnails/<title>.png`

## 6) Vertical Crop Preview
- **Platforms ▾ → Vertical Crop Preview**: pick video → Analyze
- Shows 9:16 crop following the dominant face; needs `opencv-python` (MediaPipe optional)

## 7) Worker & Queue
- **Worker** tab: pause/resume, run due jobs, throttle, DND window, next publish preview
- **Queue** tab: filter by kind/status, run 1/5, delete selected

## 8) CLI (optional)
- Portrait version:
  ```powershell
  python -m cli.svp_cli --make-vertical --src "C:\videos\clip.mp4" --out "C:\videos\clip_portrait.mp4"
