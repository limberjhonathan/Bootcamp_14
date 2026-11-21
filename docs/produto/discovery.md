# Evidências de discovery

> Entrega do checkpoint 02. Objetivo: testar as **premissas de maior risco** da [hipótese de valor](hipotese.md) com pessoas reais, **antes** de construir.
>
> **Transparência:** cada fonte está rotulada como real (🟢) ou simulada com IA (🧪). Só as fontes reais contam como validação.

## Status do discovery

| Etapa | Tipo de evidência | Status |
|---|---|---|
| 1. Proto-personas | Hipóteses do POD, a validar | ✅ Feito |
| 2. Análise de concorrentes | Pesquisa secundária (desk research) | ✅ Feito |
| 3. Entrevistas com usuários | 1 conversa real (E1) + 3 simuladas com IA (S1–S3) | 🟡 Parcial: validação com usuários no checkpoint 03 |
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

> Duas fontes, separadas de propósito: **E1 é uma conversa real**, informal e reconstruída de memória. **S1 a S3 são entrevistas simuladas com IA**, com personas sintéticas construídas a partir das proto-personas e das regras de negócio do protótipo. As simulações **não são evidência de usuário real**: servem para afiar o roteiro e as perguntas do checkpoint 03.

| # | Tipo | Perfil | Empresa | Data | Entrevistadores |
|---|---|---|---|---|---|
| **E1** | 🟢 Real (conversa informal) | Gerente de projetos, setor de TI | Confidencial | Semana de 09/11/2026 | Limber Jhonathan e Vinicius Franco |
| S1 | 🧪 Simulada (IA) | Analista de processos (persona Ana) | Fictícia: empresa de serviços, ~800 pessoas | 20/11/2026 | Claude Code |
| S2 | 🧪 Simulada (IA) | Desenvolvedor de RPA (persona Rafael) | Fictícia: área de automação de um banco médio | 20/11/2026 | Claude Code |
| S3 | 🧪 Simulada (IA) | Gestora de PME (persona Marta) | Fictícia: distribuidora com 40 pessoas | 20/11/2026 | Claude Code |

### E1: Gerente de projetos de TI *(conversa real)*

> **Formato:** conversa informal, sem gravação nem roteiro estruturado. Registro feito pelo POD **de memória**. Os pontos que não foram abordados estão marcados como tal, em vez de preenchidos.

- **O que ele disse (paráfrase do POD):**
  - A área **tem processos que precisam ser mapeados**: existe uma demanda real e pendente de mapeamento.
  - Para ajudar, **a IA precisa ter uma visão dos processos**, ou seja, entender o contexto e o conjunto dos processos, não só gerar um desenho isolado.
- **Tempo para mapear / ferramenta atual:** não abordado.
- **Teste da descrição (bloco 4 do roteiro):** não realizado.

**Leitura do POD:**
- Reforça **P3** (a dor existe): há um passivo de processos a mapear.
- Reforça a **proposta de valor da base conectada**: o valor esperado da IA não é só gerar BPMN, é *ter visão* do conjunto. Isso sustenta os vínculos (US-05), a análise (US-06) e a busca (US-07), e é um sinal a favor de subir a prioridade da busca e da pergunta sobre a base (RF08).
- Não traz dado para **P1** nem para **P2**.

### S1: Analista de processos *(simulada com IA)*

- **Último processo mapeado:** onboarding de fornecedores, com 4 entrevistas com as áreas e cerca de 2 dias até o fluxo aprovado, no Bizagi.
- **Maior dor:** "Desenhar é rápido. O que demora é transformar as anotações das entrevistas em fluxo e depois manter atualizado."
- **Automação hoje:** levantada caso a caso, quando alguém reclama.
- **Reação a um BPMN gerado:** editaria, desde que dê para corrigir o fluxo com facilidade e a IA não invente etapas.
- **Barreira:** confidencialidade, porque não colaria documentos internos numa IA sem garantia sobre os dados.

### S2: Desenvolvedor de RPA *(simulada com IA)*

- **Contexto:** recebe pedidos de "robotizar" sem processo documentado e passa a primeira semana descobrindo o fluxo real.
- **Maior dor:** "Ninguém sabe dizer em qual sistema cada etapa acontece."
- **Reação:** a lista de atividades manuais com sistema e responsável é o que mais interessa; o diagrama vem depois.
- **Barreira:** desconfia de sugestões de automação sem justificativa.

### S3: Gestora de PME *(simulada com IA)*

- **Contexto:** os processos ficam na cabeça de duas pessoas-chave.
- **Maior dor:** "Quando alguém sai, o processo vai junto."
- **Reação:** não sabe o que é BPMN; quer descrever do jeito dela e ver um passo a passo.
- **Barreira:** preço e tempo para aprender a ferramenta.

## Síntese

| Premissa | E1 (real) | S1–S3 (simuladas) | Resultado |
|---|---|---|---|
| P1 descrição suficiente | Não abordado | Sinal positivo | ⚪ **Inconclusiva**: testar no checkpoint 03 com o protótipo |
| P2 edita em vez de refazer | Não abordado | Sinal positivo, com ressalva de "não inventar etapas" | ⚪ **Inconclusiva** |
| P3 mapeamento é uma dor real | ✅ Há processos pendentes de mapeamento | Sinal positivo | 🟢 **Indício real** (1 fonte) |
| P4 achar automação é difícil | Não abordado | Sinal positivo (S2) | ⚪ **Inconclusiva** |

**Tempo médio para mapear um processo hoje:** sem dado real. A meta "≤ 50% do tempo" do [PRD](prd.md#6-métricas-de-sucesso) continua como hipótese.

### Padrões encontrados
- **Visão do conjunto > diagrama isolado.** A fala real do E1 ("a IA precisa ter uma visão dos processos") é a evidência mais forte do ciclo e aponta para o diferencial da base conectada, não só para a geração de BPMN.
- **Confiança e confidencialidade** aparecem como barreira nas simulações. Isso já está mitigado no [AI Canvas](ai-canvas.md) e precisa ser perguntado a usuários reais.

### O que mudou no produto
| Descoberta | Mudança |
|---|---|
| E1: a IA precisa de visão do conjunto dos processos | Vínculos (US-05) e análise (US-06) seguem como Must; **busca (US-07) é a primeira candidata a subir** se houver folga |
| Simulações: medo de a IA inventar etapas | Mantidos os critérios US-02 #1 e US-06 #5 e a métrica "etapas inventadas = 0" no eval |

### Citações
> "Temos processos que precisamos mapear, e a IA precisa ter uma visão dos processos." *(E1, gerente de projetos de TI, paráfrase do POD a partir de conversa informal)*

### Próximos passos (checkpoint 03)
- [ ] Retomar a conversa com o E1 usando o roteiro curto (tempo, ferramenta, teste da descrição)
- [ ] Testar o protótipo com pelo menos 2 usuários reais, conforme a seção 4
- [ ] Substituir as simulações S1–S3 por entrevistas reais

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

