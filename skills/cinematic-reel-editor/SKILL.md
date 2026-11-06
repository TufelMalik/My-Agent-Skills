---
version: 1.0
name: cinematic-reel-editor
description: "AI Video Editor environment for converting raw video into cinematic, high-retention 9:16 vertical Instagram Reels, YouTube Shorts, and TikTok videos. Includes word-by-word bouncy animated captions (Alex Hormozi / Neon / Minimalist styles), intelligent 16:9 to 9:16 reframing with ambient blur fill, camera punch zooms, kinetic motion overlays, procedural sound design (whooshes, pops, impacts), and ducked background music using OneTake's deterministic motion engine."
---

# Cinematic Reel Editor (9:16 Vertical)

Transform raw video recordings (landscape or portrait) into high-converting, viral Instagram Reels, YouTube Shorts, and TikTok videos.

## Features & Capabilities

1. **Intelligent Reframing (16:9 -> 9:16)**:
   - **`blur_fill`**: Beautiful blurred, zoomed ambient background with centered foreground video. No awkward black bars.
   - **`center_crop`**: Direct punch-crop to 9:16.
2. **High-Engagement Kinetic Captions**:
   - Word-by-word synchronized speech highlighting using `faster-whisper`.
   - Styles:
     - `hormozi`: Bold uppercase typeface with glowing yellow highlight pill and scale bounce on active word.
     - `neon`: Electric green cyberpunk glow.
     - `cinematic`: Elegant warm gold subtitle typography.
   - Automatic emoji integration (e.g. 💰, 🔥, ⚡, 🚀, 🤖, 💡, ⏳).
3. **Dynamic Camera Punches & Motion**:
   - Alternating punch zooms (1.0x -> 1.18x) on sentence transitions to maintain viewer dopamine and retention.
   - Subtle handheld drift and landing shake (`OM.shake`).
4. **Motion Graphics & Overlays (OneTake Engine)**:
   - Bottom retention progress bar (keeps viewers watching to completion).
   - Real-time animated audio visualizer wave.
   - Floating hook pills and pop-in callout badges (`OM.popIn`, `OM.swiftSpring`).
   - True 180° camera shutter motion blur.
5. **Procedural SFX & Sound Design**:
   - Synthesized whooshes on zoom transitions.
   - Snappy pops on keyword appearances.
   - Deep sub impacts on hooks.
   - Background music with automatic speech-ducking (-12dB duck during voice).

---

## Quick Usage

### 1. Command-Line Interface (CLI)

```bash
# Basic edit with default Hormozi style:
.\venv\Scripts\python.exe reel_editor.py edit --input raw_video.mp4 --out my_reel.mp4

# Full cinematic edit with custom callout, background music, and neon captions:
.\venv\Scripts\python.exe reel_editor.py edit \
  --input raw_video.mp4 \
  --out viral_reel.mp4 \
  --style neon \
  --bgm assets/music/cinematic_beat.mp3 \
  --hook "DON'T MISS THIS" \
  --callout "SECRET HACK" \
  --emoji "💡"

# Render pure OneTake 9:16 kinetic motion reel demo:
.\venv\Scripts\python.exe reel_editor.py motion-demo --out demo_reel.mp4 --dur 10
```

### 2. Python API

```python
from editor.video_pipeline import process_video_to_reel

result = process_video_to_reel(
    input_video="my_footage.mp4",
    output_video="final_reel.mp4",
    caption_style="hormozi",    # "hormozi", "neon", "cinematic"
    reframe_mode="blur_fill",     # "blur_fill" or "center_crop"
    enable_sfx=True,             # Procedural whooshes & pops
    bgm_path="ambient_bgm.mp3",  # Ducked automatically
    hook_text="PAY ATTENTION",
    callout_title="STEP 1",
    callout_emoji="🚀"
)
print(result)
```

### 3. MCP Server (AI Agent Integration)

Launch the Model Context Protocol (MCP) server:
```bash
.\venv\Scripts\python.exe mcp_server.py
```
Exposes tools:
- `edit_raw_video_to_reel`
- `transcribe_speech`
- `get_onetake_motion_library`
- `render_onetake_html`
