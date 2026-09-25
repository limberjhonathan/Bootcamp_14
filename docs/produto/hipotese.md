# Hipótese de valor

> **Acreditamos que** uma plataforma inteligente de gestão e mapeamento de processos, que combine BPMN, IA, documentação, arquitetura, pessoas, sistemas, riscos e automações,
> **para** empresas e profissionais responsáveis por processos e transformação digital,
> **vai gerar** redução do tempo necessário para mapear e manter processos, maior visibilidade operacional e identificação mais rápida de oportunidades de melhoria e automação.
>
> **Saberemos que é verdade quando** o tempo médio para documentar um processo diminuir significativamente, o número de processos mantidos na plataforma crescer e os usuários identificarem oportunidades reais de melhoria e automação através da plataforma.

## Como vamos testar

O protótipo da Aula 03 testa esta hipótese com usuários reais. O ponto central é o recorte que depende da IA:

| Métrica | Como medir no protótipo/MVP | Sinal de validação *(meta inicial, a calibrar no discovery)* |
|---|---|---|
| Tempo para documentar um processo | Cronometrar o mesmo processo feito com a ferramenta atual do usuário e com a plataforma | Redução de pelo menos 50% |
| Qualidade do BPMN gerado pela IA | Fração de elementos gerados que o usuário mantém sem editar | Pelo menos 70% mantidos |
| Oportunidades identificadas | Sugestões de melhoria ou automação que o usuário considera reais | Pelo menos 1 oportunidade relevante por processo |

## Premissas de maior risco

1. Usuários conseguem descrever um processo em linguagem natural com detalhe suficiente para a IA gerar um BPMN útil.
2. Analistas de processos confiam no BPMN gerado a ponto de editá-lo, em vez de refazê-lo do zero.
3. O valor da base conectada (sistemas, pessoas, riscos) aparece já com poucos processos cadastrados.
