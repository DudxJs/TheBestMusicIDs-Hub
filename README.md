![The Best Music ID's - Hub](https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/TheBestMusicIDs.png)

---

# Use playlists publicly!
The script is capable of creating playlists, and you can use it in your own scripts!<br>
*Example:*
``` lua
_G.TMI_PLAYLIST_ID = "PLAYLIST_ID_HERE" -- Enter the ID of the playlist you want here!
local playlist = loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs'))()

for _, song in ipairs(playlist) do
    print(song.id, song.name, song.category, song.status)
end
```
## How to use?
- Access the desired player's profile in the script [TheBestMusicIDs](https://github.com/DudxJs/ExploitUniverseStudio/blob/main/TheBestMusicIDs)
