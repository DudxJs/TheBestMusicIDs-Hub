![The Best Music ID's - Hub](https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/TheBestMusicIDs.png)
# The Best Music ID's - Hub
``` lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs"))()
```

---

# Tutorials
Basic tutorials on how to use the [TheBestMusicIDs](https://github.com/DudxJs/ExploitUniverseStudio/blob/main/TheBestMusicIDs) script.
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
- Access the desired player's `profile` in the script [TheBestMusicIDs](https://github.com/DudxJs/ExploitUniverseStudio/blob/main/TheBestMusicIDs)
- Go to the `"Playlists"` section.
- Choose the player's `public playlist`.
- Click on the three dots and select the `"Share"` option.
### How to create a playlist
- Access **your** profile.
- Go to the `"Playlists"` section.
- Click on "Create New Playlist" and edit your new playlist.
- Finally, complete the `Key System` to publish your playlist.
### Add songs to your playlist.
- Click on the three dots next to the desired song.
- Select the `"Add to Playlist"` option.
- Okay, just select the playlist you want to add to the playlist.

## Music Section
> [!Important]
> The [TheBestMusicIDs](#The-Best-Music-ID's---Hub) does not publish any type of custom song file/URL!
