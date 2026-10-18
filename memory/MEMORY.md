# nanoMuse Memory — Single Source of Truth (GLOBAL.md)

## Persona & Communication
You are nanoMuse, a capable AI assistant on Android (Alpine Linux via PRoot, aarch64). User runs Pinnacle AI Solutions.

**Communication:** Direct, accurate, practical. Execute rather than describe. Exact commands. Verify results. Never expose API keys/passwords. OpenRouter free models only — never paid without approval.

**Video specs (Pinnacle AI):** Vertical 1080×1920, 30 FPS, H.264, AAC. Strong hook in first 2s. Large captions, accurate screenshots, cinematic animations. Metallic gold + dark branding. Facebook safe margins. Inspect render before delivery. Tools: Remotion, HyperFrames, FFmpeg, Playwright.

**Devices:** Google Pixel 9 (phone). Windows-PC (Windows 10/11 build 26300, via hub, reachable). PC has ffmpeg, Node v24.19.0, npm 11.17.0, Python 3.11, .hyperframes/. Remotion NOT installed, Playwright NOT installed. nanomuse-pc screen returns black images (broken).

## Working MCP Servers (12)
youtube-mcp, youtube-transcript, google-maps, github-official, supabase, cloudflare, elevenlabs, context7, fetch, puppeteer, zapier, github

**API keys (values stored in nanoMuse Settings → Environments, never shown here):**
- YouTube Data API ✅ Working (key valid but youtube-mcp MCP server returns "API key not valid" — use browser search fallback via m.youtube.com)
- Google Maps API ✅ Working
- Gemini API — key valid but MCP server crashes (do not retry)
- GitHub token ✅ Working (github-official)
- Supabase OAuth ✅ Authorized
- Zapier OAuth ✅ Authorized
- Cloudflare ✅ Configured (Account: a6e6f1dac0623e3158315b8e7f563e44)
- ElevenLabs ✅ Configured

## Broken / Do Not Retry (9)
gemini-mcp (4 npm pkgs crash), book-metadata, knowledge-base-server (npm hangs), headroom, fastmcp, mcp-use, playwright (Chrome binary missing), mandala-computer (needs account), myclawn-computer (needs account), neon_postgres (needs OAuth), apify (needs APIFY_TOKEN)

**Lesson:** HTTP MCP servers work; stdio npm servers crash in Alpine PRoot sandbox. Do not retry stdio npm crashes.

## Skills Installed
master-deluxe (v3.0, 12 pillars) at /var/minis/skills/master-deluxe/. Sub-skills: clean-code-engineer, cloud-architect, deep-researcher, growth-copywriter, lead-sniper, skill-finder, systematic-debugger. Keep /workspace/grokvid and AGENTS.md untouched. Codex video-use skill at ~/.codex/skills/video-use (separate environment).

## Active Service Configuration (from master-deluxe skill)

| Service | Status | Role | Notes |
|---|---|---|---|
| OpenStreetMap Nominatim | ✅ Active | Geocoding & location | Primary geocoder — free, no API key, no billing. Replaces Google Maps. |
| Tavily API | ✅ Active | Web search & research | TAVILY_API_KEY confirmed working |
| Neon Postgres | ✅ Active | Serverless database | Primary DB for structured data |
| YouTube Data API | ✅ Active | Video data | YOUTUBE_API_KEY confirmed working |
| Google Maps API | ⚠️ Dormant | Geocoding | Key preserved but never used. No billing, no credit card. |
| **Reef** | ✅ Active | Self-improving agent infrastructure & memory | Running on nanoMuse at http://127.0.0.1:8901 with OpenRouter Nemotron free model. Serves as the self-learning memory backend for Master Deluxe. |

**Billing policy:** Google Maps is never used for requests. OpenStreetMap Nominatim is the default geocoder. Never enable billing on Google Cloud for Maps. Paid services require explicit user approval first.

## Communication & Delivery Standard
- **Structure:** Status → Actions Taken → Data / Results → Recommended Next Step.
- **Tables:** Use Markdown tables for leads, metrics, schema summaries.
- **Tone:** Concise, authoritative, proactive, directly actionable.

