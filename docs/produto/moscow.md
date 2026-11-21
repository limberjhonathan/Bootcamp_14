# MoSCoW do MVP

> Priorização oficial do MVP (checkpoint 02). Fonte: [PRD](prd.md) e [AI Canvas](ai-canvas.md). As histórias detalhadas, com critérios de aceite, ficam em [/docs/specs/historias-mvp.md](../specs/historias-mvp.md).
>
> **Regra do recorte:** o MVP entrega **um fluxo principal ponta a ponta** (skate, não roda):
> **descrever processo → IA gera BPMN → usuário revisa e ajusta → vincula responsáveis e sistemas → IA aponta trabalho manual e automações.**
> Tudo que é **Must** existe para esse fluxo funcionar. Se um item não é necessário para ele, não é Must.

## Must have: sem isso não há MVP

| ID | Item | História | RF |
|---|---|---|---|
| M1 | Entrar na plataforma com uma conta, com os dados isolados por organização | US-01 | — (RNF segurança) |
| M2 | Descrever um processo em linguagem natural e a IA gerar um BPMN 2.0 válido | US-02 | RF01 |
| M3 | Visualizar e editar o BPMN gerado no editor visual e salvar o processo | US-03 | RF02 |
| M4 | Cadastrar pessoas/áreas e sistemas da organização | US-04 | RF03 |
| M5 | Vincular responsável e sistema a cada atividade, com sugestões da IA que o usuário aprova ou rejeita | US-05 | RF03 |
| M6 | Pedir à IA a análise do processo: atividades manuais e sugestões de automação justificadas | US-06 | RF04 |
| M7 | Recusa de pedidos fora do domínio de processos e validação do XML antes de exibir | US-02 (critérios) | RNF robustez da IA |

## Should have: importante, entra se o Must estiver pronto

| ID | Item | História | RF |
|---|---|---|---|
| S1 | Listar os processos e buscar por processo, atividade ou sistema ("Quais processos usam o Dynamics?") | US-07 | RF05 |
| S2 | Exportar o processo em BPMN/XML compatível com o Camunda Modeler | US-08 | RF06 |
| S3 | Marcar visualmente o conteúdo gerado por IA até o usuário revisá-lo | US-09 | RNF / risco "confiança excessiva" |
| S4 | Instrumentar o tempo para documentar um processo (métrica principal) | US-10 | Métricas |

## Could have: desejável, só se sobrar tempo

| ID | Item | RF |
|---|---|---|
| C1 | Explicar o BPMN em linguagem simples | RF07 |
| C2 | Perguntas em linguagem natural sobre a base de processos (chat) | RF08 |
| C3 | Importar um BPMN/XML existente | — |
| C4 | Templates de processos prontos | — |

## Won't have (agora): fora do MVP, explicitamente

| Item | Por que fica fora |
|---|---|
| Reuniões, entrevistas e vídeos como entrada (multimodal) | Custo e complexidade altos; texto já valida a hipótese |
| Upload de documentos e RAG | Depende do fluxo principal validado |
| Riscos e controles | Módulo independente, não faz parte do fluxo principal |
| KPIs e indicadores por processo | Idem |
| Comparação AS-IS × TO-BE e versionamento | Exige histórico de versões |
| Aprovação e publicação de processos | Governança é valor Enterprise |
| Catálogo de automações | Depende da análise (M6) estar validada |
| SSO, permissões avançadas, auditoria | Enterprise |
| Planos pagos, cobrança e integrações (Dynamics, Camunda etc.) | Fora do escopo do bootcamp |

## Critério de corte

Se o prazo apertar, cortar nesta ordem: **Could → S4 → S3 → S2 → S1**. Nenhum Must é cortado; se um Must estiver em risco, o POD reduz o escopo **dentro** dele (ex.: M4 com cadastro mínimo de nome, sem hierarquia de áreas).
