# TheBestMusicIDs-Hub

---

# Use playlists publicly!
The script is capable of creating playlists, and you can use it in your own scripts!
``` lua
_G.TMI_PLAYLIST_ID = "PL_2596486665_1783372320"
local playlist = loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs'))()

for _, song in ipairs(playlist) do
    if song.status == "ok" then
        print(song.id, song.name, song.category)
    end
end
```
