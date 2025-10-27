# Backlog - Histórias de Usuário

## Epic: Registrar Pedido

Este epic engloba todas as funcionalidades relacionadas ao registro de pedidos no sistema da lanchonete.

---

## User Stories

### US01 - Iniciar Novo Pedido

**Como** atendente,  
**Quero** iniciar um novo pedido no sistema,  
**Para** começar a registrar os itens solicitados pelo cliente.

**Critérios de Aceitação:**
- [ ] O sistema deve gerar um número de pedido único ao iniciar
- [ ] O sistema deve exibir uma tela em branco para adicionar itens
- [ ] O sistema deve registrar qual atendente está criando o pedido
- [ ] O sistema deve registrar data e hora de início do pedido

**Prioridade:** Alta  
**Estimativa:** 3 pontos  
**Sprint:** 1

---

### US02 - Adicionar Item ao Pedido

**Como** atendente,  
**Quero** adicionar itens do cardápio ao pedido,  
**Para** registrar o que o cliente deseja pedir.

**Critérios de Aceitação:**
- [ ] O sistema deve permitir selecionar itens por categoria (sanduíches, bebidas, sobremesas)
- [ ] O sistema deve exibir o nome e preço de cada item
- [ ] O sistema deve permitir adicionar múltiplos itens ao pedido
- [ ] O sistema deve adicionar o item à lista do pedido quando selecionado
- [ ] O sistema deve atualizar o valor total do pedido automaticamente

**Prioridade:** Alta  
**Estimativa:** 5 pontos  
**Sprint:** 1

---

### US03 - Definir Quantidade de Item

**Como** atendente,  
**Quero** definir a quantidade de cada item,  
**Para** registrar corretamente quando o cliente pede mais de uma unidade do mesmo produto.

**Critérios de Aceitação:**
- [ ] O sistema deve permitir alterar a quantidade de um item (padrão: 1)
- [ ] O sistema deve aceitar quantidades de 1 a 99
- [ ] O sistema deve recalcular o valor total ao alterar a quantidade
- [ ] A quantidade deve ser exibida claramente junto ao item

**Prioridade:** Alta  
**Estimativa:** 3 pontos  
**Sprint:** 1

---

### US04 - Adicionar Observações ao Item

**Como** atendente,  
**Quero** adicionar observações específicas a cada item,  
**Para** registrar pedidos personalizados do cliente (ex: "sem cebola", "bem passado").

**Critérios de Aceitação:**
- [ ] O sistema deve permitir adicionar texto livre como observação
- [ ] Cada item pode ter sua própria observação independente
- [ ] As observações devem ser exibidas junto ao item no resumo
- [ ] As observações devem ser enviadas para a cozinha junto com o item

**Prioridade:** Média  
**Estimativa:** 3 pontos  
**Sprint:** 1

---

### US05 - Revisar Pedido

**Como** atendente,  
**Quero** revisar todos os itens do pedido antes de confirmar,  
**Para** garantir que está correto e evitar erros.

**Critérios de Aceitação:**
- [ ] O sistema deve exibir lista completa de todos os itens adicionados
- [ ] O sistema deve mostrar quantidade, nome, observações e preço de cada item
- [ ] O sistema deve exibir o valor total do pedido
- [ ] O sistema deve permitir editar o pedido antes da confirmação

**Prioridade:** Alta  
**Estimativa:** 2 pontos  
**Sprint:** 1

---

### US06 - Editar Item do Pedido

**Como** atendente,  
**Quero** editar ou remover itens do pedido durante a revisão,  
**Para** corrigir erros ou mudanças solicitadas pelo cliente.

**Critérios de Aceitação:**
- [ ] O sistema deve permitir alterar a quantidade de um item já adicionado
- [ ] O sistema deve permitir editar as observações de um item
- [ ] O sistema deve permitir remover um item do pedido
- [ ] O sistema deve atualizar o valor total após qualquer edição

**Prioridade:** Alta  
**Estimativa:** 5 pontos  
**Sprint:** 1

---

### US07 - Confirmar Pedido

**Como** atendente,  
**Quero** confirmar o pedido após revisão,  
**Para** registrá-lo definitivamente no sistema e enviá-lo para a cozinha.

**Critérios de Aceitação:**
- [ ] O sistema deve validar que o pedido contém ao menos 1 item
- [ ] O sistema deve atribuir um número definitivo ao pedido
- [ ] O sistema deve registrar data/hora de confirmação
- [ ] O sistema deve marcar o status do pedido como "Enviado para Cozinha"
- [ ] O sistema deve exibir mensagem de confirmação com o número do pedido

**Prioridade:** Alta  
**Estimativa:** 3 pontos  
**Sprint:** 1

---

### US08 - Enviar Pedido para Cozinha

**Como** sistema,  
**Quero** enviar o pedido confirmado para a fila da cozinha,  
**Para** que a equipe de preparo seja notificada em tempo real.

**Critérios de Aceitação:**
- [ ] O sistema deve enviar o pedido automaticamente após confirmação
- [ ] O pedido deve incluir número, itens, quantidades e observações
- [ ] O sistema deve registrar o envio no log
- [ ] Em caso de falha na comunicação, o sistema deve armazenar em fila de pendências

