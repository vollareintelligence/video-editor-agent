# 03 · Notificações empilhando (10 s)

**Para que serve:** prova social nos 3 primeiros segundos de um reels (vendas, agendamentos, mensagens, apoios).
**Função narrativa:** acúmulo visível = demanda real. O ritmo acelerando simula "não para de chegar".

## Parâmetros
`{cor_fundo}` · `{notificacoes}` = 4 a 8 itens reais (app genérico, remetente, texto curto) · `{numero}` · `{rotulo}` · `{frase_final}`

## Roteiro de tempo
| Tempo | Ação |
|---|---|
| 0,0–2,0 s | tela de bloqueio genérica: relógio grande, data, fundo desfocado em `{cor_fundo}` |
| 2,0–8,0 s | notificações caem do topo com tremor de vibração (±6 px, 3 ciclos, 180 ms) e empilham; intervalo começa em 1,2 s e cai até 0,35 s |
| 8,0–9,0 s | a pilha colapsa num selo: "`{numero}` `{rotulo}` hoje" com contador subindo |
| 9,0–10,0 s | `{frase_final}` aparece embaixo; parado |

## Regras
- **Sem marca de aparelho ou de app real** (ícones genéricos). Só notificações verdadeiras: inventar prova é propaganda enganosa.
- Dados pessoais de terceiros ficam borrados ou trocados por iniciais.
- Empilhamento: no máximo 5 visíveis; as antigas descem e saem por baixo.

## QA
- Contagem final bate com a quantidade/valor real informado pelo cliente.
- Nenhum nome completo ou telefone legível.
