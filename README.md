![The Best Music ID's - Hub](https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/TheBestMusicIDs.png)

# The Best Music ID's - Hub

A social music-ID hub for Roblox executors: publish, discover, listen, like, follow and organize official Roblox audio IDs — with playlists, leaderboards, profiles and a real-time key system, all wrapped in a custom-built UI.

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs"))()
```

![Version](https://img.shields.io/badge/version-3.5-blueviolet)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Made with](https://img.shields.io/badge/made%20with-Lua-blue)

---

## 📖 Table of Contents

- [About](#-about)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Tutorials](#tutorials)
  - [Music Section](#music-section)
    - [How to publish a song](#how-to-publish-a-song)
    - [Edit your published music](#edit-your-published-music)
    - [Listen to the music posted (yours or another user's)](#listen-to-the-music-posted-yours-or-another-users)
    - [Like a song](#like-a-song)
    - [Report a broken / banned ID](#report-a-broken--banned-id)
  - [Playlists Section](#playlists-section)
    - [How to get the playlist ID](#how-to-get-the-playlist-id)
    - [How to create a playlist](#how-to-create-a-playlist)
    - [Add songs to your playlist](#add-songs-to-your-playlist)
    - [Using a playlist in your own scripts](#using-a-playlist-in-your-own-scripts)
  - [Profile Section](#profile-section)
    - [Follow / Unfollow players](#follow--unfollow-players)
    - [Leaderboard (Top 10)](#leaderboard-top-10)
  - [Home Section](#home-section)
- [Key System](#-key-system)
- [Audio Status System](#-audio-status-system)
- [Project Architecture](#-project-architecture)
- [Changelog](#-changelog)
- [Disclaimer](#-disclaimer)
- [Credits](#-credits)

---

## 📌 About

**TheBestMusicIDs** is not just a script — it's a mini social network for Roblox audio IDs, built entirely with custom Lua UI (no Roblox Studio, no external GUI libraries). It lets any player:

- Publish and share **official Roblox audio IDs** (the script never hosts or plays custom/pirated audio files — only IDs that exist in the real Roblox catalog);
- Browse, filter, search and sort everyone's submissions;
- Listen through a built-in circular-visualizer audio player;
- Like, follow, and climb a global leaderboard;
- Organize songs into public playlists that can even be consumed from **other scripts**.

The interface is fully custom-made: floating panels, animated RGB strokes, tab systems with scroll-fade, splash screen, changelog cards on the Home page, and more — all built from scratch on top of Roblox's native UI instances.

---

## ✨ Features

| Category | What you get |
|---|---|
| 🎵 **Music Publishing** | Publish any valid Roblox audio ID with name, category and preview before confirming |
| ✏️ **Editing** | Edit your own published songs (name, category, ID) at any time |
| 🎧 **Audio Player** | Custom player with circular visualizer, interactive timeline, and particle effects |
| ❤️ **Likes** | Like/unlike any song; like counts feed into sorting and the leaderboard |
| 👥 **Follow System** | Follow/unfollow players, view followers/following lists |
| 🏆 **Leaderboard** | Global Top 10 ranking based on likes and community engagement |
| 📁 **Playlists** | Create playlists, add/remove songs, share via Playlist ID, and consume them externally |
| 🔎 **Search & Filters** | Search by name, category, player, or ID; sort by newest/oldest or most liked |
| 🚨 **Broken ID Detection** | Automatic detection of banned/private audios with visual banners and community-driven reporting |
| 🔐 **Key System** | Anti-abuse key verification required before publishing, editing, or creating playlists |
| 🏠 **Home / Changelog** | In-app changelog with categorized update cards (added / removed / fixed) |
| 🛡️ **Anti-Direct-Run Protection** | Core module refuses to run unless loaded through the official loader |

---

## ⚙️ How It Works

The script uses a **modular loader architecture**. When you run the loadstring above, it:

1. Authenticates the request and points to the correct module folder (public build);
2. Downloads and executes each module **in order** from GitHub, reporting progress (used to drive the splash screen);
3. Boots the main GUI once every module has loaded successfully.

```
config.lua        → constants, icons, colors, Supabase & Key System URLs, global cache/state
core.lua          → pure utility functions (buttons, switches, panels, formatting, etc.)
api.lua           → Supabase requests: likes, follows, playlists, pagination, Roblox user lookups
audio_player.lua  → the audio player screen (visualizer, timeline)
ui_components.lua → reusable UI: splash screen, key system panel, music cards, playlist modals
id_change_system.lua → ID editing, ID validation, and broken-audio reporting queue
profile.lua       → user profile, leaderboard calculation, playlists, follow lists
music_list.lua    → publish flow, music feed, filters/search, sorting
main_gui.lua       → main interface, tab system, Home page, entry point (main())
```

All data (music entries, likes, follows, playlists) is stored in a **Supabase** backend and read/written through `api.lua`, so everything you publish is visible to every other user of the script in real time.

---

## Tutorials

Basic tutorials on how to use the **TheBestMusicIDs** script.

> [!IMPORTANT]
> **TheBestMusicIDs** does **not** publish any type of custom song file or external URL. Only IDs **already available** in the official Roblox audio catalog can be submitted.

### Music Section

#### How to publish a song
1. Have the song ID on hand.
2. Go to the **"Publish"** tab.
3. Fill in the required information (ID, name, category).
4. Click **"Publish Music"**.
5. Confirm that the preview shown is indeed the song you want to publish.
6. Complete the **Key System** to finish publishing.

#### Edit your published music
1. Click the three dots (`⋯`) next to your already [published](#how-to-publish-a-song) song.
2. A panel will open with your song's editable fields.
3. Make your changes and click **"Save changes"**.
4. Complete the **Key System** to confirm the edit.

#### Listen to the music posted (yours or another user's)
1. Click the three dots (`⋯`) next to the desired song.
2. Select **"Listen to Music"**.
3. A dedicated audio player opens with a circular visualizer and interactive timeline — play, pause, seek and restart freely.

#### Like a song
1. Click the <img src="https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/like.png" height="15"> icon on any song card.
2. Your like is saved instantly and contributes to that song's ranking and the poster's leaderboard score.
3. Click again to unlike.

#### Report a broken / banned ID
- The script automatically checks each audio's status (OK / banned / private) and displays a colored banner on the song card when a problem is detected.
- When any player encounters a broken ID, the script quietly reports it in the background (throttled, with retries) so the listing stays accurate for everyone — no manual action required.

---

### Playlists Section

The script can create playlists, and **you can consume them from your own scripts** too.

> Example:
```lua
_G.TMI_PLAYLIST_ID = "PLAYLIST_ID_HERE" -- Enter the ID of the playlist you want here!
local playlist = loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs'))()

for _, song in ipairs(playlist) do
    print(song.id, song.name, song.category, song.status)
end
```

#### How to get the playlist ID
1. Access the desired player's **profile** inside the script.
2. Go to the **"Playlists"** section.
3. Open the player's **public playlist**.
4. Click the three dots (`⋯`) and select **"Share"** to copy the Playlist ID.

#### How to create a playlist
1. Access **your own** profile.
2. Go to the **"Playlists"** section.
3. Click **"Create New Playlist"** and fill in its name/details.
4. Complete the **Key System** to publish your playlist.

#### Add songs to your playlist
1. Click the three dots (`⋯`) next to the desired song.
2. Select **"Add to Playlist"**.
3. Choose the playlist you want to add the song to.

#### Using a playlist in your own scripts
As shown above, set `_G.TMI_PLAYLIST_ID` to the target playlist ID **before** loading the script. Instead of opening the GUI, the loader returns a plain Lua table of songs (`id`, `name`, `category`, `status`) that you can loop through in your own code — useful for building custom jukeboxes, auto-players, etc.

---

### Profile Section

#### Follow / Unfollow players
- Visit any player's profile and click **Follow**/**Unfollow**.
- View full **Followers** and **Following** lists from the profile tabs.

#### Leaderboard (Top 10)
- The **"Top 10"** tab ranks players based on likes received across their published songs.
- The current #1 player is highlighted with a special badge across the interface.

---

### Home Section
The **Home** tab shows:
- A changelog with the latest updates, categorized as **Added**, **Removed** or **Fixed**, each with its own icon/color;
- Credits section for the script's authors/contributors.

---

## 🔐 Key System

To prevent spam and abuse, any action that writes data (**publishing**, **editing**, **creating a playlist**) requires completing a **Key System** check before the request is sent. The key panel is reused across all these flows, so the experience is always consistent.

---

## 🚦 Audio Status System

Every song ID is periodically validated against Roblox. Statuses are cached per session so the same ID isn't re-checked repeatedly, and are shown directly on each music card:

| Status | Meaning | Banner |
|---|---|---|
| ✅ `ok` | Audio plays normally | none |
| 🚫 `banned` | Audio was taken down / doesn't exist | red banner |
| 🔒 `private` | Audio exists but isn't public | yellow banner |

Any player who encounters a status change contributes an update to the shared database in the background, keeping the listings accurate for the whole community without needing a moderator.

---

## 🧱 Project Architecture

```
TheBestMusicIDs (loader)
 └─ main.lua                — orchestrates module loading, order & error reporting
     ├─ security/config.lua     — constants, icons, colors, cache/state
     ├─ core.lua                — utility functions (buttons, panels, formatting)
     ├─ security/api.lua        — Supabase + Key System requests
     ├─ ui/audio_player.lua     — audio player screen
     ├─ ui/ui_components.lua    — reusable UI building blocks
     ├─ ui/id_change_system.lua — ID editing & broken-audio reporting
     ├─ ui/profile.lua          — profile, leaderboard, playlists
     ├─ data/music_list.lua     — publishing, feed, filters, search
     └─ ui/main_gui.lua         — main interface, tabs, entry point
```

`main.lua` will **refuse to run** unless it's invoked through the official loader (`TheBestMusicIDs`), which sets an internal auth token before dispatching to it. This prevents people from copy-pasting `main.lua` directly and skipping the loader flow.

---

## 🆕 Changelog

> Check the in-app **Home** tab for the most up-to-date changelog — new entries are added there first.

---

## ⚠️ Disclaimer

- This script only references **official Roblox audio IDs** already available on the platform. It does not host, upload, or stream any third-party/custom audio files.
- Use of external scripts/executors is subject to Roblox's Terms of Service. Use at your own risk.

---

## 🙌 Credits

Developed and maintained by **[DudxJs](https://github.com/DudxJs)**.

If you enjoy the project, consider leaving a ⭐ on the repository!
