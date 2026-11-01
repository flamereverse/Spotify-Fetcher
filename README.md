<div align="center">

# SpotifyFetcher

**Fast, async, self-hostable Spotify → local library archiver.**

[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Docker](https://img.shields.io/badge/ghcr.io-spotfetch-2496ED?logo=docker&logoColor=white)](https://ghcr.io)


<img width="1280" height="720" alt="spotify_fetcher_banner" src="https://github.com/user-attachments/assets/6804ab33-4c32-4a02-bc9f-18a7bd6af03f" />


</div>

---

`SpotifyFetcher` takes a Spotify URL, URI, or a text file full of them, resolves the
tracks through the official Spotify Web API, finds the closest audio match on
YouTube, and writes a correctly named, correctly tagged file into your music
folder.

It never touches your Spotify account credentials beyond a Client Credentials
token. No OAuth login, no user scopes, no Premium requirement.

> **Legal note:** Spotify does not ship audio with its API. `spotfetch` resolves
> *metadata* from Spotify and *audio* from YouTube. Downloads are a re-encoding
> of a YouTube stream, not a bit-exact copy of Spotify's stream.

---

## Features

- **Async pipeline** — resolves, matches, and downloads concurrently (`--concurrency`, default 4)
- **Smart matching** — token-overlap + duration-delta + channel-authority scoring, with hard penalties for live takes, karaoke, covers, and sped-up edits
- **Resumable** — a JSONL ledger skips anything already fetched; `--overwrite` to force
- **Full metadata write-back** — ID3v2.4 / MP4 atoms / Vorbis comments, cover art, track & disc numbers, release date, ISRC
- **`{artist}/{album}/{nn} - {title}`** layout with sanitised, collision-safe filenames
- **Optional synced lyrics** from LRCLIB (`--lyrics`)
- **Rate-limit aware** — honours `Retry-After`, backs off exponentially, never hammers the API
- **Format conversion** via ffmpeg: `mp3`, `opus`, `m4a`, `flac`, `wav`
- **Container-first** — `docker run` with a single bind mount


**tags ignore pls**

spotify, spotify-downloader, spotify-fetch, spotify-fetcher, spotify-mp3, spotify-api, yt-dlp, music-downloader, cli, python, asyncio, metadata, mp3, flac, docker, download-music
