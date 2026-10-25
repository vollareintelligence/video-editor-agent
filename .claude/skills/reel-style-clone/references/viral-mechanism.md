# Camada de mecanismo: por que a referência funciona

O `reel-style-clone` mede **como** um vídeo foi editado (cortes, legendas, ritmo, som).
Esta camada responde **por que** ele prende o público e transforma isso em um briefing
de produção original. Rode depois da análise forense e antes do handoff para o build.

Método adaptado de `sharon-laicc/viral-video-decomposer` (MIT). Ver
[ATTRIBUTION-viral-mechanism.md](ATTRIBUTION-viral-mechanism.md).

## Regra central

Analise método, estrutura, ritmo e lógica de produção. Não copie expressão protegida:
roteiro literal, sequência de planos característica, marca d'água, identidade do criador,
identidade de marca ou ativos proprietários. A saída é um padrão reutilizável, nunca um
clone do conteúdo.

## 1. Fatos da fonte (sempre registrar)

| Campo | Observação |
|---|---|
| Plataforma, conta, URL, data de publicação | |
| Duração | via ffprobe |
| Seguidores da conta | no momento da coleta |
| Curtidas, comentários, compartilhamentos, salvamentos | os que estiverem visíveis |
| Visualizações / alcance / retenção | só existem para contas próprias; em contas de terceiros, marque "indisponível" |
| Data da coleta | métricas mudam; sem data o número não vale |
| `extraction_method` | vídeo direto, arquivo baixado, capturas de tela, só transcrição, misto |
| `confidence` | alta, média ou baixa |
| `limitations` | áudio ausente, sem timecode exato, OCR incerto, só quadros amostrados |

### Sinais de desempenho (calcular quando houver dados)

- **Taxa de engajamento por seguidor** = (curtidas + comentários) ÷ seguidores × 100.
- **Índice de destaque** = curtidas do post ÷ mediana de curtidas dos últimos 20 posts da
  mesma conta. Acima de ~3× sugere post fora da curva da própria conta. O limiar é
  heurístico: registre o valor, não só o rótulo.
- **Comentários por 1.000 curtidas**: mede se o público conversa ou só reage.

Curtidas e comentários indicam engajamento, não distribuição. Uma referência só vira
"padrão comprovado" quando o índice de destaque é alto **e** o padrão se repete em mais de
um post da conta. Um post isolado pode ser sorte.

## 2. Segmentação narrativa

Agrupe os planos pela função, não por rótulos vagos: gancho, preparação, prova, revelação,
contraste, escalada, recompensa, resumo, CTA.

## 3. Campos do mecanismo

| Campo | Valores típicos |
|---|---|
| `hook_type` | contraintuitivo, pergunta de dor, resultado primeiro, conflito/suspense, identificação emocional, espetáculo visual, "isso é você" |
| `emotion_driver` | ansiedade, curiosidade, satisfação, companhia, desejo, confiança, alívio |
| `audience_promise` | o que o espectador ganha ao assistir até o fim |
| `curiosity_gap` | a informação plantada no início e só entregue depois |
| `rhythm` | corte rápido, três atos, fluxo do dia a dia, prova progressiva, virada |
| `visual_density` | baixa, média ou alta, com o motivo |
| `trust_signals` | tela real, processo mostrado, antes/depois, credencial |
| `comment_trigger` | a pergunta ou posição que provoca comentário |
| `conversion_move` | seguir, salvar, comentar palavra-chave, mensagem, compra, lembrança de marca |

## 4. Tabela de planos (versão compacta)

| Plano | Timecode | Imagem / ação | Fala / legenda | Função emocional | Função narrativa | Prompt reutilizável |
|---|---|---|---|---|---|---|

Seja concreto: "0–3 s, close na mesa bagunçada, zoom brusco, gancho de ansiedade" vale mais
que "abertura forte". Planos vazios (B-roll, pausa, objeto, transição) também carregam ritmo
e emoção: registre.

## 5. Briefing de produção (JSON)

```json
{
  "source": {},
  "performance": {"engagement_rate_pct": null, "outlier_index": null, "comments_per_1k_likes": null, "collected_at": ""},
  "analysis_summary": "",
  "viral_pattern": {},
  "shots": [],
  "production_template": {},
  "batch_variants": [],
  "originality_guardrails": []
}
```

## 6. Guarda-corpos de originalidade

Liste, para cada referência:
- **Reutilizável no nível do padrão:** estrutura do gancho, duração dos blocos, densidade de
  interrupções, tipo de prova, posição do CTA.
- **Precisa mudar:** texto, imagens, personagens, trilha, identidade visual, bordões e
  qualquer elemento que identifique o criador original.

## Barra de qualidade

- Timecodes e durações precisam ser exatos: o build executa o ritmo a partir deles.
- Se a evidência é incompleta, marque a confiança e não finja precisão de quadro.
- Separe a leitura humana (tese, mecanismo) da especificação de máquina (JSON).
