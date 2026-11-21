# Diário agêntico: checkpoint 02

**Data:** 2026-11-20 · **Encontro:** 02, Produto · **Agente:** Claude Code (Claude Opus 5.5) · **Operador:** Limber Jhonathan (PO)

## Objetivo do ciclo

Entregar o pacote de produto do encontro 02 (slide 72 da Aula 01): **evidências de discovery, AI Canvas, MoSCoW do MVP, histórias com critérios de aceite e PRD v1**.

## Resultado

| Entrega | Artefato | Status |
|---|---|---|
| AI Canvas | [ai-canvas.md](../produto/ai-canvas.md) | ✅ Feito no ciclo anterior, revisado sem mudanças |
| MoSCoW do MVP | [moscow.md](../produto/moscow.md) | ✅ 7 Must, 4 Should, 4 Could, 9 Won't, com ordem de corte |
| Histórias + critérios de aceite | [historias-mvp.md](../specs/historias-mvp.md) | ✅ 10 histórias, 36 critérios Dado/Quando/Então |
| PRD v1 | [prd.md](../produto/prd.md) | ✅ Requisitos rastreados até as histórias |
| Evidências de discovery | [discovery.md](../produto/discovery.md) | 🟡 Proto-personas, concorrentes, protótipo e 1 conversa com usuário (E1) |
| Harness | [AGENTS.md](../../AGENTS.md) v0 → v1 | ✅ 5 regras novas, vindas dos erros abaixo |

## O que o agente fez

1. **Levantou as entregas do encontro.** Leu o slide 72 (checkpoints) e o slide 84 (checklist do encontro 01) no PDF da Aula 01, no Google Classroom.
2. **Priorizou o MVP (MoSCoW).** Partiu do PRD v0 e usou um critério objetivo: *é Must só o que o fluxo principal precisa para funcionar*. Definiu uma ordem de corte (Could → S4 → S3 → S2 → S1) para o caso de o prazo apertar.
3. **Escreveu as histórias.** São 10 histórias ligadas às personas do PRD. Cada uma tem caminho feliz, casos de erro e borda (XML inválido, descrição curta, sistema não cadastrado, análise sem resultado) e os riscos do AI Canvas viraram critérios testáveis: prompt injection (US-02 #5), isolamento entre organizações (US-01 #3) e não inventar atividades (US-06 #5).
4. **Promoveu o PRD a v1.** Cada RF aponta para a história que o implementa. Entraram RF00 (login), RF09 (selo de conteúdo gerado por IA) e RF10 (medir o tempo), e as metas ficaram marcadas como hipótese.
5. **Preparou o discovery.** Transformou as 3 premissas de maior risco da hipótese em 4 premissas testáveis, cada uma com sinal de validação. Escreveu um roteiro de 30 min baseado em fatos passados, com um teste prático: o entrevistado descreve um processo e reage ao BPMN gerado.
6. **Alinhou o repositório ao produto real.** Ao saber que o projeto é o **Fundamenta**, leu o código do front (`sistema-fundamenta-front`), trocou o nome provisório "ProcessIQ" em README, AGENTS.md e PRD e corrigiu a stack com base no `package.json` e no `.env.example`.

## Onde o agente errou

| # | Erro | Como foi detectado | Correção |
|---|---|---|---|
| 1 | **Afirmou no diário que tinha lido a atividade "Checkpoint"** do Classroom. A página carregou vazia e as instruções nunca foram lidas. | O POD questionou: "isso está realmente certo?" | Texto corrigido; regra "Fonte antes de afirmar" no AGENTS.md |
| 2 | Clicou em "Ver material" achando que era o Checkpoint, mas abriu os slides da Aula 01 | O próprio agente, ao ler a página | Navegou de novo pelo tópico Aula 02 |
| 3 | Escreveu todo o pacote com o nome provisório "ProcessIQ", sem perguntar se o produto já tinha nome ou código | O POD informou o repositório do Fundamenta | Nome trocado; regra "Confira o código real" |
| 4 | O AGENTS.md citava **shadcn/ui** como design system, mas o front real usa **MUI sem Tailwind**. O IA citado era genérico, e o real é **Gemini**. | Leitura do `package.json` e do `.env.example` do front | Stack corrigida, com ADR pendente |
| 5 | As histórias não cobrem **RACI e SIPOC**, que o "Novo com IA" do protótipo já mostra | Comparação com o README do front | Em aberto: o POD decide se entra na US-02 ou vira Could |

## Onde o POD interveio

- **Pediu o checkpoint 02** e abriu o PDF dos slides quando o agente não conseguiu ler a atividade.
- **Corrigiu o produto:** informou que o projeto é o Fundamenta e apontou o repositório do front.
- **Pegou uma afirmação falsa no diário** (erro #1). É o tipo de revisão humana que o AI-DLC exige.
- **Cobrou qualidade:** pediu que o diário tivesse nível sênior, o que levou a transformar os erros em regras do harness.
- **Discovery:** o POD trouxe uma conversa real com um gerente de projetos de TI (E1): "temos processos que precisamos mapear, e a IA precisa ter uma visão dos processos". O agente registrou a conversa como paráfrase de memória, sem completar com dados que não foram ditos.

## Decisões tomadas

| Decisão | Alternativa descartada | Motivo |
|---|---|---|
| MVP = um fluxo ponta a ponta | Uma fatia de cada módulo do protótipo | Valida a hipótese central (IA gera BPMN útil) com menos escopo |
| Login (US-01) é Must | Deixar login para depois | O isolamento por organização é requisito de LGPD do AI Canvas e precisa existir desde o início |
| Vínculos sugeridos pela IA exigem aprovação | Vincular automaticamente | Mitiga alucinação; aceitas × rejeitadas vira métrica |
| Aprovações, portal e assistente ficam fora do MVP | Construir porque já existem telas no protótipo | Ter tela pronta não é critério de prioridade; o fluxo principal é |

## Aprendizados aplicados ao AGENTS.md (v1)

Cada erro virou uma regra em [AGENTS.md › Regras adicionadas no checkpoint 02](../../AGENTS.md):

- Erro #1 → **Fonte antes de afirmar**
- Erros #3 e #4 → **Confira o código real**
- Discovery → **Evidência de discovery é humana**
- Revisão das histórias → **Critério de erro obrigatório**
- Herdado do checkpoint 01 → **Metas são hipóteses**

## Pendências para fechar o checkpoint

- [ ] Fazer pelo menos 5 entrevistas e preencher o [discovery.md](../produto/discovery.md)
- [ ] Calibrar as metas do PRD com o tempo de mapeamento relatado
- [ ] Decidir sobre RACI/SIPOC (erro #5)
- [ ] Ler as instruções e os comentários da atividade "Checkpoint" no Classroom e conferir se pedem algo além do slide 72
- [ ] PR revisado pelo Tech Lead, merge e tag `checkpoint-02`
