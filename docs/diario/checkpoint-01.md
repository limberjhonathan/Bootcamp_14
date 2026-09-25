# Diário agêntico: checkpoint 01

**Data:** 2026-09-24 · **Encontro:** 01, Times e desafio · **Agente:** Claude Code

## O que o agente fez
- Leu os slides da Aula 01 e gerou a estrutura do repositório conforme o esqueleto do bootcamp (slide 70).
- Organizou o Lean Canvas na ordem problema → segmentos → proposta de valor, condensando o problema nas 3 principais dores.
- Rascunhou a hipótese de valor, o PRD v0 com os 6 pilares, o AGENTS.md v0 e o template de ADR.
- A pedido do POD, preencheu o AI Canvas completo: por que IA, dados, métricas, plano de eval e riscos.
- Fez os commits, criou a tag `checkpoint-01` e enviou para o GitHub.
- Revisou o repositório contra a lista do checkpoint 01 e apontou as lacunas.

## Onde o agente errou
- Não conseguiu ler o PDF dos slides diretamente, porque faltava uma dependência (`pdftoppm`). Contornou extraindo o texto com `pdftotext`.
- Deixou o AI Canvas só como rascunho e os campos do POD como placeholders, o que exigiu uma segunda rodada para completar.
- Definiu metas numéricas (tempo −50%, 70% do BPMN mantido, eval 17/20) sem dados de discovery. Elas precisam ser calibradas.

## Onde o POD interveio
- Forneceu o conteúdo do Lean Canvas e a hipótese de valor.
- Definiu os papéis e preencheu os membros do POD no README.
- Pediu o preenchimento completo do AI Canvas e a revisão do que faltava.
- Validou o recorte do MVP em um único fluxo principal: descrever → gerar BPMN → vincular → analisar.

## Aprendizados para o AGENTS.md
- O agente deve checar as entregas do checkpoint (slides 72–73 e 84) antes de dar a tarefa como concluída.
- Metas numéricas sugeridas pelo agente precisam ser marcadas como hipótese até serem validadas no discovery.
- O PDF da aula não é versionado. As referências aos slides ficam citadas nos documentos.
