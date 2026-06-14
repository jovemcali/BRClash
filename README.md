# ⚽ Brasileirão Clash

Card-battler de turnos com a temática do futebol brasileiro, no estilo "ponha a mala na mesa e mostre quem é craque". Todo o jogo (HTML, CSS e JavaScript) vive em um **único arquivo** `index.html`, sem frameworks — Vanilla JS puro. O progresso é salvo localmente via `localStorage`.

## ▶️ Como jogar / rodar

Abra o `index.html` no navegador (duplo clique ou arraste para uma aba). Não precisa de servidor.

- **6 turnos, 3 campos.** Vença 2 dos 3 campos em Poder. Empate em campos? Decide o Poder total.
- **Energia ⚡** = número do turno (turno 1 = 1⚡ … turno 6 = 6⚡). Não acumula.
- Até **4 cartas por campo**. Os campos 2 e 3 são revelados nos turnos 2 e 3 (mas dá pra escalar às cegas antes).
- Arraste/toque cartas da mão para os campos. Ao encerrar, as jogadas viram de costas e são reveladas na Resolução.
- Efeitos: **Virar** (ao revelar), **Contínuo** (enquanto em campo) e **Condicional**.
- **Mala Branca (Snap):** uma vez por partida, clique no troféu para **dobrar a aposta**. No turno 6 as Taças dobram sozinhas. **Amarelar** = sair pagando o valor atual.
- Monte seu deck de **12 cartas** em Meus Baralhos.

## 🎮 Modos e telas

- **Jogar:** sorteia um adversário no seu nível (com início automático em 5s e opção de cancelar).
- **Modo Copa:** 4 divisões (Série D → A). Vença a sequência de partidas para ser campeão; uma derrota (ou amarelar) elimina. Banner de fase no início, dupla confirmação ao sair, e tela de campeão com troféu, glow e confetes.
- **Loja do Cartola:** 3 figurinhas em oferta com rotação de 12h, opção de fixar (📌), estado "comprada" persistente; e versos de carta a preço padronizado.
- **Jornada:** acumule Taças 🏆 para desbloquear cartas e versos. Bloqueados aparecem em preto e branco com cadeado.
- **Coleção, Montar Baralho, Configurações** (som, tela cheia, editar perfil, compartilhar conquistas, resetar save).

## 🧱 Arquitetura (objetos globais)

- **`Game`** — núcleo da partida: estado (`Game.g`), turnos, energia, snap, validação (`stageTo`), resolução (`resolve`), fim de jogo (`finish`).
- **`UI`** — telas (`show`/`go`/`back`), modais, toasts, loja, coleção, jornada, sorteio.
- **`Decks`** — criação/edição/validação (12 cartas) e salvamento de baralhos.
- **`Copa` / `CopaStats`** — torneio por divisões e estatísticas.
- **`Shop`** — rotação de figurinhas (12h), fixação (pin) e compras.
- **`Profile` / `Coins` / `Bought` / `BackSkin`** — perfil, economia (cartolas) e posses.
- **`FX` / `Snd`** — animações em fila no DOM e engine de áudio com fallback sintetizado.
- **`CARDS` / `LOCS`** — definições de figurinhas e locais.

## 💾 Persistência (chaves `localStorage`)

`brclash_tacas`, `brclash_maxtacas`, `brclash_decks`, `brclash_active`, `brclash_coins`, `brclash_bought`, `brclash_skins`, `brclash_nick`, `brclash_avatar`, `brclash_captain`, `brclash_back`, `brclash_copastats`, `brclash_shop`, `brclash_road_seen`.

## 📁 Estrutura

```
BRCLASH/
├── index.html        # jogo completo (HTML + CSS + JS)
├── assets/
│   ├── cards/        # artes das figurinhas
│   ├── locs/         # artes dos locais
│   ├── backs/        # versos de carta
│   └── sfx/          # efeitos sonoros (.mp3, opcionais — há fallback)
└── README.md
```

> Os arquivos de `assets/` são opcionais: se uma arte ou som não existir, o jogo usa um fallback (placeholder visual ou som sintetizado) e nunca quebra.

## 🆕 Atualizações recentes

- Jornada destaca o último desbloqueio por **progressão de troféus** (não o capitão comprado); cartas bloqueadas em escala de cinza + cadeado.
- Editar perfil restrito a **nome e avatar** (não permite trocar capitão).
- Botão "Voltar" com histórico de navegação real (preserva a Copa).
- Snap: dica "clique para dobrar a aposta"; selo ×2 no turno 6 e ×4 com mala pendente.
- Sorteio com contagem regressiva grande (5s) e botão Cancelar.
- Loja: 3 cartas com rotação de 12h, pin e estado "comprada"; +300 🎩 ao alcançar um marco já comprado.
- Troca de adversário Cuca → Roger Machado; modais internos (sair da Copa / resetar save); botão Encerrar fica vermelho nos últimos 10s; compartilhamento de conquistas.

## 🛠️ Stack

HTML5 · CSS3 · JavaScript (Vanilla) — sem dependências externas.
