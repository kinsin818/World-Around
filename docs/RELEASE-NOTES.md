# World Around / 环视TV — Release Notes (public summary)

The publisher keeps a private release ledger; this page is the public-facing
summary of the R1 builds. **No binaries are published in this repository.**
UI language: Simplified Chinese.

## R1 lineage (July–August 2026)

| Pack | What shipped |
|---|---|
| Pack 0 | Environment: .NET SDK, LibVLCSharp/VLC verified, Go + SQLite + ffprobe, Android SDK + emulator chain. |
| Pack 1 | Source Steward M3U parser: local file + remote URL, #EXTINF tags (tvg-id/name/logo/group-title), standard Channel/Stream model, unit tests. |
| Pack 2 | SQLite schema + import: sources/channels/streams/aliases/probe_runs/probe_results; duplicate-aware ingest. |
| Pack 3 | Source probing & health score: concurrent stream probes, HTTP status / open_ms / first_frame_ms / resolution, dead-link marking, health_score, dead.txt + report.md. |
| Pack 4 | Export: clean.m3u + channels.json, streams ordered by health_score, report (total / alive / dead / top failure reasons). |
| Pack 5 | Windows player skeleton: WPF, channel list left + player right, loads channels.json, click-to-play first stream, play/pause/volume/fullscreen. |
| Pack 6 | Windows failover: auto-switch to next stream on failure, "switching backup" hint, persisted recents / favorites / last channel. |
| Pack 7 | UI polish: dark TV style, large channel list, keyboard (arrows/enter) operable, clean fullscreen. |
| Pack 8 | Android MVP: Kotlin + Media3, HLS/M3U8 playback, channel tree, favorites, fullscreen (phone-first, TV later). |

## Acceptance evidence

Every pack has on-device evidence (screenshots in the private ledger): Windows
home/playing/fullscreen with official public sources (e.g. Al Jazeera English
Live), failover smoke tests, and Android portrait/landscape playback with
official HLS test streams (Apple BipBop). The screenshots in this repository's
README are drawn from those runs.

## What's deliberately not here

- Playlist data (any .m3u / channels.json / sources.txt) — self-hosted tool, the
  publisher's own sources stay private.
- Binaries — R1 artifacts are debug builds; a release build would be published
  separately if the project goes public.