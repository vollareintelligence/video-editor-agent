# Formato — Carrossel "N ideias" com demo animada por slide

Fonte analisada: carrossel de 8 vídeos (capa + 6 ideias + CTA), 1080×1350 (4:5), 30 fps,
sem áudio, sem cortes. Analisado em 2026-10-25 com o método `reel-style-clone`
adaptado para slides (ver `slides.md`).

> Copiar o **sistema** (estrutura, ritmo de leitura, gatilhos), nunca a identidade:
> paleta, fontes, assinatura e textos da criadora original não entram nas nossas peças.

## ESTRUTURA (a sequência é o produto)

| Slide | Duração | Função | O que mostra |
|---|---|---|---|
| Capa | 15 s | Promessa + prova | Vídeo real do criador usando a ferramenta, título grande embaixo |
| 01–06 | 5–15 s | Entrega | Número + nome da ideia, "resultado:" em 1 frase, demo animada, prompt pronto, "o que fazer:" |
| CTA | 5 s | Captura | Recapitulação em 3 passos + "comenta [palavra] que eu te mando" |

- A capa é **a única com movimento quase contínuo** (96% dos frames mudam). Ela vende.
- O CTA é **praticamente estático** (5% dos frames). Ele pede ação, não entretém.
- Nos slides de ideia, a demo se move entre 24% e 62% do tempo: animação com respiro
  para o olho ir da demo para o texto e voltar.

## LAYOUT DO SLIDE DE IDEIA (grade fixa)

- Topo central: assinatura pequena "Nome // Nicho" (marca recorrente sem poluir).
- Coluna esquerda (≈45% da largura): número em serifa itálica fina → título em grotesca
  bold pesada, 2 linhas, entrelinha apertada → bloco "resultado:" em grotesca regular grande.
- Coluna direita (≈35%): moldura de celular 9:16 com borda preta grossa arredondada
  rodando a demo. A demo é o vídeo de 1080×1920 que o próprio prompt gera.
- Faixa inferior: card branco imitando a caixa de prompt de um chat de IA
  (cantos arredondados, "+" à esquerda, botão de enviar laranja à direita), com o prompt
  completo e os `[campos entre colchetes]` que o leitor troca.
- Rodapé: "o que fazer:" + onde usar a peça. É o que converte salvar em usar.

## PALETA E TIPOGRAFIA MEDIDAS (referência, não usar igual)

| Papel | Cor medida | Função |
|---|---|---|
| Fundo | `#F7EFE4` creme com textura de papel | Acolhimento, "caderno" |
| Título/acento | `#6D1F29` bordô | Autoridade |
| Capa | `#640C1E` bordô profundo | Contraste com o vídeo real |
| Botão | `#C35F3F` laranja | Reconhecimento de "interface de IA" |

Sistema tipográfico: **serifa itálica fina só para números**, grotesca bold para títulos,
grotesca regular para texto, sans de interface para o prompt. Três famílias, cada uma
com uma função.

## POR QUE FUNCIONA (o que transportar)

1. **Isca de salvamento:** cada slide é uma ferramenta pronta. Prompt copiável = salvar.
2. **Prova embutida:** o resultado aparece rodando ao lado do prompt. O leitor não
   precisa acreditar, ele vê.
3. **Moldura de celular:** mostra o vídeo 9:16 dentro de um post 4:5 sem letterbox.
4. **CTA por comentário:** "comenta X" gera engajamento e lista de leads por DM.
5. **Ritmo:** a capa prende com movimento, as ideias deixam ler, o CTA para.

## COMO APLICAR

Troque a promessa da capa e as ideias pelo nicho do cliente; as demos saem dos
templates do skill `html-motion-templates`. Exemplos de nicho (anonimizados):

- **Criador de IA:** "6 animações que eu faço com IA", com uma demo de template por slide.
- **SaaS de compliance:** "5 erros que derrubam sua campanha", demo = alerta animado.
- **Fotógrafo de casamento:** "4 jeitos de entregar o filme", demo = trechos na moldura.

Identidade própria obrigatória: paleta, tipografia, assinatura e palavra de CTA do cliente
(registradas no MASTER_CONTEXT.md, nunca aqui).
