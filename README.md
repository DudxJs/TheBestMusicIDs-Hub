![The Best Music ID's - Hub](https://github.com/DudxJs/TheBestMusicIDs-Hub/blob/main/assets/TheBestMusicIDs.png)

---

# Playlists Section
The script is capable of creating playlists, and you can use it in your own scripts!
> Example:
``` lua
_G.TMI_PLAYLIST_ID = "PLAYLIST_ID_HERE" -- Enter the ID of the playlist you want here!
local playlist = loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs'))()

for _, song in ipairs(playlist) do
    print(song.id, song.name, song.category, song.status)
end
```
## How to get the playlist ID
+ Access the desired player's `profile` in the script [TheBestMusicIDs](https://github.com/DudxJs/ExploitUniverseStudio/blob/main/TheBestMusicIDs)
+ Go to the `"Playlists"` section.
+ Choose the player's `public playlist`.
+ Click on the three dots and select the `"Share"` option.
## How to create a playlist
+
