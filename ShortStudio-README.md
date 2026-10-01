# ShortStudio — AI Social Video Studio

Your video, social-ready in seconds. Drop in a video and AI reads the scene, location, and weather — then writes captions, subtitles, and platform descriptions, and burns them directly into your video.

> Developed under the working name ClipReady; the repo and live app are ShortStudio.

## What it does

1. **Upload** any video (MP4, MOV, WebM, up to ~500MB)
2. **AI extracts metadata** — date/time, GPS location, camera model
3. **Reads the scene** — sampled frames analyzed with Claude Vision AI
4. **Auto-fetches weather** at the time and place of recording (Open-Meteo, free)
5. **Generates platform-specific content** for TikTok/Reels, YouTube Shorts, and Facebook:
   - Titles, descriptions, hashtags
   - TikTok opening hooks
   - YouTube SEO tags
6. **Subtitle overlay** — AI captions appear live in the preview player
7. **Text overlays** — bold headline moments burned into the video
8. **Export** — captions burned into the video via Canvas + MediaRecorder (browser-native, no backend)

## Live

[visionary-zuccutto-f7f805.netlify.app](https://visionary-zuccutto-f7f805.netlify.app/)

## Run locally

Static site — serve the repo root with any static server, or deploy as-is to Netlify or Cloudflare Pages:

```bash
python3 -m http.server 8000
```

## Stack

Vanilla HTML/CSS/JS, Claude Vision API, Open-Meteo. By [Emre Senturer](https://github.com/emresenturer).
