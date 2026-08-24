# Power Automate

## Objetivo

Transportar a versão vigente do workbook compartilhado até o endpoint do board sem transformar o fluxo em fonte de regras de negócio.

## Sequência do fluxo

1. Gatilho recorrente ou por alteração de arquivo.
2. Localização do item pelo caminho canônico.
3. Leitura do conteúdo binário.
4. Obtenção do nome e do autor da última modificação, quando disponível.
5. Chamada HTTP autenticada para o endpoint de sincronização.
6. Registro do status, duração e identificador da execução.
7. Tratamento de falha com nova tentativa controlada e alerta.

## Contrato HTTP

```text
POST /api/power-automate/sync
Authorization: Bearer <secret>
Content-Type: application/vnd.openxmlformats-officedocument.spreadsheetml.sheet
X-File-Name: <nome-do-arquivo.xlsx>
X-Modified-By: <responsável-da-alteração>

<conteúdo binário do XLSX>
```

## Validações no destino

- autorização presente e válida;
- conteúdo não vazio;
- assinatura ZIP do formato XLSX;
- extensão permitida;
- limite de tamanho;
- nome registrado como metadado;
- resposta estruturada com resultado e horário de ingestão.

## Monitoramento

O fluxo deve registrar pelo menos:

- horário de início e fim;
- status;
- etapa que falhou;
- código HTTP;
- identificador de correlação;
- nome do arquivo processado;
- tentativa e política de reprocessamento.

## Armadilha operacional

Alterar uma cópia local sincronizada não prova atualização do item online. Quando existe divergência, o arquivo do link oficial prevalece e deve ser reaberto para validação.
