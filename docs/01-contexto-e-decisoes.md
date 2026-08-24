# Contexto e decisões de construção

## Ponto de partida

A gestão existia em uma planilha compartilhada com backlog, roadmap e campos de atualização. A planilha era adequada para edição, mas a leitura executiva, a consulta por processo, o histórico colaborativo e a emissão de relatórios exigiam uma camada adicional.

## Decisões adotadas

### Uma fonte central

O workbook compartilhado permanece como fonte operacional. O board consome a versão sincronizada e não mantém uma cópia editável concorrente do backlog.

### Correlação por ID

Cada atividade recebe ID estável. Esse ID relaciona backlog, roadmap, relatório individual, evidência, risco e atualização.

### Separação de estados

O modelo distingue:

- análise realizada;
- documento produzido;
- aceite documental;
- configuração ou implementação;
- evidência técnica;
- validação funcional;
- conclusão.

Essa separação evita transformar “entregável concluído” em “controle implantado”.

### Atualização controlada

Antes de gravar, os valores vigentes são lidos. Depois da gravação, o workbook é salvo, fechado, reaberto e relido. A sincronização e a renderização no board são controles posteriores.

### Roadmap protegido

O roadmap representa janela, workstream, responsável e resultado esperado. Ele só muda quando há decisão ou evidência de replanejamento. Atualizações descritivas no backlog não alteram datas automaticamente.
