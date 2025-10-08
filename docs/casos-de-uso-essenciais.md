# Casos de Uso Essenciais

## UC01 - Registrar Pedido

**Ator Principal:** Atendente

**Partes Interessadas e Interesses:**
- **Cliente:** Deseja fazer um pedido de forma rápida e sem erros
- **Atendente:** Deseja registrar o pedido de forma eficiente e enviá-lo para a cozinha
- **Cozinha:** Deseja receber pedidos claros e organizados para preparo
- **Gerente:** Deseja que os pedidos sejam registrados corretamente para controle de vendas

**Pré-condições:**
- O atendente está autenticado no sistema
- O cardápio está disponível no sistema

**Garantias de Sucesso (Pós-condições):**
- O pedido é registrado no sistema
- O pedido é enviado para a cozinha
- O cliente é informado sobre o pedido registrado

**Cenário de Sucesso Principal:**

1. Cliente chega ao estabelecimento e consulta o cardápio impresso
2. Cliente informa ao atendente os itens desejados
3. Atendente inicia o registro de um novo pedido no sistema
4. Atendente adiciona os itens solicitados pelo cliente ao pedido
5. Atendente confirma o pedido
6. Sistema registra o pedido com data/hora e número único
7. Sistema envia o pedido para a fila da cozinha
8. Sistema exibe confirmação do pedido registrado
9. Atendente informa ao cliente o número do pedido

**Extensões (Fluxos Alternativos):**

*3a. Cliente desiste do pedido:*
1. Atendente cancela a operação
2. Sistema descarta o pedido em andamento

*4a. Item não está disponível:*
1. Atendente informa ao cliente
2. Cliente escolhe outro item ou remove o item do pedido

*4b. Cliente deseja adicionar observações ao item:*
1. Atendente registra as observações específicas (ex: "sem cebola", "bem passado")
2. Sistema armazena as observações junto ao item

*5a. Cliente lembra de mais itens:*
1. Atendente retorna ao passo 4 para adicionar mais itens

**Requisitos Especiais:**
- O sistema deve ser responsivo (tempo de resposta < 2 segundos)
- Interface simples e intuitiva para uso sob pressão

**Lista de Variações Tecnológicas:**
- Terminal touch-screen
- Tablet
- Desktop

**Frequência de Ocorrência:** 
Pode ocorrer continuamente durante o horário de atendimento
