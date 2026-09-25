# ProcessIQ *(nome provisório)*

> Plataforma de **Process Intelligence + BPM + IA** que transforma informações dispersas sobre processos em uma base inteligente e conectada: BPMN, pessoas, sistemas, documentos, riscos, indicadores e automações em um único ambiente.

Projeto do **Bootcamp · Software Engineering Project** do MBA em Engenharia de Software da Faculdade Impacta. O projeto é desenvolvido com o método **AI-DLC**: o agente escreve o código, e o POD especifica, revisa e responde por ele.

| | |
|---|---|
| **URL do MVP** | *a definir (checkpoint 05)* |
| **Checkpoint atual** | `checkpoint-01` · Times e desafio ✅ concluído |
| **Hipótese de valor** | [docs/produto/hipotese.md](docs/produto/hipotese.md) |

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

- **Modelagem BPMN 2.0** com editor visual, modo simplificado, versionamento, comparação AS-IS × TO-BE, aprovação e publicação.
- **IA para processos:** gera o BPMN a partir de linguagem natural, reuniões, entrevistas ou vídeos; aponta gargalos, redundâncias e tarefas manuais automatizáveis; explica o processo em linguagem simples e responde perguntas sobre ele.
- **Base de conhecimento conectada:** Empresa → Área → Processo → Subprocesso → Atividade, ligada a pessoas, sistemas, documentos, riscos, KPIs e automações.
- **Busca inteligente** sobre toda a base, por exemplo: *"Quais processos utilizam o Dynamics?"*

### Onde a IA entra (e por que não é enfeite)

Tire a IA e o produto vira mais um editor BPMN, que é exatamente a alternativa que já existe. A proposta de valor depende da IA para **transformar informação não estruturada em processo estruturado** e para **analisar os processos usando o contexto da organização**. A IA aparece **dentro do fluxo** (gera e sugere o diagrama no editor) e como **conversa** para perguntas abertas sobre a base de processos.

A justificativa detalhada fica no [AI Canvas](docs/produto/ai-canvas.md), que é entregue no checkpoint 02.

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
- [PRD](docs/produto/prd.md)
- [AI Canvas](docs/produto/ai-canvas.md) *(checkpoint 02)*

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
| 02 | Produto | Evidências de discovery, AI Canvas, MoSCoW do MVP, histórias com critérios de aceite, PRD v1 | ⚪ |
| 03 | Protótipo | Telas HTML testadas com 2 ou mais usuários, ADR do design system, diário #1 | ⚪ |
| 04 | Design C1/C2 | C1 e C2 em LikeC4, ADRs, walking skeleton no ar com deploy e CI | ⚪ |
| 05 | MVP | URL pública, fluxo principal ponta a ponta, testes e eval no CI, rastreabilidade, diário #2 | ⚪ |
| 06 | Pitch | Pitch ao vivo com demo e material em `/docs/pitch/` | ⚪ |
