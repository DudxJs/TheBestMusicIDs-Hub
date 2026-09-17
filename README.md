<div align="center">

<img src="https://raw.githubusercontent.com/DudxJs/TheBestMusicIDs-Hub/refs/heads/main/assets/TheBestMusicIDs.png" alt="TheBestMusicIDs" width="480">

# TheBestMusicIDs

**The music ID hub for Roblox.**
Publish, discover, and organize music into playlists — directly in-game.

[![Status](https://img.shields.io/badge/status-online-brightgreen)]()
[![Version](https://img.shields.io/badge/version-3.8-blueviolet)]()
[![Languages](https://img.shields.io/badge/languages-EN%20%7C%20PT-informational)]()

</div>

## Table of Contents

- [Overview](#overview)
- [Getting Started](#getting-started)
- [Navigation](#navigation)
- [Playlists](#playlists)
- [Developer API](#developer-api)
- [FAQ](#faq)

## Overview

TheBestMusicIDs is a complete interface for discovering, publishing, and organizing music IDs inside Roblox. No more tabbing out to look for an ID on a forum or a group — everything lives in one place, with a built-in player, likes, profiles, and collaborative playlists.

## Getting Started

TheBestMusicIDs runs from a single loader line:

```lua
loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/ScriptsUniverseStudio/refs/heads/main/TheBestMusicIDs'))()
```

This line always fetches the latest version straight from the repository — there's nothing to download or keep up to date on your end. The main interface opens automatically.

> Only need playlist data in your own script, without opening the interface? Skip straight to [Developer API](#developer-api) — it's a separate, lighter file made just for that.

## Navigation

| Tab | What you'll find |
|---|---|
| **Home** | Latest updates and credits |
| **Music** | Search, category filters, and sorting across the full catalog |
| **Publish** | Add your own track to the public catalog |
| **Top 10** | Ranking of the most-liked songs and users |

Tap any track to open the player, like it, view the publisher's profile, or add it to a playlist.

## Playlists

Create your own playlists, add tracks from the catalog (or exclusive tracks that don't appear publicly), and share them with other players.

### Create a playlist

1. Open the playlists menu and tap **New Playlist**.
2. Set a name, cover image, and creator name.
3. Add tracks from the catalog, or publish an exclusive track directly into the playlist.

### Collaboration

Add other players as collaborators by username — they can add and organize tracks within the same playlist.

### Organization

- Pin tracks to the top of the playlist.
- Reorder by dragging.
- Turn on shuffle in the playlist player.

### Copy a playlist

Any public playlist can be duplicated to your own account in one tap, preserving the track order.

> **Changes that require an access key**
> Publishing a track, editing an already-published track, creating a playlist, and editing an existing playlist's info go through a key verification step. Tap **Get Key** inside the verification panel to generate your access link.

## Developer API

TheBestMusicIDs ships a separate, lightweight file just for pulling playlist data into your own scripts — it doesn't touch the interface, doesn't download any UI modules, and doesn't require a key. It's a plain data endpoint.

```lua
local TMI = loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/TheBestMusicIDs-Hub/refs/heads/main/API'))()

local songs = TMI:GetPlaylist("PLAYLIST_ID_HERE")

for _, song in ipairs(songs) do
    print(song.id, song.name, song.category, song.status)
end
```

Prefer something shorter? The loader also exposes `GetPlaylist` directly, so you don't need to keep the returned table around:

```lua
loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/TheBestMusicIDs-Hub/refs/heads/main/API'))()

local songs = GetPlaylist("PLAYLIST_ID_HERE")
```

Both forms call the exact same function — use whichever fits your script better.

### Return value

`GetPlaylist(playlistId)` returns a list of tracks from the given playlist. Each entry includes:

| Field | Description |
|---|---|
| `id` | Roblox audio ID — only included if the playlist owner enabled ID export |
| `name` | Track name |
| `category` | Category (Funk, Phonk, Rock, etc.) |
| `status` | Current audio state (`ok`, `banned`, `private`) |

The returned table also carries a few named fields alongside the track list (these don't interfere with `ipairs()`):

| Field | Description |
|---|---|
| `playlistId` | The ID you passed in |
| `ownerName` | Display name of the playlist's owner |
| `requireCredits` | `true` if the owner asked integrators to credit TheBestMusicIDs |

If a playlist doesn't exist, is private, or has developer access turned off, `GetPlaylist` returns an empty table and logs the reason with `warn(...)` — no exceptions are thrown, so it's always safe to iterate the result directly.

### What you can build with it

- A custom jukebox that plays straight from a TMI playlist.
- In-game panels that display a playlist's catalog without depending on the hub's interface.
- Integrations with radio systems, boomboxes, or in-game events.

> A playlist's ID is the same identifier used in its in-app share link.

## FAQ

**Do I need an access key to use the app?**
No. Browsing, listening, liking, and following users is free. A key is only requested when publishing, editing, or managing playlists.

**My track disappeared from the list.**
Tracks banned or made private by Roblox are flagged automatically and stop playing — the card shows the reason.

**Do I need to open the full app to use the Developer API?**
No — the API file is completely separate from the main loader. It never opens the interface, downloads UI modules, or asks for a key; it only fetches playlist data.

---

<div align="center">

Built for the Roblox community.

</div>
