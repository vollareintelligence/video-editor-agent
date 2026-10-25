# 04 · Conversa de chat animada (15 s)

**Para que serve:** responder objeção, pergunta frequente ou contar história curta. Funciona como gancho ou como o reels inteiro.
**Função narrativa:** o público se reconhece na mensagem do "cliente" e recebe a resposta pronta.

## Parâmetros
`{cor_balao}` · `{contato}` (nome/iniciais) · `{mensagens}` = lista alternando `cliente:` e `eu:` (2 a 6 trocas) · `{emoji_final}`

## Roteiro de tempo
- Antes de cada mensagem, indicador "digitando…" com 3 pontos pulsando.
- Duração do "digitando" e da leitura proporcionais ao texto: `digitando = 0,6 s + 0,02 s × caracteres`, `leitura = 0,8 s + 0,045 s × caracteres` (teto de 3,5 s).
- Balões entram com escala 0,9 → 1,0 + subida de 12 px em 8 frames (ease out).
- Últimos 2 s: `{emoji_final}` pula na última mensagem (escala 0 → 1,3 → 1,0) e a câmera dá zoom 1,0 → 1,35 nela.

## Regras
- App de mensagens genérico (balões cinza + `{cor_balao}`), sem marca de app real.
- Fonte de interface do sistema, tamanho ≥ 34 px no canvas de 1080 (legível no celular).
- Se o total passar de 15 s, corte trocas, não acelere a leitura.

## QA
- Cada mensagem fica visível tempo suficiente para ler em voz alta.
- O zoom final não corta o emoji nem o balão.
