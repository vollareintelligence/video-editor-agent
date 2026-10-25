# 05 · Frase no ritmo da música (8 s @ 120 BPM)

**Para que serve:** hook tipográfico, abertura de stories, frase de impacto/bordão.
**Função narrativa:** uma palavra por batida cria tensão e a frase completa no fim libera.

## Parâmetros
`{frase}` (6 a 14 palavras) · `{bpm}` (padrão 120 → batida a cada 0,5 s) · `{cor_a}` `{cor_b}` · `{musica}` (opcional, mixada depois)

## Roteiro de tempo
- Batida `n` entra em `t = n × 60/{bpm}`. Uma palavra por batida, ocupando 80–95% da largura.
- Cada entrada: flash branco de 2 frames (opacidade 0,6 → 0) + tremida de 3 frames (±10 px).
- A cada 4 batidas o fundo alterna entre `{cor_a}` e `{cor_b}`.
- Última batida: a frase inteira aparece montada e congela até o fim.

## Regras
- Sincronia é tudo: ancore as palavras no grid de batidas, não em tempos "a olho". Se houver música, meça o BPM real (picos de grave no espectrograma) antes de montar.
- Se a frase tiver mais palavras do que batidas, junte palavras curtas (artigos, preposições) com a seguinte.
- Flash: no máximo 2 frames, para não ficar desconfortável. Evite flashes em sequência mais rápida que 3 por segundo.

## QA
- No render com música, cada palavra cai em ±1 frame da batida (conferir na forma de onda).
