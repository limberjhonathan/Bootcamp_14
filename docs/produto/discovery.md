# Evidências de discovery

> Entrega do checkpoint 02. Objetivo: testar as **premissas de maior risco** da [hipótese de valor](hipotese.md) com pessoas reais, **antes** de construir.
>
> ⚠️ **Preencher com dados reais.** Tudo marcado com `[PREENCHER]` vem das entrevistas do POD. Não invente respostas: evidência fabricada invalida a hipótese.

## Premissas testadas

| # | Premissa (da hipótese) | Como testar na entrevista | Sinal de validação |
|---|---|---|---|
| P1 | Usuários conseguem descrever um processo em linguagem natural com detalhe suficiente para a IA gerar um BPMN útil | Pedir que a pessoa descreva, por escrito, um processo real em até 5 min | A descrição tem ≥ 3 etapas e cita ao menos um sistema ou responsável |
| P2 | Analistas confiam no BPMN gerado a ponto de editá-lo, em vez de refazê-lo | Mostrar um BPMN gerado por IA a partir da descrição dela e perguntar o que faria | Diz que editaria, e não refaria do zero |
| P3 | O mapeamento atual é lento e dói | Perguntar quanto tempo levou o último processo mapeado e com qual ferramenta | Relata horas/dias por processo e frustração |
| P4 | Encontrar trabalho manual e oportunidades de automação é difícil hoje | Perguntar como identificam o que automatizar | Processo manual, baseado em entrevistas ou planilhas |

## Roteiro de entrevista (30 min)

**Abertura (2 min).** Explicar que é uma pesquisa, não uma venda. Pedir permissão para anotar. Não mostrar a solução antes do bloco 4.

**1. Contexto (5 min)**
- Qual é o seu papel? Com que frequência você mapeia ou documenta processos?
- Quais ferramentas você usa hoje (Bizagi, Camunda, Visio, Miro, planilha...)?

**2. A última vez (8 min)** *(fatos do passado, não opiniões sobre o futuro)*
- Me conte a última vez que você mapeou um processo. Qual era? Quanto tempo levou, do levantamento ao diagrama final?
- De onde vieram as informações (entrevistas, documentos, reuniões)?
- O que foi mais difícil ou demorado?
- Esse diagrama ainda está atualizado hoje? Quem usa?

**3. Automação e análise (5 min)**
- Como vocês decidem quais atividades automatizar?
- Você sabe hoje quais processos usam um determinado sistema? Como descobre?

**4. Teste da descrição (8 min)** *(testa P1 e P2)*
- "Descreva, em texto livre, um processo que você conhece bem." (cronometrar)
- Mostrar o BPMN gerado pela IA a partir do texto (gerar na hora com um LLM ou preparar antes).
- "O que você faria com esse diagrama? Editaria, refaria, descartaria? O que está errado?"

**5. Fechamento (2 min)**
- Se isso existisse, o que faria você trocar a ferramenta atual? O que te impediria?
- Conhece mais alguém que mapeia processos e toparia conversar?

## Entrevistados

> Meta: **pelo menos 5 entrevistas**, priorizando os primeiros adeptos (analistas de processos e profissionais de RPA). Não usar nomes completos sem autorização; use iniciais.

| # | Perfil | Empresa (porte/setor) | Ferramenta atual | Data | Entrevistador |
|---|---|---|---|---|---|
| E1 | `[PREENCHER]` | `[PREENCHER]` | `[PREENCHER]` | `[PREENCHER]` | `[PREENCHER]` |
| E2 | | | | | |
| E3 | | | | | |
| E4 | | | | | |
| E5 | | | | | |

## Registro por entrevista

### E1: `[perfil]`

- **Último processo mapeado:** `[PREENCHER]` · **tempo gasto:** `[PREENCHER]` · **ferramenta:** `[PREENCHER]`
- **Maior dor (nas palavras dela/dele):** "`[PREENCHER]`"
- **Como identifica automações hoje:** `[PREENCHER]`
- **Teste da descrição:** levou `[__]` min · `[__]` etapas · citou sistemas? `[sim/não]`
- **Reação ao BPMN gerado:** `[editaria / refaria / descartaria]` · o que estava errado: `[PREENCHER]`
- **Barreiras para adotar:** `[PREENCHER]`

*(copiar o bloco para E2…E5)*

## Síntese

| Premissa | E1 | E2 | E3 | E4 | E5 | Resultado |
|---|---|---|---|---|---|---|
| P1 descrição suficiente | | | | | | `[validada / invalidada / inconclusiva]` |
| P2 edita em vez de refazer | | | | | | |
| P3 mapeamento lento e doloroso | | | | | | |
| P4 achar automação é difícil | | | | | | |

**Tempo médio relatado para mapear um processo hoje:** `[PREENCHER]` → usado para calibrar a meta de "≤ 50% do tempo" do [PRD](prd.md#6-métricas-de-sucesso).

### Padrões encontrados
- `[PREENCHER]`

### Surpresas e o que mudou no produto
| Descoberta | Mudança no PRD / MoSCoW |
|---|---|
| `[PREENCHER]` | `[PREENCHER]` |

### Citações marcantes
> "`[PREENCHER]`" (E?)
