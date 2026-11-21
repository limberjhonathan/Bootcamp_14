# AGENTS.md: harness do agente *(v1)*

> Instruções para qualquer agente de código que trabalhe neste repositório (Claude Code, Copilot, Cursor, Kiro...). O arquivo evolui a cada encontro com o que o POD aprender. Dono: **Tech Lead**.

## Contexto do produto

Fundamenta é uma plataforma de gestão de processos (BPM) com IA. Antes de propor qualquer coisa, leia:

1. [docs/produto/prd.md](docs/produto/prd.md): escopo do MVP e requisitos
2. [docs/produto/moscow.md](docs/produto/moscow.md): o que é Must e o que está fora do MVP
3. [docs/produto/lean-canvas.md](docs/produto/lean-canvas.md): problema e proposta de valor
4. [docs/specs/](docs/specs/): histórias e critérios de aceite
5. [docs/adr/](docs/adr/): decisões já tomadas

## Método: AI-DLC

Todo ciclo de trabalho (bolt) segue quatro passos:

1. **Propor:** apresente um plano com o que construir e como, citando a história ou spec de origem.
2. **Aguardar aprovação:** não escreva código antes de o POD aprovar o plano.
3. **Executar:** gere o código **e os testes** correspondentes.
4. **Entregar para validação:** abra ou atualize um PR para revisão humana.

Na fase de Inception, faça perguntas quando o contexto for insuficiente. Não invente requisitos.

## Regras

- **Spec antes do código.** Toda funcionalidade tem uma história com critérios de aceite em `/docs/specs/`. Se não houver, pare e peça.
- **Rastreabilidade.** Cada teste referencia a história de origem (ex.: `// US-01`). Cada PR cita as histórias que implementa.
- **Critérios de aceite viram testes** no formato Dado/Quando/Então.
- **Escopo do MVP.** Não implemente nada marcado como fora do MVP no PRD.
- **Arquitetura.** Não crie serviços, containers ou dependências externas que não estejam no C2 (`/architecture/`). Se for necessário, proponha primeiro um ADR.
- **Design system.** Use apenas o design system definido em ADR. Não invente estilos.
- **Dependências.** Não adicione bibliotecas sem justificar no PR.
- **WIP.** No máximo 2 PRs abertos. Não gere trabalho novo enquanto houver PRs aguardando revisão.

### Regras adicionadas no checkpoint 02
- **Fonte antes de afirmar.** Só registre no diário ou nos documentos o que você leu de fato. Se uma fonte não carregou (página, PDF, atividade), escreva isso de forma explícita.
- **Evidência de discovery é humana.** O agente prepara o roteiro e a estrutura, mas nunca preenche entrevistas, citações ou números de discovery.
- **Confira o código real.** Antes de descrever a stack ou o produto, leia o repositório do front (`sistema-fundamenta-front`), não documentos antigos.
- **Critério de erro obrigatório.** Toda história tem pelo menos um critério de caminho de erro ou borda, além do caminho feliz.
- **Metas são hipóteses.** Metas numéricas sem dado de discovery ficam marcadas como hipótese.

## Limites (nunca faça)

- Nunca comite segredos, chaves de API ou arquivos `.env`. Use variáveis de ambiente.
- Nunca faça push direto na `main` nem force-push.
- Nunca desative, pule ou apague testes para fazer o CI passar.
- Nunca envie dados reais de clientes para serviços externos em testes. Use dados fictícios.

## Stack

> O front-end já existe em [sistema-fundamenta-front](https://github.com/limberjhonathan/sistema-fundamenta-front). As escolhas abaixo ainda precisam ser oficializadas em ADRs (design system no checkpoint 03, demais até o checkpoint 04).

| Camada | Escolha |
|---|---|
| Frontend | Next.js 16 (App Router) + React 19 + TypeScript |
| Editor BPMN | `bpmn-js` |
| Design system | MUI (Material UI) + Emotion, sem Tailwind *(ADR no checkpoint 03)* |
| Estado e dados | Zustand (estado local) + TanStack Query + Axios (API) |
| Formulários | Formik + Yup |
| Backend | *a definir* |
| Banco | *a definir* |
| IA | Google Gemini via API (`GEMINI_MODEL` com modelos de fallback) + validação do XML BPMN gerado |
| Arquitetura | LikeC4 (C1/C2) em `/architecture/` |
| CI/CD | GitHub Actions: testes + eval |

**Atenção (Next.js 16):** a versão tem mudanças incompatíveis com versões anteriores. Antes de escrever código no front, consulte `node_modules/next/dist/docs/`.

## Estrutura de pastas

Siga a estrutura descrita no [README](README.md#estrutura-do-repositório). O código do MVP fica em `/src/`, os evals da IA em `/evals/` e o protótipo em `/prototype/`.

## Diário agêntico

Ao final de cada sessão relevante, o POD registra em `/docs/diario/` o que o agente fez, onde errou e onde houve intervenção humana.
