# Método para referências SEM áudio e SEM cortes (slides animados de carrossel)

Descoberto em 2026-10-25: uma "referência" pode ser um carrossel de vídeos 4:5 baixado
slide a slide. O pipeline de reel (§2 cortes, §4 áudio) devolve **zero cortes e nenhuma
faixa de áudio**, e isso não é falha: é o formato. Detecte cedo e troque de método.

## 1. Detectar o caso (antes de gastar com transcrição)

```bash
ffprobe -v error -select_streams a -show_entries stream=codec_name -of csv=p=0 ref.mp4   # vazio = sem áudio
ffmpeg -i ref.mp4 -vf "select='gt(scene,0.25)',showinfo" -f null - 2>&1 | grep -c pts_time  # 0 = sem cortes
```

Sinais do caso slide: sem áudio + 0 cortes + 4:5 (1080×1350) + duração de 5 a 15 s +
vários arquivos com o mesmo prefixo de ID. **Pule whisper, espectrograma e BPM.**

## 2. Medir o movimento por região (substitui cuts/sec)

Num slide, o ritmo mora na *região animada*, não em cortes. Meça a variação de luma
(YDIF) só na área da demo:

```bash
ffmpeg -v error -i ref.mp4 \
  -vf "crop=W:H:X:Y,signalstats,metadata=print:key=lavfi.signalstats.YDIF:file=-" \
  -f null - | grep -o 'YDIF=[0-9.]*' | cut -d= -f2 \
  | awk '{s+=$1;n++;if($1>0.5)m++} END{printf "med=%.2f movendo=%d%%\n",s/n,100*m/n}'
```

`movendo` = % de frames com mudança visível. Leitura da referência medida:
capa 96% (vende com movimento), slides de conteúdo 24–62% (respiro para ler),
CTA 5% (parado de propósito). **Esse perfil é o contrato de ritmo do clone.**

Observação: `metadata=print` escreve no stdout só com `file=-`; sem isso o resultado
some e a média divide por zero.

## 3. Ler o texto na tela (o conteúdo É o texto)

Contact sheets a 360w deixam o texto ilegível. Extraia **um frame em resolução cheia**
por slide (frame em t=2 s costuma já ter tudo montado) e leia com visão:

```bash
ffmpeg -ss 2 -i ref.mp4 -frames:v 1 -vf "scale=900:-2" evidence/full.png
```

Registre títulos, numeração e qualquer prompt/código visível.

## 4. Ordem do carrossel

Os nomes de arquivo não dizem a ordem. Reconstrua pela numeração na tela (01, 02…)
e pela função: capa = título + promessa; CTA = pedido de comentário/ação.

## 5. Saída

Em vez do style guide de reel (PACING/CAPTIONS/SOUND), entregue:
- um guia de **formato** (estrutura, grade do slide, paleta e tipografia medidas,
  perfil de movimento, por que funciona). Exemplo: `format-carousel-ideas.md`;
- um **template de motion por demo** que tenha valor reutilizável, escrito com as
  nossas palavras e timing próprio. Os templates vão para o skill `html-motion-templates`.

Regra de cópia: copie estrutura e ritmo, nunca textos, paleta, fontes, assinatura ou
prompts literais da referência.
