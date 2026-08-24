# Como gerenciar RBAC

## 1. Separar mineração de aprovação

Frequência de acesso, perfil existente ou agrupamento estatístico identifica candidatos. Não comprova necessidade, menor privilégio, SoD ou aprovação.

Estados recomendados:

1. inventariado;
2. candidato minerado;
3. função reconciliada;
4. owner definido;
5. composição validada;
6. SoD analisado;
7. aprovado;
8. configurado;
9. testado;
10. publicado;
11. revisado periodicamente;
12. retirado.

## 2. Estrutura mínima de uma role

- identificador e nome;
- descrição de negócio;
- domínio e processo;
- população elegível;
- critérios de atribuição e remoção;
- entitlements e access profiles;
- owner e aprovador;
- risco e criticidade;
- conflitos SoD;
- exceções e validade;
- evidência de teste;
- data de revisão;
- status e versão.

## 3. Método de construção

### Inventariar

Consolidar aplicações, telas, permissões, grupos, perfis, pacotes e relações usuário–acesso. Preservar fonte, data-base e identificador técnico.

### Normalizar

Remover diferenças editoriais, mas não fundir permissões materialmente distintas. Separar ambiente, tela, rotina, opção e tipo de operação.

### Minerar candidatos

Agrupar por função, cargo, unidade, processo ou padrão de uso. O resultado permanece candidato.

### Reconciliar com a realidade funcional

Comparar cada permissão com telas, procedimentos, catálogo, normas e processo. Registrar correspondência, divergência e limite da evidência.

### Validar menor privilégio e SoD

Questionar necessidade, abrangência, conflito, exceção, risco e controle compensatório. Não usar coexistência histórica como autorização.

### Aprovar e testar

Obter decisão do owner e do aprovador, configurar em ambiente controlado, testar cenários positivos, negativos, exceções, revogação e reconciliação.

## 4. Gestão do ciclo de vida

Toda role deve possuir revisão periódica, indicadores de uso, regra de alteração, controle de versão, procedimento de exceção e critério de retirada. Role sem owner ou sem evidência de revisão é pendência de governança.

## 5. Indicadores úteis

- cobertura de entitlements por role aprovada;
- roles sem owner;
- roles sem revisão vigente;
- exceções vencidas;
- conflitos SoD por severidade;
- atribuições fora de critério;
- revogações não reconciliadas;
- tempo entre decisão e execução;
- role explosion e sobreposição funcional.
