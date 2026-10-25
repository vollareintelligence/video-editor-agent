# 02 · Logo em colagem stop motion (5 s)

**Para que serve:** vinheta de abertura/fechamento, intro de stories, assinatura de vídeos.
**Função narrativa:** a marca "se monta" na frente do público, gerando sensação de feito à mão.

## Parâmetros
`{logo_svg}` (recriado fiel ao original, em camadas por cor) · `{tagline}` · `{textura_papel}` (opcional)

## Roteiro de tempo
| Tempo | Ação |
|---|---|
| 0,0–2,0 s | 6 a 10 fragmentos de papel nas cores do logo entram de bordas diferentes, girando ±25° |
| 2,0–3,0 s | fragmentos se encaixam na posição final; no encaixe, escala 1,06 → 1,0 ("pop") |
| 3,0–4,0 s | `{tagline}` entra como carimbo: escala 1,4 → 1,0 em 4 frames + leve rotação, opacidade irregular |
| 4,0–5,0 s | tudo parado |

## Regras
- **Stop motion é o segredo:** anime a 12 q/s (`steps()` ou snap do tempo em 1/12 s) com jitter de 1–2 px e ±0,5° por quadro. A 30 q/s suave vira "PowerPoint".
- Bordas rasgadas via máscara SVG irregular; sombra curta (2–4 px, opacidade 0,25).
- Recriar o logo exige aprovação do dono da marca. Nunca use logo de terceiros.

## QA
- No frame de 2,9 s o logo está idêntico ao original (sobrepor e comparar).
- Carimbo legível no tamanho de celular.
