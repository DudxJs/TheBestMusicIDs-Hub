<div align="center">
  <h1>ðŸš€ Roblox Advanced Script & API Loader</h1>
  <p><b>Desenvolvido por: Dudx_js (Eduardo7W7_0)</b></p>
</div>

---

## ðŸ“Œ Sobre o Projeto
Esta documentaÃ§Ã£o cobre a estrutura, o funcionamento e a integraÃ§Ã£o dos arquivos `api.lua`, `config.lua` e do script **Loader**. O sistema foi meticulosamente projetado para rodar como um **LocalScript** independente de mapa, oferecendo suporte total para executores Mobile (como Delta) e PC, garantindo compatibilidade perfeita com telas de toque e mouse.

<details>
  <summary><b>âœ¨ Clique para expandir as Funcionalidades Principais</b></summary>
  
  * ðŸ“± **Suporte Multiplataforma HÃ­brido:** Otimizado para Mobile e PC. Entradas de toque e cliques de mouse sincronizados.
  * ðŸ”„ **Loader DinÃ¢mico & Modular:** Carrega dependÃªncias de forma progressiva e segura.
  * ðŸŒ **IntegraÃ§Ã£o de API AvanÃ§ada:** Pronta para uso com `http_request` nativo do executor para comunicaÃ§Ã£o com backends em nuvem.
  * ðŸ›¡ï¸ **Sintaxe Segura:** CÃ³digo limpo e adequado ao ambiente Luau. Operadores nÃ£o suportados (como `+=`) nÃ£o sÃ£o utilizados e garantimos que o cÃ³digo esteja livre de caracteres invisÃ­veis que causam bugs no terminal.
</details>

---

## ðŸ“‚ Estrutura de Arquivos

* ðŸ“„ **`loader.lua`** - Ponto de entrada do sistema. Gerencia o carregamento inicial, a injeÃ§Ã£o da UI e chama os mÃ³dulos necessÃ¡rios.
* ðŸ“„ **`api.lua`** - MÃ³dulo principal de rede. Cuida de todas as requisiÃ§Ãµes HTTP externas de forma segura.
* ðŸ“„ **`config.lua`** - Arquivo central para definiÃ§Ãµes de variÃ¡veis, links, chaves e customizaÃ§Ãµes de interface (como o padrÃ£o Dark/Hacker Theme).

---

## âš™ï¸ Como Funciona (Fluxo de ExecuÃ§Ã£o)

Antes de rodar no jogo, Ã© fundamental entender a lÃ³gica do sistema:
1. O jogador executa o **Loader** no executor (Mobile ou PC).
2. O Loader faz o parse imediato das configuraÃ§Ãµes globais no `config.lua` (definindo o tema visual, URLs base e chaves).
3. O sistema de rede Ã© ativado chamando o `api.lua`. Ele detecta e utiliza a funÃ§Ã£o correta de rede (`http_request` ou equivalente compatÃ­vel) para interagir com o backend, validando seÃ§Ãµes ou buscando dados globais.
4. O script constrÃ³i a interface grÃ¡fica em modo LocalScript, alocando os botÃµes na tela e instanciando listeners que respondem instantaneamente ao toque ou ao clique do mouse.

---

## ðŸ’» VisualizaÃ§Ã£o dos MÃ³dulos

<details>
  <summary><b>ðŸ› ï¸ Expandir: config.lua (Exemplo)</b></summary>

```lua
-- ConfiguraÃ§Ãµes globais do sistema e UI
local Config = {
    Prefix = "!",
    Visuals = {
        Theme = "Dark/Tech",
        RGBGradients = true,
    },
    API_URL = "https://script.google.com/macros/s/SEU_ID_AQUI/exec", -- Substituir com URL de deploy
    MobileSupport = true
}
return Config
```
</details>

<details>
  <summary><b>ðŸŒ Expandir: api.lua (Exemplo)</b></summary>

```lua
-- MÃ³dulo de API utilizando http_request
local API = {}
local request_func = (syn and syn.request) or http_request or request

function API.FetchData(endpoint)
    if not request_func then
        warn("Erro: http_request nÃ£o suportado ou executor incompatÃ­vel!")
        return nil
    end
    
    local response = request_func({
        Url = endpoint,
        Method = "GET"
    })
    
    -- Retorna o corpo da requisiÃ§Ã£o de forma segura
    if response and response.StatusCode == 200 then
        return response.Body
    else
        warn("Falha na comunicaÃ§Ã£o com o servidor.")
    end
end

return API
```
</details>

---

## âœ… Checklist de Desenvolvimento & Testes

Para garantir que a integraÃ§Ã£o no Spck Editor / Termux esteja perfeita e sem erros antes da execuÃ§Ã£o no Roblox, acompanhe as etapas:

- [ ] Verificar a ausÃªncia de espaÃ§os ou caracteres invisÃ­veis no fim das linhas.
- [ ] Testar o carregamento inicial do `loader.lua` pelo Delta.
- [ ] Confirmar se o tema "Dark Mode" estÃ¡ renderizando sem conflitos de UI.
- [ ] Checar o console/terminal se o `http_request` obteve status `200` ao bater na API externa.
- [ ] Validar a movimentaÃ§Ã£o de cÃ¢mera (se hÃ¡ "Giro Infinito" ocorrendo ao arrastar elementos da tela no mobile).

---
<div align="center">
  <i>ManutenÃ§Ã£o e desenvolvimento: Fluxo otimizado para Spck Editor.</i>
</div>
