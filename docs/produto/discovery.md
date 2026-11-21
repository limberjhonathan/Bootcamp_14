# Evidências de discovery

> Entrega do checkpoint 02. Objetivo: testar as **premissas de maior risco** da [hipótese de valor](hipotese.md) com pessoas reais, **antes** de construir.
>
> ⚠️ **Preencher com dados reais.** Tudo marcado com `[PREENCHER]` vem das entrevistas do POD. Não invente respostas: evidência fabricada invalida a hipótese.

## Status do discovery

| Etapa | Tipo de evidência | Status |
|---|---|---|
| 1. Proto-personas | Hipóteses do POD, a validar | ✅ Feito |
| 2. Análise de concorrentes | Pesquisa secundária (desk research) | ✅ Feito |
| 3. Entrevistas com usuários | Pesquisa primária | ⏳ Pendente |
| 4. Protótipo Fundamenta como artefato de teste | Protótipo navegável (base do checkpoint 03) | ✅ Pronto para teste |

## 1. Proto-personas *(hipóteses, ainda não validadas)*

> Proto-personas registram **o que o POD acredita** sobre os usuários antes das entrevistas. As entrevistas confirmam ou derrubam cada ponto.

| | **Ana, analista de processos** *(primeira adepta)* | **Rafael, profissional de RPA** | **Marta, gestora de PME** |
|---|---|---|---|
| **Contexto** | Escritório de processos de uma empresa média ou grande; usa Bizagi ou Visio | Time de automação; recebe pedidos para "robotizar" processos | Dona ou gerente de operações; não tem equipe de BPM |
| **Tarefa principal** | Levantar processos em entrevistas e desenhar o BPMN | Entender o processo antes de automatizar | Documentar "como se faz" para treinar a equipe |
| **Dor que acreditamos existir** | Horas redesenhando diagramas a partir de anotações; documentação desatualizada logo depois | Ninguém sabe dizer quais atividades são manuais nem em que sistema acontecem | Não domina BPMN; os processos ficam na cabeça das pessoas |
| **Ganho esperado com o Fundamenta** | Rascunho do BPMN em minutos para revisar | Lista de atividades manuais com sistema e responsável | Processo documentado sem aprender a notação |
| **O que precisamos confirmar** | Tempo real gasto por processo (P3); se editaria o BPMN gerado (P2) | Se a análise de trabalho manual seria útil (P4) | Se consegue descrever o processo em texto (P1) |

## 2. Análise de concorrentes *(pesquisa secundária)*

> Comparação qualitativa feita pelo POD a partir da proposta pública de cada ferramenta. Não substitui a conversa com usuários.

| Alternativa | O que faz bem | Lacuna que o Fundamenta explora |
|---|---|---|
| **Bizagi Modeler** | Modelagem BPMN completa e gratuita, muito usada em escritórios de processos | Exige domínio da notação; o desenho é manual |
| **Camunda Modeler** | Padrão técnico de BPMN/DMN voltado à execução | Feito para desenvolvedores, não para quem só documenta |
| **SAP Signavio** | Suíte corporativa de gestão e mineração de processos | Custo e complexidade altos para empresas médias e PMEs |
| **Visio / Lucidchart / Draw.io / Miro** | Diagramas fáceis e conhecidos | Não entendem o processo: sem vínculo com pessoas e sistemas, sem análise |
| **Planilhas e documentos** | Custo zero, todo mundo sabe usar | Fragmentados, desatualizados e impossíveis de consultar |

**Leitura do POD:** as ferramentas se dividem entre *notação poderosa, mas difícil* (Bizagi, Camunda, Signavio) e *fácil, mas burra* (Visio, Miro, planilhas). O espaço do Fundamenta é **fácil de criar (descrever em texto) e inteligente depois (vínculos e análise com IA)**. As entrevistas precisam confirmar se essa lacuna dói o bastante para alguém trocar de ferramenta.

## 3. Entrevistas com usuários

### Premissas testadas

