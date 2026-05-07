# ClipReady — AI Social Video Studio

Turn any video into a social-media-ready package using AI.

## What it does

1. **Upload** any video (MP4, MOV, WebM, up to ~500MB)
2. **AI extracts** metadata — date/time, GPS location, camera model
3. **Reads the scene** — sends 5 sampled frames to Claude Vision AI
4. **Auto-fetches** weather at the time/place of recording (Open-Meteo, free)
5. **Generates** platform-specific content for TikTok/Reels, YouTube Shorts, and Facebook:
   - Title, description, hashtags
   - TikTok opening hook
   - YouTube SEO tags
6. **Subtitle overlay** — AI captions appear live in the preview player
7. **Text overlays** — bold headline moments burned into the video
8. **Export** — captions burned into video via Canvas + MediaRecorder (browser-native, no backend)

---

## Deploy to Netlify

### Option A — Netlify Drop (fastest)
1. Go to [netlify.com/drop](https://app.netlify.com/drop)
2. Drag the entire `clipready` folder onto the page
3. Done — you'll get a live URL instantly

### Option B — Netlify CLI
```bash
npm install -g netlify-cli
cd clipready
netlify deploy --prod
```

### Option C — GitHub + Netlify
1. Push this folder to a GitHub repo
2. Connect the repo in Netlify dashboard
3. Build command: (leave blank)
4. Publish directory: `.`

---

## No API keys required

| Service | Purpose | Cost |
|---------|---------|------|
| Anthropic Claude | Video understanding + content generation | Pay per use via claude.ai |
| Open-Meteo | Historical weather data | Free, no key |
| Nominatim | Reverse geocoding (GPS → city name) | Free, no key |

> Claude API calls go through the claude.ai interface session automatically.

---

## Export format

The exported video is **WebM** format (VP9/VP8 codec). All major platforms accept this:
- TikTok ✓ (converts automatically)
- Instagram ✓
- YouTube ✓
- Facebook ✓

For maximum compatibility, you can convert to MP4 locally using [HandBrake](https://handbrake.fr/) (free).

---

## Known limitations

- **Export is real-time**: A 5-minute video takes ~5 minutes to export. Keep the browser tab active.
- **GPS metadata**: Most iPhone videos include GPS. Android varies. If no GPS, location/weather features are skipped gracefully.
- **Audio quality**: Captured via WebAudio API — near-identical to original.
- **Max file size**: ~500MB (browser memory limit). For larger files, trim first.

---

## Roadmap (next features)

- [ ] Speech-to-text transcription (Whisper API) for word-accurate subtitles
- [ ] Direct platform upload (TikTok API, Meta API)
- [ ] Brand voice memory (save tone/style preferences)
- [ ] Clip trimming before export
- [ ] Thumbnail frame selector + download
- [ ] Auth + usage tiers (Stripe)
