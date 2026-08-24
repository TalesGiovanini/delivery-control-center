# Operação e incidentes

## Procedimento normal

1. abrir o workbook pelo link oficial;
2. confirmar nome, aba e tabela;
3. ler os registros atuais;
4. aplicar o delta autorizado;
5. preservar responsáveis vigentes;
6. atualizar autor e data/hora;
7. confirmar salvamento;
8. fechar e reabrir o mesmo arquivo;
9. reler os IDs alterados;
10. conferir execução do fluxo;
11. validar o board;
12. registrar o log.

## Incidente: planilha alterada, board antigo

Verificar, nesta ordem:

1. o arquivo editado é o item do link oficial?
2. a sessão possuía permissão de gravação?
3. o salvamento foi confirmado?
4. os valores persistiram após reabertura?
5. o fluxo leu o mesmo caminho?
6. o POST chegou ao endpoint?
7. a resposta foi 200?
8. o nome e o horário do arquivo ingerido estão corretos?
9. o board está usando a fonte vigente ou cache?
10. o parser encontrou as abas e cabeçalhos esperados?

## Incidente: fluxo com sucesso, conteúdo incorreto

Sucesso técnico não valida semântica. Baixar ou reler a fonte ingerida, comparar células-alvo e revisar se o fluxo enviou versão anterior, cópia local ou arquivo de caminho semelhante.

## Incidente: roadmap divergente

Comparar workstream, responsável, janela e resultado esperado. Não alinhar datas por aproximação. Registrar decisão quando houver replanejamento.

## Pós-incidente

Produzir linha do tempo, causa raiz, impacto, correção, prevenção, responsável, prazo e evidência de encerramento.
