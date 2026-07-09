![The Best Music ID's - Hub](https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/TheBestMusicIDs.png)
# The Best Music ID's - Hub
``` lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs"))()
```

---

# Tutorials
Basic tutorials on how to use the [TheBestMusicIDs](https://github.com/DudxJs/ExploitUniverseStudio/blob/main/TheBestMusicIDs) script.
> **Find it Quickly**<br>
> [Music Section](##Music-Section)
> - [How to publish a song](###How-to-publish-a-song)
> - [Edit your published music](###Edit-your-published-music)
> - [Listen to the music posted (yours or another user's)](###Listen-to-the-music-posted-(yours-or-another-user's))<br>
> [Playlists Section](##Playlists-Section)
> - [How to get the playlist ID](###How-to-get-the-playlist-ID)
> - [How to create a playlist](###How-to-create-a-playlist)
> - [Add songs to your playlist](###Add-songs-to-your-playlist)

## Music Section
> [!Important]
> The [TheBestMusicIDs](#The-Best-Music-ID's---Hub) does not publish any type of custom song file/URL!
> Only IDs already **Available** in the official Roblox store!
### How to publish a song
- First, have the song ID on hand.
- Go to the "Publish" page.
- Please fill in the required information as requested.
- Click on `"Publish Music"`
- Please verify that this is indeed the song you wish to publish.
- Finally, perform the Key System to publish the music!
### Edit your published music
- Click on the three dots next to your already [published](###How-to-publish-a-song) song.
- A panel will appear for you to make your changes.
- When you're finished editing, click `"Save changes"` and complete the `Key System`.
### Listen to the music posted (yours or another user's)
- Click on the three dots next to the desired song.
- Select the "Listen to Music" option.
- It will open a professional audio player for you.
---
## Playlists Section
The script is capable of creating playlists, and you can use it in your own scripts!
> Example:
``` lua
_G.TMI_PLAYLIST_ID = "PLAYLIST_ID_HERE" -- Enter the ID of the playlist you want here!
local playlist = loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs'))()

for _, song in ipairs(playlist) do
    print(song.id, song.name, song.category, song.status)
end
```
### How to get the playlist ID
- Access the desired player's `profile` in the script [TheBestMusicIDs](#The-Best-Music-ID's---Hub)
- Go to the `"Playlists"` section.
- Choose the player's `public playlist`.
- Click on the three dots and select the `"Share"` option.
### How to create a playlist
- Access **your** profile.
- Go to the `"Playlists"` section.
- Click on "Create New Playlist" and edit your new playlist.
- Finally, complete the `Key System` to publish your playlist.
### Add songs to your playlist
- Click on the three dots next to the desired song.
- Select the `"Add to Playlist"` option.
- Okay, just select the playlist you want to add to the playlist.
