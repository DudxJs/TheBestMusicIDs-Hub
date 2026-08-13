<div align="center">

<img src="https://raw.githubusercontent.com/DudxJs/TheBestMusicIDs-Hub/refs/heads/main/assets/TheBestMusicIDs.png" alt="TheBestMusicIDs" width="480">

# 🎧 TheBestMusicIDs

**A central de IDs de música para Roblox.**
Publique, descubra e organize músicas em playlists — direto no jogo.

[![Status](https://img.shields.io/badge/status-online-brightgreen)]()
[![Versão](https://img.shields.io/badge/versão-3.7-blueviolet)]()
[![Idiomas](https://img.shields.io/badge/idiomas-PT%20%7C%20EN-informational)]()

[Instalar](#-instalação) • [Playlists](#-playlists) • [API para Devs](#-api-para-desenvolvedores) • [FAQ](#-perguntas-frequentes)

</div>

---

## ✨ O que é

TheBestMusicIDs é uma interface completa para descobrir, publicar e organizar IDs de música dentro do Roblox. Sem sair do jogo, sem alt-tab pra procurar ID em fórum ou grupo — tudo em um só lugar, com player embutido, curtidas, perfis e playlists colaborativas.

---

## 🚀 Instalação

Execute no seu executor:

```lua
loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/TheBestMusicIDs-Hub/refs/heads/main/TheBestMusicIDs'))()
```

Isso abre a interface principal. Nenhuma configuração adicional é necessária.

---

## 🧭 Navegação

| Aba | O que você encontra |
|---|---|
| 🏠 **Home** | Novidades, atualizações e créditos |
| 🎵 **Músicas** | Busca, filtros por categoria e ordenação de todo o catálogo |
| 📤 **Publicar** | Adicione sua própria música ao catálogo público |
| 🏆 **Top 10** | Ranking das músicas e usuários mais curtidos |

Toque em qualquer música para abrir o player, curtir, ver o perfil de quem publicou ou adicioná-la a uma playlist.

---

## 📁 Playlists

Crie suas próprias playlists, adicione músicas do catálogo (ou músicas exclusivas, que não aparecem publicamente) e compartilhe com outros jogadores.

### Criar uma playlist

1. Abra o menu de playlists e toque em **Nova Playlist**.
2. Defina nome, capa e nome do criador.
3. Adicione músicas do catálogo ou publique uma faixa exclusiva direto na playlist.

### Colaboração

Adicione outros jogadores como colaboradores pelo nome de usuário — eles podem incluir e organizar músicas na mesma playlist.

### Organização

- Fixe músicas no topo da playlist.
- Reordene por arraste.
- Ative o modo aleatório no player da playlist.

### Copiar uma playlist

Qualquer playlist pública pode ser duplicada para a sua própria conta com um toque, preservando a ordem das músicas.

> **Alterações que exigem chave de acesso**
> Publicar música, editar uma música já publicada, criar playlist e editar informações de uma playlist existente passam por uma verificação de chave. Toque em **Pegar Key** dentro do painel de verificação para gerar seu link de acesso.

---

## 🔌 API para Desenvolvedores

Além da interface, o TheBestMusicIDs expõe suas playlists para uso em outros scripts — sem precisar abrir a UI.

```lua
local TMI = loadstring(game:HttpGet('https://raw.githubusercontent.com/DudxJs/ExploitUniverseStudio/refs/heads/main/TheBestMusicIDs'))()

local songs = TMI:GetPlaylist("PLAYLIST_ID_HERE")

for _, song in ipairs(songs) do
    print(song.id, song.name, song.category, song.status)
end
```

### Retorno

`TMI:GetPlaylist(playlistId)` retorna uma lista de músicas da playlist informada. Cada item traz:

| Campo | Descrição |
|---|---|
| `id` | ID do áudio no Roblox |
| `name` | Nome da música |
| `category` | Categoria (Funk, Phonk, Rock, etc.) |
| `status` | Situação atual do áudio (`ok`, `banned`, `private`) |

### O que você pode construir com isso

- Um jukebox próprio que toca direto de uma playlist do TMI.
- Painéis in-game que exibem o catálogo de uma playlist sem depender da interface do hub.
- Integrações com sistemas de rádio, boombox ou eventos do seu jogo.

> ID da playlist é o mesmo identificador usado no link de compartilhamento dentro do app.

---

## ❓ Perguntas frequentes

**Preciso de chave de acesso pra usar o app?**
Não. Navegar, ouvir músicas, curtir e seguir usuários é livre. A chave só é pedida para publicar, editar ou gerenciar playlists.

**Minha música sumiu da lista.**
Áudios banidos ou tornados privados pelo Roblox são sinalizados automaticamente e deixam de tocar — o card mostra o motivo.

**Posso usar `TMI:GetPlaylist` fora do contexto do app aberto?**
Sim — o carregamento retorna a interface do TMI mesmo sem abrir a GUI, permitindo consumir dados de playlists por script.

---

<div align="center">

Feito para a comunidade Roblox. · [Créditos e changelog](#-o-que-é)

</div>
