# 06 · Contagem de lançamento estilo VHS (10 s)

**Para que serve:** teaser de abertura de vendas, inscrições, evento ou episódio. Stories no dia da abertura.
**Função narrativa:** contagem regressiva = urgência; estética VHS = evento, "transmissão ao vivo".

## Parâmetros
`{cor}` · `{frase_abertura}` · `{infos}` = 2 a 4 itens (data, bônus, vagas…) · `{cta}`

## Roteiro de tempo
| Tempo | Ação |
|---|---|
| 0,0–4,0 s | contagem 3, 2, 1 (1,33 s cada) sobre fundo preto; em cada troca, glitch de 4 frames (deslocamento RGB 6–12 px + faixa horizontal de ruído) |
| 4,0–6,0 s | `{frase_abertura}` estoura: escala 0,6 → 1,05 → 1,0 com aberração cromática |
| 6,0–9,0 s | `{infos}` piscam uma de cada vez (aparece seco, segura ~0,7 s, some seco) |
| 9,0–10,0 s | `{cta}` fixo com seta animada em loop curto |

## Moldura VHS (fixa o tempo todo)
- HUD: "PLAY ▶" no canto superior esquerdo, "SP" no direito, timecode correndo e "● REC" embaixo.
- Granulado animado (ruído a 12 q/s, opacidade 0,08–0,12), scanlines a 3 px e leve vinheta.
- Mira/círculo de contagem fina atrás do número (estilo líder de filme).

## Regras
- Cortes secos entre as fases, sem fades.
- Use glitch forte só nas trocas da contagem. No resto, estático e legível.

## QA
- `{cta}` legível sem glitch por ≥ 1 s.
- O granulado não reduz o contraste do texto abaixo de 4,5:1.
