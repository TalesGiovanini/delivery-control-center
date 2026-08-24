# Modelo da fonte Excel

## Abas mínimas

### Backlog editável

Fonte de verdade por atividade. O cabeçalho precisa permanecer estável e a tabela deve possuir nome definido.

Campos recomendados:

| Grupo | Campos |
|---|---|
| Identificação | ID, macroetapa, linha do plano, pilar, fase/onda |
| Planejamento | atividade, objetivo, semana/data de início e fim |
| Responsabilidade | responsável, apoio, executor técnico |
| Controle | dependências, entregável, status, prioridade, percentual |
| Operação | última atualização, situação atual, próxima ação, impedimentos/riscos |
| Evidência | evidência/link, observações, entrega em repositório oficial, referência |
| Auditoria | atualizado por, data/hora da atualização |

### Roadmap

Visão temporal agregada por workstream. Deve preservar responsáveis e janelas aprovadas. Não deve ser recalculado apenas porque o texto do backlog mudou.

### Visão executiva

Pode ser calculada no board ou mantida no workbook. Deve mostrar volume, status, atraso, prioridade, risco e avanço, sempre com regra de cálculo documentada.

## Regras de qualidade

- ID único e imutável;
- datas como valores de data, não texto;
- percentual entre 0 e 100%;
- status controlado por lista;
- responsável separado de “atualizado por”;
- evidência separada de observação;
- ausência representada como pendência, nunca preenchida por inferência;
- fórmulas sem `#REF!`, `#DIV/0!` ou erros equivalentes;
- tabela e cabeçalhos preservados para o fluxo automatizado.

## Critério de publicação

Uma alteração está comprovada quando:

1. o arquivo correto foi aberto pelo link oficial;
2. os valores atuais foram lidos;
3. somente as células autorizadas foram alteradas;
4. o salvamento foi confirmado;
5. o mesmo arquivo foi reaberto;
6. os valores foram relidos;
7. a ingestão do Power Automate foi aceita;
8. o board consumiu a versão posterior.
