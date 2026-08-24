# Segurança e hardening

## Autenticação e autorização

- SSO corporativo e MFA;
- sessão com expiração e revogação;
- autorização por perfil;
- segregação entre administrador, editor e leitor;
- rate limiting e bloqueio progressivo;
- registro de tentativas e eventos administrativos.

## Secrets

- armazenar em secret manager;
- nunca embutir em código, fluxo exportado ou URL;
- rotação periódica;
- escopo mínimo;
- mascaramento em logs;
- revogação imediata após exposição.

## Upload e armazenamento

- allowlist de extensão e MIME;
- validação de assinatura do arquivo;
- limite de tamanho;
- inspeção antimalware;
- criptografia em trânsito e repouso;
- retenção e descarte;
- acesso privado aos objetos;
- metadados sem dados sensíveis desnecessários.

## Aplicação

- headers de segurança;
- proteção CSRF quando aplicável;
- validação de entrada;
- prevenção de injeção;
- dependências atualizadas;
- logs estruturados;
- alertas de erro e disponibilidade;
- testes de recuperação.

## Privacidade

O board deve exibir apenas os dados necessários para gestão. Evidências sensíveis permanecem no repositório oficial e o painel mantém referência controlada, não cópia indiscriminada.
