# 🎧 Sound design do Brasileirão Clash — guia de arquivos

Coloque os arquivos **`.mp3`** nesta pasta (`assets/sfx/`) usando **exatamente** os nomes abaixo
(tudo minúsculo, com `_`, terminando em `.mp3`). Ex.: `card_play.mp3`.

- Se um arquivo **não existir**, o jogo toca um som sintetizado de reserva — então nada fica mudo enquanto você baixa.
- Todos os sons são **pré-carregados no 1º toque** do jogador (sem atraso na hora da animação).
- Sons marcados **[pool]** podem tocar sobrepostos (rápidos, sem corte).
- Sons marcados **[throttle Xms]** têm trava anti-repetição (não disparam de novo antes de X ms).
- O **volume** de cada som já vem ajustado no código (coluna "vol"). Pode masterizar os arquivos perto desse nível.

> Dica: prefira clipes **curtos** (a maioria 0,1–0,6s; vitórias/derrotas/jingles podem ser maiores) e **normalizados**.
> Formato: `.mp3`.

---

## 🖱️ Interface / navegação
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `ui_click.mp3` | .45 | clique genérico / selecionar carta | [throttle 40ms] |
| `ui_back.mp3` | .45 | voltar de tela | |
| `ui_tab.mp3` | .45 | trocar aba (loja, vestiário) | |
| `ui_toggle.mp3` | .45 | ligar o som / alternâncias | |
| `ui_error.mp3` | .50 | ação inválida (sem energia, campo lotado, carta bloqueada) | curtinho "negado" |

## 🃏 Cartas
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `card_play.mp3` | .60 | escalar/posicionar carta no campo | [throttle 30ms] |
| `card_draw.mp3` | .60 | comprar carta (DRAW) | |
| `card_undo.mp3` | .55 | desfazer jogada / devolver carta à mão | |
| `card_reveal.mp3` | .65 | virar a carta na Resolução | [pool] |
| `card_destroy.mp3` | .70 | carta destruída | |
| `card_discard.mp3` | .65 | carta descartada (ex.: Tribunal da Torcida) | |
| `card_banish.mp3` | .70 | carta banida / transformada (Bruxaria) | |

## ✨ Efeitos de carta
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `effect_flip.mp3` | .60 | efeito **Virar** ativando (brilho) | [pool] |
| `effect_cont.mp3` | .55 | efeito **Contínuo** disparando no fim do turno | [throttle 40ms] |
| `fx_fireball.mp3` | .70 | bola de fogo do Dinamite voando | |
| `fx_bolt.mp3` | .65 | projétil mágico (R10) | |
| `fx_ghost.mp3` | .60 | fantasma do Z4 (rebaixamento) | |
| `fx_illusion.mp3` | .60 | ilusão se dividindo (R10) | |
| `buff_up.mp3` | .50 | carta **ganha** Poder (+N) | [throttle 45ms] [pool] |
| `nerf_down.mp3` | .50 | carta **perde** Poder (−N) | [throttle 45ms] [pool] |
| `dice_roll.mp3` | .55 | dado/roleta de sorte (toca 1x, ~1s) | faça um som de rolagem |

## 🏟️ Locais (campos)
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `loc_reveal.mp3` | .75 | **revelação** do local (lento e imponente) | momento grande |
| `loc_effect.mp3` | .60 | efeito do local **ativando** | diferente do revelar |

## 🔢 Placar / pontuação
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `score_field.mp3` | .70 | pulso do placar vencedor de cada campo (fim de jogo) | |
| `score_count.mp3` | .50 | tique de contagem de pontos (reservado/opcional) | [throttle 45ms] [pool] |

## 💼 Mala Branca (snap)
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `mala_arm.mp3` | .65 | você clica na mala → **engatilhar** (tensão) | windup/charging |
| `mala_drop.mp3` | .80 | mala caindo na mesa (snap do adversário / impacto) | impacto forte |
| `mala_commit.mp3` | .80 | **efetivação** da dobra no fim da rodada | explosão/confirmação |
| `stake_tick.mp3` | .45 | contagem dos troféus subindo | [throttle 55ms] [pool] |
| `fireworks.mp3` | .50 | fogos no ícone da mala | [throttle 40ms] [pool] |

## 📣 Banners / apito
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `turn_banner.mp3` | .70 | anúncio "Turno X" | |
| `resolution.mp3` | .70 | anúncio "Resolução" | tom diferente do turno |
| `whistle_start.mp3` | .70 | apito de início da partida | |
| `whistle_final.mp3` | .75 | apito da última rodada (turno 6) | mais longo/forte |

## 🎲 Sorteio do adversário
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `draw_spin.mp3` | .40 | tique enquanto a roleta gira | [throttle 45ms] [pool] |
| `draw_land.mp3` | .75 | roleta trava no adversário | |

## 🏆 Resultados
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `victory.mp3` | .80 | vitória | jingle |
| `defeat.mp3` | .75 | derrota | jingle |
| `draw_tie.mp3` | .70 | empate | neutro |
| `trophy_fly.mp3` | .50 | cada troféu voando p/ o troféu central | [throttle 60ms] [pool] |
| `cartola_pop.mp3` | .55 | "pop" da cartola contando cartolas | [throttle 60ms] [pool] |
| `unlock_card.mp3` | .75 | nova figurinha desbloqueada na tela de resultado | |
| `coins.mp3` | .60 | cartolas ganhas | [throttle 30ms] [pool] |
| `shop_buy.mp3` | .70 | compra na loja | |

## 🗺️ Jornada / Roadmap
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `road_fill.mp3` | .55 | trilha do roadmap preenchendo até o novo marco | [throttle 50ms] [pool] |
| `road_reveal.mp3` | .80 | revelação da recompensa no centro da tela | triunfante |

## ⏱️ Timer
| Arquivo | vol | Quando toca | Notas |
|---|---|---|---|
| `timer_low.mp3` | .50 | tique de pressão nos últimos 10s | [throttle 250ms] |
| `timer_out.mp3` | .70 | tempo esgotado | |

---

### Resumo rápido (copiar/colar a lista de nomes)
```
ui_click, ui_back, ui_tab, ui_toggle, ui_error,
card_play, card_draw, card_undo, card_reveal, card_destroy, card_discard, card_banish,
effect_flip, effect_cont, fx_fireball, fx_bolt, fx_ghost, fx_illusion, buff_up, nerf_down, dice_roll,
loc_reveal, loc_effect,
score_field, score_count,
mala_arm, mala_drop, mala_commit, stake_tick, fireworks,
turn_banner, resolution, whistle_start, whistle_final,
draw_spin, draw_land,
victory, defeat, draw_tie, trophy_fly, cartola_pop, unlock_card, coins, shop_buy,
road_fill, road_reveal,
timer_low, timer_out
```
**Total: 48 sons** (todos opcionais — o que faltar usa o som sintetizado de reserva).
