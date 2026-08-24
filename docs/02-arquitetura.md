# Arquitetura

## Componentes

| Componente | Responsabilidade |
|---|---|
| Excel Online | Fonte oficial do backlog e do roadmap |
| Power Automate | Detecta/agenda leitura do arquivo e envia o workbook vigente |
| Endpoint autenticado | Valida credencial, nome, extensão, tamanho e estrutura básica do XLSX |
| Armazenamento de objetos | Mantém a versão vigente do workbook para leitura pelo board |
| Banco operacional | Mantém recados, agendas e registros de aprovação separados do arquivo |
| Board web | Processa o workbook, apresenta visões e gera relatórios |
| Logs | Comprovam chamadas, status HTTP, resultado, horário e identificador de requisição |

## Fluxo de dados

```mermaid
sequenceDiagram
    participant E as Excel Online
    participant P as Power Automate
    participant A as API
    participant O as Armazenamento
    participant B as Board

    E->>P: Arquivo salvo
    P->>P: Ler conteúdo e metadados
    P->>A: POST XLSX + nome + autorização
    A->>A: Validar payload
    A->>O: Substituir versão vigente
    A-->>P: HTTP 200 + data de ingestão
    B->>O: Ler workbook vigente
    O-->>B: XLSX + metadados
    B->>B: Interpretar abas e colunas
    B-->>B: Atualizar visões e relatórios
```

## Por que separar arquivo e colaboração

O workbook é melhor para tabelas estruturadas e edição compartilhada. Recados, agendas e aprovações possuem ciclo próprio, consultas frequentes e anexos. A separação reduz acoplamento e evita regravar o Excel para cada interação do board.

## Requisitos de confiabilidade

- idempotência no recebimento;
- controle de tamanho e extensão;
- autenticação do endpoint;
- metadados de arquivo, origem e horário;
- cache desabilitado para a fonte vigente;
- logs sem exposição de segredos;
- rollback pela versão anterior do repositório de origem;
- monitoramento de falhas e fila de reprocessamento.
