# 01 · Manifesto de marca (15 s)

**Para que serve:** peça de autoridade com cara de comercial grande. Post fixado, anúncio de topo de funil, abertura de lançamento.
**Função narrativa:** uma frase-tese quebrada em cenas curtas, cada cena com uma técnica de animação diferente, fechando no nome da marca.

## Parâmetros
`{marca}` `{perfil}` `{cor_a}` `{cor_b}` `{cor_fundo}` · `{frases}` = 3 a 5 blocos curtos (2 a 4 palavras cada)

## Roteiro de tempo (30 fps, 1080×1920)
| Tempo | Cena | Técnica |
|---|---|---|
| 0,0–1,6 s | bloco 1 | palavra única gigante, corte seco de entrada (sem fade) |
| 1,6–3,4 s | bloco 2 | linhas entram empilhadas com máscara de baixo para cima |
| 3,4–5,2 s | bloco 3 | palavra em serifa itálica sobre fundo invertido (troca de register) |
| 5,2–7,0 s | bloco 4 | varredura de cor: o fundo `{cor_b}` sobe como cortina |
| 7,0–10,0 s | bloco 5 | máquina de escrever monoespaçada com cursor piscando |
| 10,0–11,0 s | virada | risco atravessando a frase anterior + contra-frase pequena |
| 11,0–12,0 s | transição | colagem/glitch curto de fragmentos tipográficos (**truque único, usar 1 vez**) |
| 12,0–15,0 s | assinatura | `{marca}` grande, `@{perfil}` pequeno embaixo, parado no último segundo |

## Regras
- Ritmo: troca de cena a cada 1,6–1,8 s nas 4 primeiras, depois desacelera. Nunca duas técnicas iguais seguidas.
- Tipografia ocupa 70–90% da largura. Margem segura de 120 px no topo e 340 px embaixo (UI do app).
- No máximo 2 cores de acento + fundo. Contraste de texto ≥ 4,5:1.
- HyperFrames: uma `timeline` GSAP com `paused: true`, cenas como `<section data-start data-duration>`; nada de `setTimeout` (render determinístico).

## QA
- Frame em 0,1 s já mostra texto (gancho imediato).
- Cada cena legível por ≥ 0,9 s antes de sair.
- Último segundo estático (o Reels corta o loop sem perder a marca).
