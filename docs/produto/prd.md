# PRD: Fundamenta *(v1)*

> **Status:** v1, checkpoint 02. Escopo do MVP priorizado no [MoSCoW](moscow.md); histórias e critérios de aceite completos em [/docs/specs/historias-mvp.md](../specs/historias-mvp.md); evidências em [discovery.md](discovery.md); estratégia de IA no [AI Canvas](ai-canvas.md).
>
> **Histórico:** v0 (checkpoint 01, esqueleto dos 6 pilares) → v1 (checkpoint 02, MoSCoW, histórias e critérios de aceite).
>
> O PRD é a entrada do agente: quanto mais específico, melhor o que ele constrói.

## 1. Visão e objetivo

Permitir que qualquer pessoa responsável por um processo o **documente em minutos, descrevendo-o em linguagem natural**, e o transforme em um BPMN conectado a pessoas e sistemas, que a IA consegue analisar para apontar trabalho manual e oportunidades de automação.

**Problema resolvido:** mapear processos é lento, depende de especialistas em BPMN e gera documentação parada, desconectada da operação.

### Recorte do MVP (skate, não roda)

O MVP entrega **um fluxo principal completo**, e não uma fatia de cada módulo do Lean Canvas:

> **Descrever processo → IA gera BPMN → usuário revisa e ajusta → vincula responsáveis e sistemas às atividades → IA analisa e aponta atividades manuais e oportunidades de automação.**

Ficam **fora do MVP** (ver *Won't have* no [MoSCoW](moscow.md)): vídeos e reuniões como entrada, riscos e controles, KPIs, AS-IS × TO-BE, aprovação e publicação, SSO, planos pagos e integrações.

## 2. Público-alvo

| Persona | Dor | Necessidade |
|---|---|---|
| **Analista de processos** (primeiro adepto) | Gasta horas desenhando BPMN em Camunda, Bizagi ou Visio a partir de entrevistas | Rascunho rápido do fluxo para revisar, em vez de desenhar do zero |
| **Profissional de RPA** | Precisa entender o processo antes de automatizar e não sabe onde está o trabalho manual | Mapa das atividades manuais e dos sistemas envolvidos |
| **Gestor de PME** | Não tem equipe de BPM e não domina a notação | Documentar o processo sem aprender BPMN |

## 3. Requisitos funcionais

| ID | Requisito | Prioridade | Histórias |
|---|---|---|---|
| RF00 | Entrar com uma conta, com dados isolados por organização | Must | US-01 |
| RF01 | Criar um processo a partir de uma descrição em linguagem natural, com a IA gerando um BPMN 2.0 | Must | US-02 |
| RF02 | Visualizar, editar e salvar o BPMN gerado em um editor visual | Must | US-03 |
| RF03 | Cadastrar pessoas/áreas e sistemas e vinculá-los a cada atividade, com sugestões da IA aprovadas pelo usuário | Must | US-04, US-05 |
| RF04 | Pedir à IA uma análise do processo, com atividades manuais e sugestões de automação justificadas | Must | US-06 |
| RF05 | Listar os processos cadastrados e buscar por processo, atividade ou sistema | Should | US-07 |
| RF06 | Exportar o processo em BPMN/XML | Should | US-08 |
| RF09 | Sinalizar conteúdo gerado por IA até ser revisado | Should | US-09 |
| RF10 | Registrar o tempo para documentar um processo | Should | US-10 |
| RF07 | Explicar o BPMN em linguagem simples | Could | — |
| RF08 | Fazer perguntas em linguagem natural sobre a base de processos | Could | — |

## 4. Requisitos não funcionais

- **Desempenho:** a geração do BPMN pela IA responde em até 30 s e mostra o progresso ao usuário; as demais telas carregam em menos de 2 s.
- **Segurança e LGPD:** nenhum segredo no repositório; descrições de processo não são usadas para treinar modelos de terceiros; dados isolados por organização.
- **Robustez da IA:** o BPMN gerado é sempre XML BPMN 2.0 válido, e a IA recusa pedidos fora do domínio de processos (casos adversariais cobertos no eval).
- **Usabilidade:** um usuário sem conhecimento de BPMN consegue gerar e ajustar um processo sem ajuda.
- **Interoperabilidade:** o BPMN exportado abre no Camunda Modeler.

## 5. Critérios de aceite *(resumo; a lista completa está em [historias-mvp.md](../specs/historias-mvp.md))*

**RF01: gerar processo com IA**
- **Dado** que estou logado e na tela de novo processo,
  **quando** descrevo o processo "Cadastro de parceiro" com pelo menos 3 etapas e clico em *Gerar*,
  **então** vejo um diagrama BPMN com evento de início, as atividades descritas e evento de fim, em até 30 s.

**RF03: vincular sistema**
- **Dado** um processo com a atividade "Validar CPF",
  **quando** vinculo o sistema "DataBrasil" a essa atividade,
  **então** o processo aparece na busca por "DataBrasil".

**RF04: análise de trabalho manual**
- **Dado** um processo com atividades marcadas como manuais ou que usam planilhas,
  **quando** peço a análise à IA,
  **então** recebo a lista dessas atividades, cada uma com pelo menos uma sugestão de automação.

## 6. Métricas de sucesso

> As metas abaixo são **hipóteses** até serem calibradas com os dados de [discovery](discovery.md).

| Métrica | Tipo | Meta inicial |
|---|---|---|
| **Tempo médio para documentar um processo** *(métrica principal, instrumentada no MVP)* | Produto | ≤ 50% do tempo com a ferramenta atual |
| % de elementos do BPMN gerado mantidos pelo usuário | IA | ≥ 70% |
| Taxa de acerto do eval da IA | IA | ≥ 17 de 20 casos |
| Sugestões de automação aceitas pelo usuário | IA | ≥ 1 por processo analisado |
| Processos criados por usuário ativo | Produto | a definir no discovery |
