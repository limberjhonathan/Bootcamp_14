# Fundamenta

**Sua organização, potencializada por IA.**

> Plataforma de **gestão de processos (BPM) com inteligência artificial**. O Fundamenta ajuda empresas a mapear, documentar, aprovar e consultar seus processos em um só lugar, com uma IA que cria o fluxo BPMN a partir de uma descrição em texto, aponta trabalho manual e gargalos e responde dúvidas dos colaboradores.

Projeto do **Bootcamp · Software Engineering Project** do MBA em Engenharia de Software da Faculdade Impacta. O projeto é desenvolvido com o método **AI-DLC**: o agente escreve o código, e o POD especifica, revisa e responde por ele.

| | |
|---|---|
| **URL do MVP** | *a definir (checkpoint 05)* |
| **Checkpoint atual** | `checkpoint-02` · Produto 🟡 em andamento |
| **Hipótese de valor** | [docs/produto/hipotese.md](docs/produto/hipotese.md) |
| **Front-end (protótipo)** | [limberjhonathan/sistema-fundamenta-front](https://github.com/limberjhonathan/sistema-fundamenta-front) · Next.js 16 + MUI + bpmn-js, beta visual com dados de exemplo |

---

## POD

| Papel | Membro | Responde por |
|---|---|---|
| **Product Owner** | Limber Jhonathan | PRD, histórias e validação com usuários |
| **Tech Lead** | Vinicius Franco | Harness do agente ([AGENTS.md](AGENTS.md)) e arquitetura C1/C2 |
| **Quality & Ops** | Limber Jhonathan e Vinicius Franco | CI, testes, deploy e métricas |

Todos operam agentes e revisam PRs. O papel define quem responde por cada artefato.

---

## O problema

Empresas documentam seus processos de forma fragmentada, em documentos, planilhas, apresentações e ferramentas BPMN diferentes. As três principais dores:

1. **O mapeamento depende de especialistas em BPMN.** Criar e manter fluxos é lento e difícil para quem não domina a notação.
2. **O processo desenhado vira documentação parada.** Não há conexão entre processo, pessoas, sistemas, documentos, riscos, indicadores e automações.
3. **A documentação se afasta da realidade.** O processo muda e o documento não acompanha. Encontrar gargalos, tarefas manuais e oportunidades de automação exige análise manual.

**Alternativas atuais:** Camunda Modeler, Bizagi, SAP Signavio, Bpanda, Visio, Lucidchart, Miro, Draw.io, planilhas e documentos.

## A solução

Centralizar o ciclo de vida dos processos, da criação à consulta, e usar IA para acelerar o trabalho:

- **Criar** processos descrevendo-os em linguagem natural: a IA estrutura o fluxo em BPMN 2.0, identificando papéis (RACI) e entradas/saídas (SIPOC).
- **Modelar e revisar** os fluxos em um editor visual, com responsáveis, sistemas, documentação e sugestões de automação e de conformidade.
- **Aprovar** mudanças em uma fila com prioridade e histórico.
- **Consultar** tudo pelo portal de conhecimento, pela busca ou perguntando ao assistente, que cita as fontes.
- **Acompanhar** indicadores de eficiência, conformidade e uso, com a IA apontando gargalos e processos desatualizados.

### Para quem

| Perfil | O que faz no Fundamenta |
|---|---|
| **Gestor / analista de processos** *(primeiro adepto)* | Mapeia processos com IA, acompanha KPIs, aprova alterações e identifica gargalos |
| **Colaborador** | Encontra procedimentos, tira dúvidas com o assistente e cumpre suas atividades |
| **Administrador** | Gerencia usuários, departamentos, permissões e o consumo de IA |

### Visão do produto × recorte do MVP

O protótipo do front já mostra a visão completa (dashboard, processos, Novo com IA, modelagem, aprovações, portal, assistente, busca e administração). O **MVP do bootcamp** entrega só o fluxo principal, priorizado no [MoSCoW](docs/produto/moscow.md):

> **Descrever processo → IA gera BPMN → usuário revisa e ajusta → vincula responsáveis e sistemas → IA aponta trabalho manual e automações.**

Aprovações, portal, assistente (chat), macroprocessos, permissões e cotas de IA ficam para depois do MVP.

### Onde a IA entra (e por que não é enfeite)

Tire a IA e o Fundamenta vira mais um editor BPMN, que é exatamente a alternativa que já existe. A proposta de valor depende da IA para **transformar informação não estruturada em processo estruturado** e para **analisar os processos usando o contexto da organização**. A IA aparece **dentro do fluxo** (gera e sugere o diagrama no editor) e como **conversa** para perguntas abertas sobre a base de processos.

A justificativa detalhada fica no [AI Canvas](docs/produto/ai-canvas.md).

---

## Estrutura do repositório

| Caminho | Conteúdo |
|---|---|
| [`/README.md`](README.md) | Startup, POD, papéis e URL do MVP |
| [`/AGENTS.md`](AGENTS.md) | Harness do agente: regras, stack e limites |
| [`/docs/produto/`](docs/produto/) | Lean Canvas, hipótese, AI Canvas, PRD e evidências de discovery |
| [`/docs/specs/`](docs/specs/) | Histórias de usuário e critérios de aceite (Dado/Quando/Então) |
| [`/docs/adr/`](docs/adr/) | Decisões de arquitetura (ADRs) |
| [`/docs/diario/`](docs/diario/) | Diário agêntico, um arquivo por checkpoint |
| [`/docs/pitch/`](docs/pitch/) | `pitch.md` (fonte), `pitch.pdf` e roteiro da demo |
| [`/architecture/`](architecture/) | Modelo LikeC4 (C1 e C2) |
| [`/prototype/`](prototype/) | Telas HTML do protótipo |
| [`/evals/`](evals/) | Casos de avaliação da IA e script da taxa de acerto |
| [`/src/`](src/) | Código do MVP |
| [`/.github/`](.github/) | CI com testes e eval |

## Artefatos de produto

- [Lean Canvas](docs/produto/lean-canvas.md)
- [Hipótese de valor](docs/produto/hipotese.md)
- [PRD v1](docs/produto/prd.md)
- [AI Canvas](docs/produto/ai-canvas.md)
- [MoSCoW do MVP](docs/produto/moscow.md)
- [Evidências de discovery](docs/produto/discovery.md)
- [Histórias e critérios de aceite](docs/specs/historias-mvp.md)

---

## Regras de trabalho

- A `main` é protegida: o merge só entra por PR, com revisão de outro membro do POD e CI verde.
- No máximo **2 PRs abertos** ao mesmo tempo.
- Cada checkpoint recebe uma tag, de `checkpoint-01` a `checkpoint-06`, criada até 22h40 do encontro.
- O diário agêntico é versionado, com um arquivo por checkpoint em `/docs/diario/`.
- Em aula o POD trabalha em mob. Entre as aulas o trabalho segue assíncrono, via PRs.

## Checkpoints

| # | Encontro | Entrega mínima | Status |
|---|---|---|---|
| 01 | Times e desafio | POD e papéis no README, Lean Canvas, hipótese, esqueleto do PRD, AGENTS.md v0 | ✅ concluído |
| 02 | Produto | Evidências de discovery, AI Canvas, MoSCoW do MVP, histórias com critérios de aceite, PRD v1 | 🟡 |
| 03 | Protótipo | Telas HTML testadas com 2 ou mais usuários, ADR do design system, diário #1 | ⚪ |
| 04 | Design C1/C2 | C1 e C2 em LikeC4, ADRs, walking skeleton no ar com deploy e CI | ⚪ |
| 05 | MVP | URL pública, fluxo principal ponta a ponta, testes e eval no CI, rastreabilidade, diário #2 | ⚪ |
| 06 | Pitch | Pitch ao vivo com demo e material em `/docs/pitch/` | ⚪ |
