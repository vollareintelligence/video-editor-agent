---
name: html-motion-templates
description: >-
  Biblioteca de templates de motion design curtos (5–15 s, 1080×1920) escritos como
  especificação de tempo para HyperFrames (HTML + GSAP → MP4): manifesto de marca,
  logo em colagem stop motion, notificações empilhando, conversa de chat, frase no
  ritmo da música e contagem estilo VHS. Use quando pedirem "uma animação de logo",
  "um teaser de lançamento", "um hook tipográfico", "um chat animado", "prova social
  com notificações", "um vídeo-manifesto" ou a demo animada de um slide de carrossel.
  Também serve de bloco de B-roll/takeover dentro de branded-ad-edit.
---

# html-motion-templates

Cada template em `templates/` é um **contrato de animação**: para que serve, parâmetros,
roteiro de tempo em segundos, regras e checagens de QA. Não é um prompt de chat. É a
especificação que a composição HyperFrames precisa cumprir quadro a quadro.

| # | Template | Duração | Uso principal |
|---|---|---|---|
| 01 | `01-manifesto-de-marca.md` | 15 s | autoridade, post fixado, anúncio |
| 02 | `02-logo-colagem-stop-motion.md` | 5 s | vinheta de marca |
| 03 | `03-notificacoes-empilhando.md` | 10 s | prova social no gancho |
| 04 | `04-conversa-de-chat.md` | 15 s | objeção/FAQ/história |
| 05 | `05-frase-no-ritmo.md` | 8 s | hook tipográfico no beat |
| 06 | `06-contagem-vhs.md` | 10 s | teaser de lançamento |

## Como usar

1. Escolha o template pela **função**, não pela aparência.
2. Preencha os parâmetros com dados **reais** do cliente. Marca, paleta e fontes vêm do
   MASTER_CONTEXT.md. Os templates nunca carregam marca de cliente.
3. Monte a composição HyperFrames (`npx hyperframes init <slug>`): uma timeline GSAP
   pausada, cenas com `data-start`/`data-duration`, e nada dependente do relógio real
   (`setTimeout`, `Date.now`). O render precisa ser determinístico.
4. Renderize e rode o QA do template **no MP4 renderizado** (frames extraídos com ffmpeg),
   além do `video-qa` do pacote.
5. Para usar a peça como demo de carrossel 4:5, coloque o MP4 9:16 numa moldura de
   celular (ver `reel-style-clone/references/format-carousel-ideas.md`).

## Regras transversais

- Safe zone do Reels/TikTok: 120 px no topo e 340 px embaixo, sem texto essencial.
- Último 0,5–1 s estático, porque o loop do app não pode engolir a mensagem final.
- Prova social e números só com dados verdadeiros. Sem marca de aparelho ou de app real.
- Um "truque único" por peça (glitch, flash, colagem): usado uma vez, é assinatura;
  repetido, vira gimmick.

## Origem

Sistema extraído de um carrossel de referência (6 ideias com demo) via
`reel-style-clone` no modo slides. O texto, o timing e as regras foram reescritos.
Nenhum prompt, paleta ou identidade da referência foi copiado.

## Exemplo funcional

`examples/05-frase-no-ritmo.html` é o template 05 montado e validado: `npm run check`
passou, render de 8 s/240 frames em ~16 s de captura com GPU por software, e os frames
foram conferidos no MP4. Para usar: `npx hyperframes init <slug>` e troque o `index.html`.

Ambientes sem acesso ao CDN ou ao download do Chrome (sandbox, rede restrita):
- copie `gsap.min.js` para `assets/` e referencie localmente. Se o GSAP não carregar,
  o check acusa `Cannot read properties of undefined (reading 'timeline')`;
- aponte `HYPERFRAMES_BROWSER_PATH` para um Chrome ou chrome-headless-shell já instalado.

Contraste em fundo alternado: texto branco sobre laranja médio fica abaixo de 3:1.
Na fase de fundo de acento, use a cor escura da paleta para o texto.
