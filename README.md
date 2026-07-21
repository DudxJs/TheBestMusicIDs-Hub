![The Best Music ID's - Hub](https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/TheBestMusicIDs.png)

# The Best Music ID's - Hub

The social music-ID hub for Roblox. Publish, discover, listen, like, follow and organize official Roblox audio IDs — with playlists, leaderboards, profiles and a smooth, custom-built interface.

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs"))()
```

![Version](https://img.shields.io/badge/version-3.7-blueviolet)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Made with](https://img.shields.io/badge/made%20with-Lua-blue)

---

## <img src="https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/SearchContents.gif" height="27"> Table of Contents

- [About](#-about)
- [Features](#-features)
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
    - [Recovering a missing song](#recovering-a-missing-song)
    - [Using a playlist in your own scripts](#using-a-playlist-in-your-own-scripts)
  - [Profile Section](#profile-section)
    - [Follow / Unfollow players](#follow--unfollow-players)
    - [Leaderboard (Top 10)](#leaderboard-top-10)
  - [Home Section](#home-section)
- [Key System](#-key-system)
- [Audio Status System](#-audio-status-system)
- [Changelog](#-changelog)
- [Disclaimer](#-disclaimer)
- [Executors](#-executors)
  - [Delta Android](#delta-android)
  - [Delta iOS](#delta-ios)
  - [Madium PC](#madium-pc)
- [Credits](#-credits)

---

## <img src="https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/about.gif" height="27"> About

[TheBestMusicIDs](#the-best-music-ids---hub) is not just a script — it's a mini social network for Roblox audio IDs. It lets any player:

- Publish and share **official Roblox audio IDs** — only IDs that exist in the real Roblox catalog, nothing custom or pirated;
- Browse, filter, search and sort everyone's submissions;
- Listen through a built-in circular-visualizer audio player;
- Like, follow, and climb a global leaderboard;
- Organize songs into public playlists that can even be used inside **your own scripts**.

Floating panels, animated effects, smooth tabs, a splash screen and an in-app changelog — every screen is built to feel like a real app, not a script menu.

---

## <img src="https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/features.gif" height="24"> Features

| Category | What you get |
|---|---|
| 🎵 **Music Publishing** | Publish any valid Roblox audio ID with name, category and preview before confirming |
| ✏️ **Editing** | Edit your own published songs (name, category, ID) at any time |
| 🎧 **Audio Player** | Custom player with circular visualizer, interactive timeline, and particle effects |
| ❤️ **Likes** | Like/unlike any song; like counts feed into sorting and the leaderboard |
| 👥 **Follow System** | Follow/unfollow players, view followers/following lists |
| 🏆 **Leaderboard** | Global Top 10 ranking based on likes and community engagement |
| 📁 **Playlists** | Create playlists, add/remove songs, recover missing songs, share via Playlist ID, and use them inside your own scripts |
| 🔎 **Search & Filters** | Search by name, category, player, or ID; sort by newest/oldest or most liked |
| 🚨 **Broken ID Detection** | Automatic detection of banned/private audios with visual banners, kept accurate by the whole community |
| 🔐 **Key System** | Quick verification step before publishing, editing, or creating playlists, keeping the hub spam-free |
| 🏠 **Home / Changelog** | In-app changelog with categorized update cards (added / removed / fixed) |

---

## Tutorials

Basic tutorials on how to use the [TheBestMusicIDs](#the-best-music-ids---hub) script.

> [!IMPORTANT]
> [TheBestMusicIDs](#the-best-music-ids---hub) does **not** publish any type of custom song file or external URL. Only IDs **already available** in the official Roblox audio catalog can be submitted.

### Music Section

#### How to publish a song
1. Have the song ID on hand.
2. Go to the **"Publish"** tab.
3. Fill in the required information (ID, name, category).
4. Click **"Publish Music"**.
5. Confirm that the preview shown is indeed the song you want to publish.
6. Complete the [Key System](#key-system) to finish publishing.

#### Edit your published music
1. Click the three dots (`⋯`) next to your already [published](#how-to-publish-a-song) song.
2. A panel will open with your song's editable fields.
3. Make your changes and click **"Save changes"**.
4. Complete the [Key System](#key-system) to confirm the edit.

#### Listen to the music posted (yours or another user's)
1. Click the three dots (`⋯`) next to the desired song.
2. Select **"Listen to Music"**.
3. A dedicated audio player opens with a circular visualizer and interactive timeline — play, pause, seek and restart freely.

#### Like a song
1. Click the <img src="https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/like.png" height="20"> icon on any song card.
2. Your like is saved instantly and contributes to that song's ranking and the poster's leaderboard score.
3. Click again to unlike.

#### Report a broken / banned ID
- The hub automatically checks each audio's status (OK / banned / private) and displays a colored banner on the song card when a problem is detected.
- When any player encounters a broken ID, it's quietly reported in the background so the listing stays accurate for everyone — no manual action required.

---

### Playlists Section

Create playlists, share them with anyone, and even **use them inside your own scripts**.

> Example:
```lua
local TMI = loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs'))()
local songs = TMI:GetPlaylist("PLAYLIST_ID_HERE")

for _, song in ipairs(songs) do
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

#### Recovering a missing song
Sometimes a song inside your playlist stops being available (the original poster deleted it, it got banned, etc.). Instead of vanishing silently, it turns into a greyed-out **"Song Removed"** card so you always know what happened.

1. Open the greyed-out card.
2. Flip the **"Remove from playlist"** switch.
3. Confirm — the song is cleared from your playlist, no strings attached.

#### Using a playlist in your own scripts
As shown above, call `TMI:GetPlaylist("PLAYLIST_ID_HERE")` right after loading the script. Instead of opening the interface, it hands you back a simple list of songs (`id`, `name`, `category`, `status`) that you can loop through in your own code — perfect for custom jukeboxes, auto-players, and more.

Calling `GetPlaylist` skips opening the interface automatically — nothing else changes about how you load the script. If you don't call it, `loadstring(...)()` behaves exactly like the one-liner at the top of this README and opens the interface normally.

> [!NOTE]
> `TMI:GetPlaylist(...)` needs to be called right after the `loadstring(...)()` line, with no delay in between — otherwise the interface will already be on its way to opening.

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

## <img src="https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/key.png" height="24"> Key System

To keep the hub spam-free, publishing a song, editing one, or creating a playlist asks for a quick verification step first. It's fast, consistent, and appears the same way across every action that needs it.

---

## <img src="https://media0.giphy.com/media/v1.Y2lkPTZjMDliOTUyemJtY2F2d3ZzOHNhYTZobnNycHViMDZveHV6ZGxla3plZTA1bWNwNSZlcD12MV9naWZzX3NlYXJjaCZjdD1n/S1xV8cDgf7xJu/200.webp" height="24"> Audio Status System

Every song is kept up to date automatically. Each card shows its current status at a glance:

| Status | Meaning | Banner |
|---|---|---|
| ✅ `ok` | Audio plays normally | none |
| 🚫 `banned` | Audio was taken down / doesn't exist | red banner |
| 🔒 `private` | Audio exists but isn't public | yellow banner |

The whole community helps keep this accurate in the background, and songs that come back online are only marked `ok` again once that's genuinely confirmed — so a status never flickers back and forth because of a one-off connection hiccup.

---

## <img src="https://caas.du.edu.om/wp-content/uploads/2023/09/new.gif" height="24"> Changelog

> Check the in script **Home** tab for the most up-to-date changelog.
**NEXT UPDATE *v3.8***
- Portuguese and English languages

---

## <img src="https://cdn.pixabay.com/animation/2023/04/28/18/34/18-34-10-554_512.gif" height="24"> Disclaimer

- This script only references **official Roblox audio IDs** already available on the platform. It does not host, upload, or stream any third-party/custom audio files.
- Use of external scripts/executors is subject to Roblox's Terms of Service. Use at your own risk.

---

## Executors
> [!tip]
> You need to have one of these to run the [TheBestMusicIDs](#the-best-music-ids---hub) script.

### Delta Android
Click to [Download](https://deltaexploits.gg/delta-executor-android)
### Delta iOS
Click to [Download](https://deltaexploits.gg/delta-executor-ios)
### Madium PC
Click to [Download](https://getmadium.net/)

---

## <img src="https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/copyright.gif" height="27"> Credits

Developed and maintained by **[DudxJs](https://github.com/DudxJs)**.

If you enjoy the project, consider leaving a <img src="https://i.pinimg.com/originals/23/15/2a/23152ad938857f99ee19485d608ef091.gif" height="24"> on the repository!