| # | Premissa (da hipótese) | Como testar na entrevista | Sinal de validação |
|---|---|---|---|
| P1 | Usuários conseguem descrever um processo em linguagem natural com detalhe suficiente para a IA gerar um BPMN útil | Pedir que a pessoa descreva, por escrito, um processo real em até 5 min | A descrição tem ≥ 3 etapas e cita ao menos um sistema ou responsável |
| P2 | Analistas confiam no BPMN gerado a ponto de editá-lo, em vez de refazê-lo | Mostrar um BPMN gerado por IA a partir da descrição dela e perguntar o que faria | Diz que editaria, e não refaria do zero |
| P3 | O mapeamento atual é lento e dói | Perguntar quanto tempo levou o último processo mapeado e com qual ferramenta | Relata horas/dias por processo e frustração |
| P4 | Encontrar trabalho manual e oportunidades de automação é difícil hoje | Perguntar como identificam o que automatizar | Processo manual, baseado em entrevistas ou planilhas |

### Roteiro de entrevista (30 min)

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

### Entrevistados

> Meta: **pelo menos 5 entrevistas**, priorizando os primeiros adeptos (analistas de processos e profissionais de RPA). Não usar nomes completos sem autorização; use iniciais.

| # | Perfil | Empresa (porte/setor) | Ferramenta atual | Data | Entrevistador |
|---|---|---|---|---|---|
| E1 | `[PREENCHER]` | `[PREENCHER]` | `[PREENCHER]` | `[PREENCHER]` | `[PREENCHER]` |
| E2 | | | | | |
| E3 | | | | | |
| E4 | | | | | |
| E5 | | | | | |

### Registro por entrevista

#### E1: `[perfil]`

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

## 4. O protótipo Fundamenta como artefato de discovery

> Fonte: repositório [sistema-fundamenta-front](https://github.com/limberjhonathan/sistema-fundamenta-front), um beta visual com dados de exemplo construído pelo PO entre out e nov/2026. Ele **não é evidência de que os usuários querem o produto**: é o instrumento para testar isso com eles.

### O que o protótipo já materializa

| Hipótese | Onde aparece no protótipo | Premissa |
|---|---|---|
| Descrever em texto é suficiente para gerar o fluxo | *Novo com IA*: etapas Básico → Estratégia → Material → Revisão | P1 |
| Documentos de apoio (POPs, manuais) melhoram a geração | *Novo com IA › Material*: upload de arquivos para a IA ler (adicionado em 16/11) | P1 |
| O usuário revisa e ajusta, em vez de redesenhar | *Modelagem*: canvas BPMN (`bpmn-js`), paleta, painel de propriedades e alternativas | P2 |
| Vincular responsáveis e sistemas dá valor ao fluxo | *Modelagem › Painel de propriedades* | P4 |
| A IA aponta gargalos e trabalho manual | *Dashboard do gestor › Análise de gargalos*; sugestões de automação na Modelagem | P4 |

### Achado de escopo

O protótipo cobre a **visão completa** (14 telas, incluindo aprovações, portal, assistente, permissões e cotas de IA). Confrontado com as premissas de maior risco, ele mostra que **só 2 telas testam diretamente a hipótese central**: *Novo com IA* e *Modelagem*. Isso fundamentou o recorte do [MoSCoW](moscow.md): as demais telas ficam como *Won't (agora)*.

### Limitação

A IA ainda não está integrada ao protótipo (dados de exemplo). Por isso, P1 e P2 só podem ser testadas de verdade quando a geração estiver ligada, ou com um BPMN preparado antes, como prevê o roteiro (bloco 4).

### Plano de teste com o protótipo *(checkpoint 03)*

| Tarefa dada ao usuário | O que medir | Premissa |
|---|---|---|
| "Crie o processo de reembolso usando o *Novo com IA*" | Tempo, abandono, qualidade da descrição | P1 |
| "Ajuste o fluxo gerado até ficar correto" | % de elementos mantidos; se tentou refazer do zero | P2 |
| "Indique quem faz cada etapa e em qual sistema" | Conclusão sem ajuda | P4 |

