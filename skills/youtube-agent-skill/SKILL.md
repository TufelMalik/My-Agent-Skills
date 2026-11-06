---
version: 1.0
name: youtube-agent-skill
description: >-
  Comprehensive YouTube creator suite containing 11 specialized skills and tools
  for scripting, packaging (title + thumbnail), audio/transcript editing, retention
  analysis, chapter generation, shorts extraction, SEO, viral research, comment triage,
  content planning, and channel auditing.
---

# YouTube Agent Skill Suite

Suite of 11 creator skills and tools to run, grow, and optimize a YouTube channel without external API dependencies.

## Included Skills & Tools

| Skill / Command | Description | Tool Script |
| --- | --- | --- |
| `yt-script` | Turn raw ideas into spoken scripts with scored 21-formula hooks and retention beats | `hookscore.py` |
| `yt-package` | Title and thumbnail linting for truncation, duplication, and vagueness | `title.py` |
| `yt-edit` | Converts transcripts (SRT/VTT/Whisper) into edit decision lists (dead air, filler, retakes) | `deadair.py` |
| `yt-chapters` | Generates validated chapters respecting YouTube formatting rules | `chapters.py` |
| `yt-retention` | Analyzes YouTube Studio retention export (hook leak, cliffs, slide bleed) | `retention.py` |
| `yt-viral` | Ranks collected niche videos by multiple of own-channel median | `swipe.py` |
| `yt-shorts` | Extracts high-potential Shorts from long videos with rewritten hooks | - |
| `yt-seo` | Optimized descriptions, strategic tags, and target search queries | - |
| `yt-comment` | Triages comments into 4 priority buckets and drafts replies in your voice | - |
| `yt-plan` | Schedules weekly channel output matching realistic creator hours | - |
| `yt-audit` | Complete end-to-end channel audit narrowing down to ONE critical fix | - |

## Global Locations

- **Skills Path**: `~/.gemini/config/skills/` & `~/.claude/skills/`
- **Voice Profile Template**: `~/.gemini/youtube/voice.md` & `~/.claude/youtube/voice.md`

All 11 skills are installed globally as standalone skills and can be used directly or through this orchestrator.