**Prioridade:** Alta  
**Estimativa:** 5 pontos  
**Sprint:** 1

---

### US09 - Cancelar Pedido em Andamento

**Como** atendente,  
**Quero** cancelar um pedido que ainda não foi confirmado,  
**Para** descartar registros quando o cliente desiste.

**Critérios de Aceitação:**
- [ ] O sistema deve permitir cancelar antes da confirmação
- [ ] O sistema deve solicitar confirmação do cancelamento
- [ ] O sistema deve descartar todos os dados do pedido ao cancelar
- [ ] O sistema deve retornar à tela inicial após cancelamento

**Prioridade:** Média  
**Estimativa:** 2 pontos  
**Sprint:** 1

---

### US10 - Informar Número do Pedido ao Cliente

**Como** atendente,  
**Quero** visualizar claramente o número do pedido após confirmação,  
**Para** informar ao cliente o número que ele deve aguardar.

**Critérios de Aceitação:**
- [ ] O número do pedido deve ser exibido em destaque na tela de confirmação
- [ ] O número deve ser fácil de ler e comunicar ao cliente
- [ ] O sistema pode opcionalmente imprimir um comprovante com o número

**Prioridade:** Média  
**Estimativa:** 2 pontos  
**Sprint:** 1

---

### US11 - Visualizar Categorias do Cardápio

**Como** atendente,  
**Quero** visualizar as categorias de produtos disponíveis,  
**Para** encontrar rapidamente o tipo de item que o cliente deseja.

**Critérios de Aceitação:**
- [ ] O sistema deve exibir botões ou abas para cada categoria
- [ ] Categorias devem incluir: Sanduíches, Bebidas, Sobremesas
- [ ] As categorias devem ser facilmente distinguíveis visualmente
- [ ] Ao selecionar uma categoria, deve exibir os produtos correspondentes

**Prioridade:** Alta  
**Estimativa:** 3 pontos  
**Sprint:** 1

---

### US12 - Tratamento de Erro de Comunicação

**Como** sistema,  
**Quero** tratar falhas de comunicação com a cozinha,  
**Para** garantir que nenhum pedido seja perdido.

**Critérios de Aceitação:**
- [ ] O sistema deve detectar falhas na comunicação
- [ ] O sistema deve armazenar pedidos em fila de pendências
- [ ] O sistema deve alertar o atendente sobre a falha
- [ ] O sistema deve tentar reenviar automaticamente quando a conexão for restabelecida
- [ ] O sistema deve registrar o status "Pendente de Envio"

**Prioridade:** Média  
**Estimativa:** 5 pontos  
**Sprint:** 2

---

### US13 - Registro de Auditoria

**Como** gerente,  
**Quero** que cada pedido registre qual atendente o criou,  
**Para** ter rastreabilidade e controle das operações.

**Critérios de Aceitação:**
- [ ] O sistema deve registrar o atendente que criou o pedido
- [ ] O sistema deve registrar data/hora de criação
- [ ] O sistema deve registrar data/hora de confirmação
- [ ] Os dados devem ficar disponíveis para relatórios futuros

**Prioridade:** Baixa  
**Estimativa:** 3 pontos  
**Sprint:** 2

---

## Planejamento de Sprints

### Sprint 1 - Core do Registro de Pedidos
**Objetivo:** Implementar funcionalidades básicas para registrar e enviar pedidos

**User Stories incluídas:**
- US01 - Iniciar Novo Pedido (3 pts)
- US02 - Adicionar Item ao Pedido (5 pts)
- US03 - Definir Quantidade de Item (3 pts)
- US04 - Adicionar Observações ao Item (3 pts)
- US05 - Revisar Pedido (2 pts)
- US06 - Editar Item do Pedido (5 pts)
- US07 - Confirmar Pedido (3 pts)
- US08 - Enviar Pedido para Cozinha (5 pts)
- US09 - Cancelar Pedido em Andamento (2 pts)
- US10 - Informar Número do Pedido ao Cliente (2 pts)
- US11 - Visualizar Categorias do Cardápio (3 pts)

**Total de Pontos:** 36 pontos

---

### Sprint 2 - Melhorias e Robustez
**Objetivo:** Adicionar tratamento de erros e funcionalidades de auditoria

**User Stories incluídas:**
- US12 - Tratamento de Erro de Comunicação (5 pts)
- US13 - Registro de Auditoria (3 pts)

**Total de Pontos:** 8 pontos

---

## Definição de Pronto (Definition of Done)

Uma User Story é considerada "Pronta" quando:

1. ✅ Código implementado seguindo padrões do projeto
2. ✅ Todos os critérios de aceitação foram atendidos
3. ✅ Testes unitários criados e passando (quando aplicável)
4. ✅ Interface mockada em papel testada com usuários
5. ✅ Documentação atualizada
6. ✅ Revisão de código realizada
7. ✅ Aceite do cliente/product owner obtido

---

## Observações

- As estimativas são em pontos de história (story points) usando escala de Fibonacci
- As prioridades podem ser ajustadas conforme feedback do cliente
- User Stories podem ser divididas em tarefas menores durante o planejamento da sprint