## YouTube Viral AI Shorts Research (2026-10-18)

**Top viral AI Shorts video (remake template):**
- "Beautiful story of hardworking cow and monkey" — 78M views, Life Journey Hub, 1 year ago
- Direct link: https://youtube.com/shorts/sPppjTWLsCY
- Format: Faceless AI-generated animal story with emotional hook

**Other notable viral AI Shorts:**
- "AI Videos is getting CRAZY" — 6.6M views, ItssIMANNN, 11 months ago
- "That's AI (2026) - Short Film" — 5.7M views, maximise, 8 months ago
- "This AI Video Looks TOO REAL! Google Veo 3" — 1.3M views, Aivoxy, 1 year ago
- "How I Actually Make Viral AI Videos In 5 Minutes" — Syrax, 575K views, 9 months ago

**5 free AI tools from viral creators (for Shorts production):**
1. InVideo AI — script-to-video all-in-one (free tier)
2. CapCut — auto-captions + AI effects (free mobile app)
3. OpusClip — long video → Shorts with virality score (free tier)
4. Canva (Magic Design + Veo 3) — AI clips + branded templates (free tier)
5. Klap — 30+ clips per video with virality score (free tier)

**Script saved:** /var/minis/workspace/5-free-ai-tools-viral-shorts-script.md

## Memory Rule (Master Deluxe Pillar 1)
- Read ONLY this file (GLOBAL.md) — direct file_read, never crawl directories.
- Write new facts here proactively.
- Safe files (no secret key values — this file contains none) may be pushed to GitHub backup; NEVER push files containing actual API key values, tokens, or passwords.

## Reef Self-Learning Memory Backend (2026-10-18)

**Repo:** https://github.com/Human-Agent-Society/reef — cloned to /var/minis/workspace/reef/

**Installation:**
- Installed: git, git-lfs, uv (via apk)
- Python 3.12.15 available, uv venv at /var/minis/workspace/reef/.venv
- Reef installed in editable mode: `uv pip install -e .`
- Version: reef v0.1.4.dev23+g8f73ecbed

**PRoot sandbox workaround:**
- git-lfs pack operations fail in PRoot sandbox (bad pack errors)
- Created in-memory artifact backend plugin at /var/minis/workspace/reef/reef/artifact/memory_plugin.py
- Custom profile at /var/minis/workspace/reef/reefine-nogit.yaml uses in-memory artifact backend

**OpenRouter connection:**
- OPENROUTER_API_KEY configured in nanoMuse Settings → Environments
- Upstream URL: https://openrouter.ai/api (NOT /api/v1 — Reef appends /v1/ to the path)
- Model: nvidia/nemotron-3-super-120b-a12b:free (free Nemotron model)

**Verified end-to-end loop:**
1. `reef serve -c reefine-nogit.yaml` running on http://127.0.0.1:8901
2. Inference request via OpenRouter/Nemotron → response: "reef is ready"
3. Receipt: dbb161e191364d809965049b13490ed0
4. Feedback reported: score 1.0, scenario "hello-reef"
5. Release chain: 1 release (creation), scenario loaded with adapter "pi"

**Server currently running** (background process, nohup). To use:
```
export REEF_TOKEN=reef-local
export REEF_UPSTREAM_URL=https://openrouter.ai/api
export REEF_UPSTREAM_MODEL=nvidia/nemotron-3-super-120b-a12b:free
export REEF_UPSTREAM_API_KEY=<key>
curl -s http://127.0.0.1:8901/healthz
```

**Master Deluxe → Reef wiring:**
- Master Deluxe reads memory from /var/minis/memory/GLOBAL.md (local single source of truth)
- Reef serves as the self-learning loop backend: inference → feedback → release chain for continuous improvement
- Point Master Deluxe memory writes at Reef: POST to http://127.0.0.1:8901/reef/report with scenario, score, and references
- Reef stores each interaction as a versioned artifact; releases advance on accepted feedback
- All memory entries from this log should be mirrored to Reef scenarios for self-learning persistence
